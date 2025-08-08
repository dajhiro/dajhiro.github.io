- 깃허브 링크: https://github.com/hiro-jeon/Metroidvania-Scripts
## 구조
```markdown
<!-- Script -->
* CameraManager.cs
* PlayerMovement.cs
* Enemy.cs

<!-- GameObject -->
* Rat
* Player
```
---
## [[250808(금)]]


---
## [[250807(목)]]
### PlayerStatus
스테이터스는 향후 업그레이드를 통해 늘릴수 있도록 확장성을 고려해 설계하기 바람
- HP (어떤 데미지던 5회 받으면 사망) 
- [ ] 공격 횟수 (공격과 연결해서 연속 공격 4번 정도의 스태미너를 부여/ 스태미너는 항시 재충전하지만 재충전전에 4회 모두 고갈시 2초의 쿨타임 부여)
- 스태미나 (벽에 매달려있을수 있는 시간을 부여함. 벽에 매달리면 스태미너가 고갈되기 시작하고 고갈시 추락) 
- [ ] 점프횟수 - 2회 (더블점프 가능) 

## 할일
- [x] `Enemy.TakeDamage()` 만들기
- [x] `Player.Attack()` 만들기

## 기능 추가/변경
- [ ] UI: 적 HP 바 만들기
- [ ] Attack 2단 공격 만들기
- [ ] 플레이어 스탯 만들기
- [x] [`Enemy.TakeDamage()`](Enemy): 코루틴으로 관리,  [[250807(목)]], 17:03
- [x] [[Camera|카메라]] 움직임: `CameraManager.cs`, [[250807(목)]], 16:33
- [x] [`Player.OnCollisionEnter2D()`](Player): isFreezed 일때 무적, [[250807(목)]]

## 버그 수정
- [x] [`Enemy.TakeDamage()`](Enemy): (2)넉백으로 날라가지 않게: [[250807(목)]], 18:36
- [x] BoxCollider 크기 수정: 플레이어 뒤에있는 놈까지 맞으니
- [x] Enemy: 넉백으로 날라가지 않게
- [x] player-hurt 애니메이션 버그 수정


[[Debug|디버그]]
- `Debug.DrawRay(origin, lineVector, color)`
- `[SerializeField]`
### player-hurt 애니메이션 버그 수정
원인: 공격/대시공격은 Hurt 애니메이션을 재생하지 않아서 애니메이션 끝의 `EndHurt()`함수를 작동시키지 않는다. 그래서 `isFreezed = false`가 되지않아버린다
```markdown
- EndHurt()
+ IEnumerator Freezing()
	+ public float freezingTime = 0.5f;
	+ private Coroutine freezingCoroutine;
```

## Player: Attack()
이건 코루틴으로 처리: 어차피 그럴 예정이었음

이제 공격 히트판정을 만들자
- 폴리곤 일단 준비: [[Weapon Polygon Collider]]
- 그런데 걍 일단 박스형으로 하자 ㅋㅋ

![[Pasted image 20250807122345.png]]

``` markdown
PlayerMovement.cs
<!-- 애니메이션에 삽입 -->
+ Attack() <!-- 첫 공격 -->
```

다 구조는 비슷함 데미지나 이런 것들이 다른 거일뿐.
모두 애니메이션 탭에서 액션을 추가해서 사용할 거임.
BoxCollider2D를 만들어서 disable 상태로 만든 다음에
변수를 받아서 OverlapCollider를 사용할거임
레츠꼬

BoxCollider2D는 변수로 받을때 그냥 Collider2D로 하면 안되나? 나중에 쉽게 바꾸게.
에이 그냥 나중에 금방 바꾸지뭐

### Variable
```csharp
public BoxCollider2D attackCollider;
	// 추후 변경: 모션마다 콜라이더를 다르게 한다면 사전형 또는 리스트로
public int damage;
	// 추후 변경: 일단 동일하게
public LayerMask enemyLayer;

private ContactFilter2D contactFilter
```

### `Awake()`
콘택트 필터 만드는 중임(이거 솔직히 왜 만들어야함?)
```csharp
contactFilter = new ContactFilter2D();
contactFilter.SetLayerMask(enemyLayer);
contactFilter.useTriggers = true;
```

### `Attack()`
몰라 귀찮으니까 일단 이걸로 통일 빠르게 만드는게 더 중요함
- `attackCollider.Overlap(contactFilter, hits)`



## [[Enemy]]: OK
### 안됨
TakeDamage: 기능
- [x] 뒤로 밀려난다: 이거 작동 안함
	- [x] isEdge는 뒤로 밀려나면서도 항상 작동해야해
	- [x] 일단 지금은 Move() 때문에 아예 안됨
	- [x] 밥먹고나서 ㄱㄱ

---
적 스탯을 만들고
데미지를 당했을 때... 어떻게 처리할지

```markdown
Enemy.cs <!-- 목표 -->
+ TakeDamage()
+ Animation End <!-- 애니메이션 종료 후 실행할 함수 -->
	+ OnDamageEnd()
	+ OnDeathEnd() 
```
### `TakeDamage()`
- 변수
	- `int hp`
	- `int damagedForce`
	- `bool isFreezed`
- 기능
	- [ ] 뒤로 밀려난다: 이거 작동 안함
	- 중복으로 안맞게 상태를 설정한다: `맞고 있음 = true`
	- 체력을 줄인다
		- `if (hp < 0)` 파괴
			- 사망 트리거를 올린다
			- 사망 애니메이션 이후는 `OnDeadEnd()`
	- 대미지 트리거를 올린다
		- 데미지 애니메이션 이후는 `OnDamageEnd()`
- `OnAnimationEnd()`
	- `OnDamageEnd()`
		- `isFreezed` 상태 해제
	- `OnDeadEnd()`
		- `isFreezed` 상태 해제
		- deactive 상태로 만든다: 언젠가 쓰겠지

## 잡다한 것들
- [[Unity]]: `[Attribute]`
- 질문: 하나의 [애니메이터](Animation)를 다른 적 오브젝트에게도 적용시키고 싶은데 다들 스프라이트가 달라서 들어가는 애니메이션이 달라. 한번에 관리할 수 있는 방법이 없을까?
	- 해결: Animation Override Controller 라는 게 있군
- 질문: Animation Clip에서 Loop time을 끄지 않고 Trigger를 돌리면 영원히?
	- 해결: 처맞고 버그난 거 이거때문임? 그럴지도 일단 해결

---
## [[250806(수)]]: [[Enemy]](Rat) 기본 완성
- 버그: Tilemap 위에서 `linearVelocity.x = 1`인데도 움직이지 않음

```Markdown
Enemy.cs
+ MonoBehaviour
	+ Update()
	+ FixedUpdate()
	+ OnTriggerStay2D()
+ IEnumerator
	+ ChasePlayer()
	+ SetRandomDirection()
	+ SetDirectionToPlayer()
+ Move()
```

---
## [[250805(화)]]
사다리 타기

### [[버그]]
하자
- 지형지물을 통과하려면?
	- 사다리를 타고 있을 때에는 레이어 충돌을 없애고
	- 사다리에서 벗어날 때만
		- OnTriggerEnter2D
	- 흠 점프를 하면 끼어버리네
	- 그렇다면 그라운드를 다시 수정해야겠다.
		- Ground와 벽(Wall)은 별개로 관리해야지
		- 추후 ㄱㄱ

- [x] [[트러블슈팅]]: Transform 콜라이더랑 안 맞음  
- [x] [[트러블슈팅]]: 사다리 타기
## 사다리 타기: 진입/탈출/타는 중
- [x] [[사다리]]
- [x] 애니메이션: [[사다리 타기]]
## [[250804(월)]]
- `Animator.SetFloat()`

[[모션]]
- [x] [[정지]]
- [x] [[걷기]]
- [x] [[점프]]
- [x] [[낙하]]
- [x] [[공격]]
- [x] [[대시]]
- [x] [[대시공격]]
- [x] [[피격]]
- [x] [[사망]]
- [x] [[슬라이딩]]: Dash + Ctrl
- [x] [[앉기]]: Ctrl
	- [ ] 슬라이딩 ⇒ 앉기는 포기
- [x] [[사다리 타기]]
	- [ ] 사다리에서 점프 시 끼이는 버그: 추후 Wall/Ground 레이어를 분리하여 구현
- [ ] [[벽 슬라이딩]]

## 피격
### 장애물
- [[Layer]]: Obstacle
- [`OnTriggerEnter2D()`](OnTriggerEnter2D)
	- `if (!isFreezed && hit.gameObject.layer == "")`
- Exit Time이 문제가 되는가?



앉기 도대체 어떻게???

슬라이딩 ⇒ 앉기

슬라이딩 할 때에는 뭐 누를 수 없음
isSliding을 따로 만들어서

- [x] 콜라이더 설정 성공

`PlayerController.cs`에 모두 때려박혀 있는데
이걸 분리하고 싶다

---
## [[250803(일)]]: 이거까지는 (오늘 내로) 만들 수 있어야함
## 초기 세팅
- 패키지
- [[URP 2D]]
- [[Unity 키워드]]

## 플레이어 
### 플레이어 오브젝트(시작)
- `Player`: `GameObject`
	- Sprite
		- `SpriteRenderer`
			- `Material: Sprite-Lit-Default`
		- `Animator`
	- `CapsuleCollider2D`
	- `Rigidbody2D`
	- `PlayerController.cs`

## 애니메이션 쉬운 거부터 시작해보자
### 1. idle - run 
- 대기(Idle)
- 뛰기(Run)

애니메이션 클립 만들기
플레이어 오브젝트 - 애니메이션 창(Windows → Animation → Animation) - 스프라이트 끌어오기

스크립트를 먼저 짜야함
Input System 공부하느라 애먹음...

애니메이터 조작(Blend Tree)
- Blend Tree
	- Motion → Blend Tree: 더블클릭
- Blend Tree setting
	- Parameter setting
- Transition

---
### 2. jump - fall
점프(Jump) && 낙하(Fall)
Input System
- Action Maps
	- **Action**을 만든다
		- Jump

바닥을 만들자
2D Object → Sprite → BoxCollider2D
Ground

idle → jump → fall → idle
run → jump → fall → run

### 3. attack
- 애니메이션 클립 생성
- Input System에 키 지정: `A`
- Animator에 Attack 트리거 지정
	- idle → attack
	- run → attack
- 스크립트 작성
	- `EndAttack()`
		- 애니메이션 설정
			- 애니메이션 종료 시점에 메서드 실행
			- Add Event 버튼

점프하고 나서 A 눌렀떠니 멈춘다
A가 이동 + 공격

### 문제
아니 근데 너무 개판인데
애니메이터 원래 이렇게 더러운 건가?
관리가 안돼
그리고 공격 조건이 없어서 문제네
- run, idle 에서만 공격 가능

뭔가 이동 방향들을 정해보자

---

앉기 시작/종료 애니메이션이랑 앉는 중 애니메이션이랑 분리해야하나?
루프랑 트랜지션 설정하고
분리는 따로 할필요없고 종료면
Idle로 연결하면 될듯

이거 이해가 안가
루프랑 트랜지션

조작 관련 모든것 (이동 속도 점프 횟수 중력 대쉬 시간 대쉬 거리 등등 모든것은 향후 조정이 쉽게 `serializefield`를 이용할것)
### [[콜라이더]]
![[Pasted image 20250803181022.png|200]]

콜라이더는 캐릭터 스프라이트보다 작게

캐릭터는 캡슐 콜라이더를 사용
콜라이더는 발바닥 부분에 맞춰서
- 땅을 뚫거나 공중에 뜨지 않게 조심하고
- 그외 부분은 스프라이트보다 조금 더 적게 적용함

## 점프
![[Pasted image 20250803181043.png|200]]
### 점프 물리
- https://www.youtube.com/watch?v=yorTG9at90g&t=188s
점프시 가장 높은 지점에 도달하기 전까지는 중력값이 동일하지만 제일 높은지점부터는 뚝 떨어지게 중력값을 조절함

### 코요테 타임
https://www.youtube.com/watch?v=14M8BYHhGLs

### 타일셋
그리고 타일셋으로 타일을 언제든지 찍고 레벨을 만들수있도록  타일 준비까지가

간단하쥬?

준 캐릭터 스프라이트 파일에서
`no_dust`라고 쓰인거는 사용하지 말것

- 깃허브 링크: https://github.com/hiro-jeon/Metroidvania-Scripts
- 개인 독스: [[Unity]]
## [[250805(화)]]

## 버그
- [ ] 그리드가 안 보임
- [ ] 벽에 붙는 거
- [ ] Transform 오프셋 위치 콜라이더랑 떨어짐
	- [x] 스프라이트 피봇 위치 수정: Buttom ⇒ Custom
		- [ ] 기존: (0.42, 0)
		- [ ] 사다리: (0.47, 0)
	- [x] 사다리만 또 따로 피봇 위치 수정
	- [ ] 자꾸 좌우로 조금씩 틀어짐
		- [ ] isOnLadder 후 위치 바꾸기 전에 속도 0으로 고정: 실패
		- [ ] Collider가 사다리 안으로만 들어오게 피봇 위치 미세조정
			- [ ] ⇒ (0.474, 0)
	- [ ] 

## 사다리 타기: 진입/탈출/타는 중
애니메이션: [[사다리 타기]]

### 버그
- [x] Gravity가 돌아오지 않는다


## 진입: `isOnLadder = true`
###  활성화
- 콜라이더 무시: `CapsuleCollider2D` 비활성화
- 사다리 안에서만 움직일 수 있음(FixedUpdate 비활성화)
플레이어 위치(x값)를 사다리로 옮기기
```csharp
Vector3 contactPoint = col.ClosestPoint(transform.position);
Vector3Int cellPos = tilemap.WorldToCell(contactPoint);  // 셀 위치(index)로 전환
Vector3 tileWorldPos = tilemap.GetCellCenterWorld(cellPos); // 셀의 world position으로 전환

using UnityEngine.Tilemaps;

```


### 조건
사다리 근처에서 위(`Up`) 방향키를 입력했을 경우
- [`OnTriggerStay2D()`](OnTriggerStay2D): 사다리 근처에 도달
```csharp
// 사다리 레이어 확인 후
if (!isOnLadder && moveInput.y > 0) // 위 방향키 입력
{
	isOnLadder = true;
}
```


사다리 위에서 아래(`Down`) 방향키를 입력했을 경우
- [x] 사다리 맨 위에서 타고 내려오는 경우????? 이거 어떻게 하지
	- [x] 사다리 맨 위 인식 어떻게?
	- [x] 아 ! 바닥에 있으면 레이캐스팅 해서 쏘면 되지
	- [x] Update()로 일단 탐지
## 탈출: `onLadder = false`
점프/피격/사망 또는 [`OnTriggerExit2D()`](OnTriggerExit.md)

- [`OnTriggerExit2D()`](OnTriggerExit.md): 사다리 끝
```csharp
isOnLadder = false;
animator.SetTrigger("LadderExit");
```

- `Update()`: 점프/피격/사망
```csharp
if (isOnLadder)
{
	if (isHurting || isDead || jumpPreseed)
	{
		isOnLadder = false;
		if (jumpPressed)
		{
			
		}
	}
}
```

사다리 점프값 따로... 

근데


### 타는 중: 
- 중력값 0
- 공격/


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
- [ ] [[사다리 타기]]
- [ ] 벽 슬라이딩

## 피격
### 장애물
- [[Layer]]: Obstacle
- [`OnTriggerEnter2D()`](OnTriggerEnter2D)
	- `if (!isHurting && hit.gameObject.layer == "")`
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
### PlayerStatus
스테이터스는 향후 업그레이드를 통해 늘릴수 있도록 확장성을 고려해 설계하기 바람
- HP (어떤 데미지던 5회 받으면 사망) 
- 공격 횟수 (공격과 연결해서 연속 공격 4번 정도의 스태미너를 부여/ 스태미너는 항시 재충전하지만 재충전전에 4회 모두 고갈시 2초의 쿨타임 부여) 
- 스태미나 (벽에 매달려있을수 있는 시간을 부여함. 벽에 매달리면 스태미너가 고갈되기 시작하고 고갈시 추락) 
- 점프횟수 - 2회 (더블점프 가능) 

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

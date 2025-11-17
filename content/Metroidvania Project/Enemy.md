## Movement
정리된 부분
### property: `direction`
```csharp
private Vector2 direction;
```
방향만을 의미한다
- `isChasing == true`: 플레이어 방향
- `isChasing == false`: 랜덤 방향 `([-1, 1], [-1, 1])`

### property: `move`
```csharp
private Vector2 move;
```
조건을 받아들여서 실제로 움직이는 방향으로 정한다
- `!isAir`
	- `isEdge == true`
		- `Vector.zero`
	- `isEdge == false`
		- `move.x = direction.x`
- `isAir`
	- `move = direction`


추후 수정하자
- IsOnEdge면 움직임을 중단해야 한다
	- 근데 IsOnGround일 때에만 체크해야 한다
	- 이걸 다 합치려고 하니까 미친다
- 하나하나 분리하자
IsOnGround
근데 또 IsOnGround를 넘어가버리는 현상이 발생한다
IsOnEdge는 가고자 하는 방향이나, 가고 있는 방향으로 레이를 쏴서 물건이 있는지 확인한다


움직임
isEdge
공중에 떠있든지
움직이는 방향에 아무것도 없든지

Move()

move
실제 움직임: Move()에서만 동작

direction
방향: 랜덤 또는 플레이어 

direction은 정해지는 것: normalize 할 필요 없음
move에서 
move는 변환
- 공중
- 지상


## Scripts
### `Enemy.TakeDamage()`
### 완료: 넉백으로 날라가지 않게: [[250807(목)]], 18:36
왜 날라갔냐면 이동(의도) 방향으로만 Ray를 쏴서 그랬던 것이었다.
Freezed 상태면 날라가는 방향으로 Ray를 쏴야 하는데
반대 방향으로 쏘는데 얘가 감지를 하겠음? 바보같았다.

수정 코드
```csharp
// FixedUpdate()
Vector2 rayDirection;
if (!isFreezed)
	rayDirection = Vector2.down + direction;
else
	rayDirection = Vector2.down + rb.linearVelocity;
isEdge = !Physics2D.Raycast(transform.position, rayDirection, raycastDist, groundLayer);

```

[[Debug|디버그]] 함수
- `Debug.DrawRay(origin, lineVector, color)`
- `[SerializeField]`

### 완료: 적 무적상태 없애기, [[250807(목)]]
`isFreezed`일 시 움직임 멈춤, 하지만 무적은 해제,
적은 isFreezed일때 당연히 무적따위 없고 그리고 처맞는데 기다려주는 것도 없애버릴거다 너네 배려하다가 게임이 삭제될 수가 있어
- 즉 `TakeDamage()`에서 `isFreezed`일때도 때릴 수 있다
	- `if (!isFreezed)` 제거
	- `if (isDead)` 추가
- [[Coroutine|코루틴]]으로 제어하기
	- 코루틴 중이면: 코루틴 멈추고 새로 갱신
		- 어쨌든 다음 코루틴에서도 할거니 isFreezed은 false가 될거다

## EnemyObject
- Rigidbody2D
- BoxCollider2D: 몸체
- CircleCollider2D: 시야 감지용 Trigger
- Scripts: `Enemy.cs`
	- `FixedUpdate()`
		- `IsAtEdge()`
		- `Move()`
		- `Flip()`
	- `Update()`
		- `if (isEdge)`
			- `direction = Vector2.zero`
		- `if (isChasingMode)`
			- `direction = player.position - transform.position`
		- `if (!isChasingMode)`
			- `direction = 주기적으로 바뀌는 방향` 
- Animation
	- idle
	- run
	- hurt
	- death

[[Sprite]]
- [x] Multiple Sprite인데 피봇을 모두 Center Buttom으로 하고 싶어. 그런데 일일이 하나씩 해야하나?
- ⇒ ㄴㄴ SpriteEditor로 하나만 선택해서 Slice로 하면 됨
	- 안그래도 스프라이트 Auto Slicing 되어있어서 Grid로 바꾸고 피봇 위치만 수정 
	- Grid로 Slice하니 결국 pivot은 커스텀

### 플레이어 감지(시야)
- `OnTriggerStay2D()`
	- `if (!isChasing)`
		- `StartCoroutine()`
			- `isChasing = true`
			- `WaitForSeconds(chasingTime)`
			- `isChasing = false`

~~플레이어 닿음(플레이어 Hurt)~~
- ~~OnCollisionEnter2D()~~


질문
- 데미지를 입는 쪽에서 OnCollision을 할까 
- 데미지를 주는 쪽에서 할까
	=>  데미지를 입는 쪽

## Rat
### Movement
- 방향 정하고
	- !isChasing
		- 떠도는 시간: maxChangeTime 내의 랜덤 시간
		- 방향
			- 멈춤(33%)
			- 좌우(66%)
	- isChasing
		- 플레이어 방향으로 계속 가기

### 플레이어 감지: OnTriggerStay2D
일단 CapsuleCollider2D 인지만 검사하자 +레이어

### `Update()`
- 방향값 설정
	- 랜덤 방향
	- 플레이어 방향
- 만약 isEdge 면 멈춤

### `FixedUpdate()`
- isEdge 검사
- 움직임 구현(`Move()`)


## 클래스
### `LayerMask`
- `NameToLayer("Name")`

### `Collider2D`
- [`Collider2D.Distance()`](Collider2D.Distance)
- `gameObject`

### `gameObject`
- `layer`
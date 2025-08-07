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
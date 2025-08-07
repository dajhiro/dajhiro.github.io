오브젝트 비활성화
```csharp
gameObject.SetActive(false);
```

## C\#
`[Attribute]`: Unity
- `[Header("Title")]`
- `[Space]`
- `[Tooltip("at hovering it is shown")`
- `[Range(min, max)]`

- [[애니메이션]]

## MonoBehaviour
### Method
Default
- `Start()`
- `Awake()`
- `OnEnable()`

- `Update()`
- `FixedUpdate()`

GameObject
- `SetActive(bool)`

[[Trigger]]
- [`OnTriggerEnter2D()`](OnTriggerEnter2D)
- [`OnTriggerStay2D()`](OnTriggerStay2D)

Collider
- `OnCollisionEnter2D(Collision2D col)`

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
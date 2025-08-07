## EnemyObject
- Rigidbody2D
- BoxCollider2D
- CircleCollider2D: Trigger
- Scripts: `Enemy.cs`
	- `Move(Vector2 direction)`
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
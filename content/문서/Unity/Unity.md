## 최근
### GameObject.SetActive 비활성화
```csharp
gameObject.SetActive(false);
```

### [[Attribute]]
`[Attribute]`: Unity
```csharp
[Header("Title")]
[Space]
[Tooltip("at hovering it is shown")
[Range(min, max)]
```

### [[Coroutine]]
- `StartCoroutine()`
	- 비동기적이므로 실행 즉시 다음 코드로 넘어간다
	- 코루틴을 끝내고 넘길지, 아니면 코루틴을 무시하고 갱신할지는 선택할 수 있음

---
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

Collision(충돌: Collider 아님)
- `OnCollisionEnter2D(Collision2D col)`

Rigidbody2D
- `AddForce(Vector2 direction, [ForceMode])`

[[Enemy]]

---
- [[애니메이션]]
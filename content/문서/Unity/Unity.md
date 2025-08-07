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
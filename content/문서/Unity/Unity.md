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

Rigidbody2D
- `AddForce(Vector2 direction, [ForceMode])`

[[Enemy]]

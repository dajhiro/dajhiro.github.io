## 최근
## MonoBehaviour
### 유니티 컴포넌트 생명 주기
- **게임 오브젝트 생성 → 컴포넌트 추가 → 활성화 → 첫 프레임 → 비활성화 → 파괴**
### [[순서도]]
게임 오브젝트 생성 및 컴포넌트 추가
- `Reset()`: 컴포넌트가 에디터에서 추가될 때 1회 호출
씬이 로드되거나 오브젝트가 인스턴트화 될 때
- `Awake()`: 씬에 로드되자마자 1회 호출(활성화 여부 무관)
- `OnEnable()`: 활성화 시마다 호출
- `Start()`: 활성화 상태일 때 첫 프레임 전에 1회 추출
게임 플레이 루프 시작
- `FixedUpdate()`: 물리 프레임마다 호출: 고정 주기
- `Update()`: 매 프레임마다 호출: 게임 로직 처리
- `LateUpdate()`: `Update()`가 끝난 뒤 호출
종료
- `OnDisable()`: 컴포넌트 비활성화 시 호출
- `OnDestroy()`: 오브젝트/컴포넌트가 완전히 파괴될 때 호출

Update와 FixedUpdate의 차이
Update
- 매 프레임

FixedUpdate
- 고정된 시간 간격

---
### `GameObject.SetActive()`: 활성화/비활성화
```csharp
gameObject.SetActive(true);
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


---
- [[Animation]]
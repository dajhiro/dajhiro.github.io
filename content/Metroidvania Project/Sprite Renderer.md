## 선언
```csharp
SpriteRenderer sr = gameObject.GetComponent<SpriteRenderer>();
```

## 프로퍼티
```markdown
* bounds
	* Vector3 size
```

## 그래서
### 크기 구하는 법
```csharp
SpriteRenderer sr = gameObject.GetComponent<SpriteRenderer>();

Vector3 size = sr.bounds.size;
float width = size.x;
float height = size.y;
```

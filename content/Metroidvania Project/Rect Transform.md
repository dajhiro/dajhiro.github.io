선언
```csharp
RectTransform rt = gameObject.GetComponent<RectTransform>();
```

프로퍼티
```markdown
* rect
	* width
	* height
```

크기 구하는 법
```csharp
RectTransform rt = gameObject.GetComponent<RectTransform>();
if (rt != null)
{
	float width = rt.rect.width;
	float height = rt.rect.height;
}
```

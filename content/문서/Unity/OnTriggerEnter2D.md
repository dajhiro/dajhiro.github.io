- [[Unity]]

### (GPT)여러 개의 레이어를 LayerMask로 비교
```csharp
public LayerMask ladderLayerMask;

void OnTriggerEnter2D(Collider2D collision)
{
    if (((1 << collision.gameObject.layer) & ladderLayerMask) != 0)
    {
        isNearLadder = true;
    }
}

```
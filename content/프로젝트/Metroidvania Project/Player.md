

### isFreezed 일때 무적
```markdown
+ public float immortalTime = 1.5f;

private IEnumerator Freezing()
+ Physics2D.IgnoreLayerCollision(true);
+ WaitForSeconds(immortalTime - freezingTime);
+ Physics2D.IgnoreLayerCollision(false);
```
- freeze 추가
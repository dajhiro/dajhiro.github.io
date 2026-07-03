# REST API 캐싱
반복적인 요청에 대한 응답을 저장, 재사용하여
서버 부하를 줄이고 응답 속도를 높이는 기법

## HTTP 캐시 헤더
Cache-Control 헤더
```http
[Header]
Cache-Control: max-age=3600
Cache-Control: no-cache
Cache-Control: no-store
Cache-Control: private
Cache-Control: public
```
- `max-age=3600` — 3600초(1시간) 동안 캐시 유효
- `no-cache` — 캐시하되 사용 전 검증 필요
- `no-store` — 아예 캐시하지 않음
- `private` — 브라우저(클라이언트)만 캐시 가능
- `public` — 중간 프록시/CDN도 캐시 가능

### 기타
- ETag
- Last-Modified / If-Modified-Since

### 캐시 위치별 전략
- 클라이언트(브라우저) — Cache-Control, ETag, 개인화된 데이터
- CDN/Proxy — 정적이거나 공용 데이터, `public` 설정 필요
- API Gateway 캐싱 — AWS API Gateway, Kong 등에서 응답 자체를 캐시
- 서버 사이드 캐싱 — Redis, Memcached 등으로 DB 조회 결과를 캐시

## 서버 사이드 캐싱 — Redis

### 코드
```js
app.get('api/products/:id', async (req, res) => {
  const cacheKey = `product:${req.params.id}`;
  
  // 캐시 확인
  const cached = await redis.get(cacheKey);
  if (cached) {
    return res.json(JSON.parse(cached));
  }
  
  // DB 조회 후 캐시 저장
  const product = await db.getProduct(req.params.id);
  await redis.set(cacheKey, JSON.stringify(product), 'EX', 300);
  res.json(product);
});
```

### 전략
- TTL(Time-to-Live): 일정 시간 후 자동 만료
- 이벤트 기반 무효화: 데이터 변경(POST/PUT/DELETE) 시 관련 캐시를 명시적으로 삭제
- Cache Busting: URL에 버전을 붙여 새 리소스는 새 URL로 취급 (`/api/v2/...`)

```js
// 데이터 변경 시 캐시 무효화
app.put('/api/products/:id', async (req, res) => {
  await db.updateProduct(req.params.id, req.body);
  await redis.del(`product:${req.params.id}`); // 캐시 삭제
  res.json({ success: true });
});
```




















# REST, Representational State Transfer
CRUD(Create-Read-Update-Delete)의 HTTP 메서드 매핑

```
POST user/dajhiro
GET user/dajhiro
```

```
POST /createUser
```

## REST 원칙<sub>constraint</sub>
### 1. Client-Server
클라이언트(UI, 상태관리)와 서버(비즈니스 로직, 데이터 관리)의 책임을 명확히 분리
- 클라이언트는 표현(화면)만 신경씀
- 서버는 데이터 로직만 신경씀

### 2. Stateless
- 장점: 서버 확장(스케일링)이 쉬움 — 아무 서버나 요청을 처리해도 됨
- 대신 클라이언트가 상태(토큰, 컨텍스트)를 계속 들고 다녀야 함

### 3. [[Cacheable]]
응답에 이 데이터는 캐시해도 되는지, 얼마나 유지해도 되는지 명시
```
Cache-Control: max-age=3600
Etag: "abc123"
```

불필요한 서버 요청을 줄여서 성능/확장성 향상

### 4. Uniform Interface
REST의 핵심이자 가장 지켜지지 않는 원칙
1) 자원의 식별 Resource Identification
	- URL로 자원을 명확히 식별, `/user/[id]`는 명확히 자원 그 자체를 가리킴
2) 표현을 통한 자원 조작 — Manipulation via Representations
	- 자원을 직접 만지는 게 아니라, 그 표현(JSON, XML 등)을 받아서 조작함.
3) 자기 서술적 메시지 — Self-descriptive Messages
	- 메시지 자체에 처리 방법이 담겨 있어야 함. `Content-Type: application/json` 같은 헤더가 그 예
4) HATEOAS — Hypermedia as Engine of Application State
	- 응답에 "다음에 할 수 있는 행동"의 링크를 포함시켜야 함.

```json
{
  "id": 123,
  "name": "홍길동",
  "links": [
    { "rel": "self", "href": "/user/[id]" },
    { "rel": "order", "href": "/user/[id]/order" },
    { "rel": "delete", "href": "/user/[id]/delete" },
  ]
}
```

### 5. Layered System
클라이언트는 서버와 직접 통신하는지, 중간에 로드밸런서-캐시-프록시-게이트웨이가 있는지 몰라도 됨(몰라야 함).
```
클라이언트 → ([CDN] → [로드밸런서] → [API 게이트웨이] →) 서버
```

### 6. Code on Demand (Optional)
서버가 실행 가능한 코드(JS 등)를 클라이언트에 보내서 클라이언트의 기능을 확장할 수 있음.


- Caching
- Stateless
- Layered system
- HATEOAS


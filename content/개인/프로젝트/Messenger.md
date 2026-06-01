Facebook Messenger의 프로토콜
모바일: [[MQTT]]
웹: [[MQTT]] over WebSocket

MQTT: 발행-구독(pub/sub) 모델

WebSocket을 전송 계층으로 깔고, 그 위에 MQTT 프로토콜을 얹는 구조



WebSocket 자체를 쓴다기보다,
**WebSocket을 MQTT의 전송 수단으로 활용**하는 구조입니다.
Discord나 Slack처럼 "순수 WebSocket"을 쓰는 서비스들과는 설계 철학이 다릅니다.

브라우저는 TCP를 직접 쓸 수 없어서

- [x] 그럼 TCP 프로토콜만 가지고도 양방향 통신이 가능하단거야?
	- full-duplex

HTTP가 요청-응답 규약을 강제하기 때문이지,
TCP는 단방향이 아니다.

---
DM

WebSocket 서버는 상태를 유지해야 해서 스케일링이 어렵지만,
HTTP API는 무상태라 스케일링이 쉽고 기존 인증/권한/레이트리밋 미들웨어를 재사용할 수 있기 때문입니다.

- 스케일링이 뭐여?
- SSE

---
### SSE, Server-Sent Events
서버가 클라이언트에게 일방적으로 데이터를 밀어주는 HTTP 기반 기술

```js
const es = new EventSource('/stream');

es.onmessage = (e) => {
  console.log(e.data);
}


```















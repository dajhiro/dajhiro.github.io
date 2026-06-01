클라이언트와 서버 간의 양방향 실시간 통신을 가능케 하는 프로토콜
HTTP vs WebSocket

HTTP: Request/Response 모델

클라이언트가 요청해야만 서버가 응답할 수 있다.
연결은 매번 끊긴다. (1회성)

---
### handshake
```http
GET /chat HTTP/1.1
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: dGhlIHNhbXBsZSBub25jZQ==
```

101 Switching Protocols ⇒ WebSocket 프로토콜로 통신

### 브라우저
```js
const ws = new WebSocket('wss://example.com/socket');

ws.onopen = () => ws.send('hello');
ws.onmessage = (e) => console.log(e.data);
ws.onclose = () => console.log('disconnected');
ws.onerror = (e) => console.error(e);
```

### NestJS
```ts
@WebSocketGateway({ cors: true })
export class EventsGateway {
  @WebSocketServer()
  server: Server;
  
  @SubscribeMessage('generate')
  handleGenerate(@MessageBody() data: { videoId: string }) {
    this.server.emit('progress', { step: 'transcribing...' });
  }
}
```

---
















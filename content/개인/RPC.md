RPC, Remote Procedure Call
원격 함수 호출
여러 서버를 가지고 있을 때, **서버의 함수**를 호출하는 것.
예를 들어 


```ts
const user = await this.userClient.getUser({ id: 123 }).toPromise()
```

내부

- **gRPC** (Google) — Protocol Buffers로 직렬화, HTTP/2 위에서 동작. 지금 MSA에서 가장 많이 씀
- **tRPC** — TypeScript 타입을 그대로 공유. TexTube 같은 Next.js 풀스택에서 인기
- **JSON-RPC** — REST랑 비슷한데 엔드포인트 대신 메서드 이름으로 호출
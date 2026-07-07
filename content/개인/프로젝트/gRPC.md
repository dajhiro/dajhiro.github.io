특징
- 양방향 스트리밍
- [[Protobuf]], Protocol Buffers
- HTTP/2
- 다양한 통신 방식
	- Request-Respond
	- Server Streaming
	- Client Streaming
	- Client-Server Streaming

```proto
syntax = "proto3"

service Translator {
  rpc Translate (TextInput) returns (TextOutput);
}

message TextInput {
  string text = 1;
  string lang = 2;
}

message TextOutput {
  string translated_text = 1;
}
```

서비스(Translator)와 메시지 구조를 정의하면,
`protoc` 명령어를 통해 다양한 언어로 코드가 생성된다.

## 예시
- [[gRPC — Upper]]













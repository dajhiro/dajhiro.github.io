## 예제
클라이언트: Python

서버: 문자열을 대문자로 바꿔주는 서버

```
SayHello("hello") ⇒ HELLO
```

### 서버 구현: `server.py`
[[차이점 비교 — Chat]]

```python
from concurrent import futures
import grpc
import hello_pb2
import hello_pb2_grpc

class HelloService(hello_pb2_grpc.HelloServiceServicer):
	def SayHello(self, request, context):
		reply = request.message.upper()
		return hello_pb2.HelloResponse(message=reply)

def serve():
	server = grpc.server(futres.ThreadPoolExecutor(max_workers=10))
	hello_pb2_grpc.add_HelloServiceServicer_to_server(HelloService(), server)
	server.add_insecure_port('[::]:50051')
	server.start()
	print("Server started on port 50051")
	server.wait_for_termination()

if __name__ == '__main__':
	serve()
```

### 클라이언트: `client.py`

```python
import grpc
import hello_pb2
import hello_pb2_grpc

def run():
	channel = grpc.insecure_channel('localhost:50051')
	stub = hello_pb2_rpc.HelloServiceStub(channel)
	response = stub.SayHello(hello_pb2.HelloRequest(message="hello grpc"))
	print("Response from server: ", response.message)

if __name__ = '__main__':
	run()
```
















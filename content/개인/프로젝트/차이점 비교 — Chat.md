![[gRPC — Upper#서버 구현 `server.py`]]

```python
import grpc
from concurrent import futures
import time
import chat_pb2
import chat_pb2_grpc

class ChatService(chat_pb2_grpc.ChatServiceServicer):
    def Chat(self, request_iterator, context):
        for chat in request_iterator:
            print(f"[{chat.sender}]: {chat.message}")
            response = chat_pb2.ChatMessage(
                sender="Server",
                message=chat.message.upper()
            )
            yield response

def serve():
    server = grpc.server(futures.ThreadPoolExecutor(max_workers=10))
    chat_pb2_grpc.add_ChatServiceServicer_to_server(ChatService(), server)
    server.add_insecure_port('[::]:50051')
    server.start()
    print("Server listening on port 50051...")
    server.wait_for_termination()

if __name__ == '__main__':
    serve()
```

---
- [`yield`](yield) 제어자

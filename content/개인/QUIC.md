Quick UDP Internet Connection

RFC9000

### HTTP 2.0
기존의 프로토콜 데이터 체계 ⇒ 프레임과 스트림의 개념으로 재구축
핸드쉐이크 과정에서 발생하는 **지연 시간**,
패킷 유실 또는 오류에서 재전송할 때 지연
Head of Line Blocking

HTTP/3
RTT Round Trip Time을 제로 수준으로 줄였고
패킷 손실에 대한 빠른 대응,
IP가 바뀌어도 연결이 유지

TCP + TSL + HTTP

https://cloudflare-quic.com/
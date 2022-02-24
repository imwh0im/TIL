# Socket
  - 클라이언트와 서버가 특정 포트로 연결이 성립되어, 실시간으로 양방향 통신을 하는 방식
  - `HTTP` 통신은 클라이언트에서 요청이 발생했을 때, 서버에서는 데이터를 응답하고 연결이 종료되지만, Socket 통신은 연결을 종료하지 않는다. 
  - `TCP` 를 이용한 Socket 은 데이터의 순서가 보장되고, 데이터가 손실되지 않고 목적지에 전달되는 특징을 가집니다.
  - `UDP` 를 이용한 Socket 은 데이터의 순서가 보장되지 않고, 데이터가 손실되는 우려가 있지만 TCP Socket 에 비해 속도가 더 빠르다.

#### Link
  - [HTTP](/protocol/http.md)
  - [TCP](/protocol/tcp.md)
  - [UDP](/protocol/udp.md)

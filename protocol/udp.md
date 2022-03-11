# UDP
  - User Datagram Protocol 의 약자이다.
  - `TCP` 와는 반대로 비연결적이다.
  - UDP 는 통신 대상과의 연결을 확인하지 않기 떄문에, 데이터의 순서나 안정성이 보장되지 않는다.
    - 보장이 되지 않는다는 것은 그렇게 만들어졌다라기 보다는 그러한 기능들이 구현되어 있지 않은 거라고 보는 게 더 맞다고 생각된다.
    - UDP 는 오직 데이터 전송에만 초점이 맞춰져 만들어졌기 때문이라고 한다.
  - 하지만 TCP 에 비해 빠르다.
  - `HTTP` 가 `TCP/IP` 기반의 프로토콜로 알고 있었지만, 최근에 나온 `UDP/IP` 기반의 `HTTP3` 도 있다.

#### Link
  - [TCP](/protocol/tcp.md)
  - [HTTP](/protocol/http.md)
  - [TCP/IP](/protocol/tcp-ip.md)
  - [UDP/IP](/protocol/udp-ip.md)
  - [HTTP3](/protocol/http3.md)

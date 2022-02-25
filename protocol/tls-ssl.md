# TLS/SSL
  - `TLS(Transport Layer Security)` `SSL(Secure Sockets Layer)` 은 의미론적으로 같은 뜻으로 혼합해서 쓰인다. (동의어)
    - SSL 은 Secure Sockets Layer 의 약어로 보안 통신에 사용 되는 규약을 말하며, 여러 업데이트 후에 SSL3.0 은 IETF(국제 인터넷 표준 기구) 에서 표준으로 선정하여 그 기반의 TLS 가 나왔습니다.
    - 정리해서 말하자면 SSL 은 과거의 규약이고, TLS 는 현재의 규약이기때문에 두 용어는 결론적으로는 다른 보안 규약을 가르키는 용어이지만, 비학술적으로 보았을때는 실무 내에서는 같은 의미로 쓰이는 것으로 보인다.
  - 3 HandsShake 라는 인증 프로세스를 통해 해당 통신에 대한 Session Key 를 얻어와 데이터를 암호화하며, 통신을 합니다.
      - 과정
        1. client Hello
          - Client 에서 SSL/TLS 버전과 지원하는 암호화 방식, 무작위 바이트 문자열을 전송합니다. 기존에 SSL/TLS Session 이 Session Id 를 전송합니다.
        2. server Hello
          - Client 에서 지원하는 암호화 방식 중 어떤 것을 사용할 지와 세션 ID, 서버 측에서 무작위로 생성한 바이트 문자열을 전송합니다. 
          - 기존에 Session Id 를 전송 받은 경우에는 유효한지 확인 후 같은 Session Id 를 전송하여 재사용합니다.
          - 경우에 따라 Server 가 Client 로 인증서를 요청하는 경우가 있습니다. 그러한 경우에는 `2` 와 `3` 사이에 `Client Certifcate` 전송 과정이 포함될 수 있습니다.
        3. Server Certificate
          - Server 의 인증서를 Client 로 전송합니다. 경우에 따라 CA 를 전송하기도 합니다.
        4. Server Hello Done
          - `3` 이 끝나면 wjsthdgkqslek. 
        4. Client Key Exchange
          - Client 에서 브라우저를 통해 Server 에서 전송 받은 인증서가 유효한지 확인한 후 Client 의 무작위 바이트 문자와 Server 의 무작위 바이트 문자를 조합하여 `pre master secret` 라는 대칭키를 생성합니다. 그리고 인증서의 키를 통해 `pre mater secret` 를 공개키 암호화 후 서버로 전송 합니다.
        5. Server 쪽에서는 전송 받은 `pre master secret` 을 비밀키로 복호화 합니다. 이것이 `master secret` 입니다.
        6. Server 와 Client 에서는 `pre master secret` 를 이용해서 `master secret` 과 `session key` 를 만든니다.
        6. Cipher Spec Exchange
          - Server 와 Client 가 서로에게 협상된 알고리즘과 만들어진 키를 통해 통신하겠다고 알리는 과정입니다.
        7. Finished
          - Server 와 Client 가 TLS HandsShake 를 마치고 종료 합니다.
        8. 세션이 유지되어 있는 동안은 만들어진 `session key` 를 재사용해서 사용합니다.

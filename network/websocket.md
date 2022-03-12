# websocket (ing)

- 서버와 클라이언트 간에 socket connection을 유지해서 언제든 양방향 통신 또는 데이터 전송을 가능하도록 하는 기술
- real time web application 구현에 널리 사용
- stateful protocol이기 때문에 http와 tcp 연결 트래픽을 피할 수 있다.


### 기존 http
- 특징
    - request - response 구조
    - stateless
    - connectionless
- 단점
    - 서버는 클라이언트한테 응답만 할 수 있음
    - 연결 지속이 어려워 계속 인증을 해야함
    - 클라이언트에서 연결이 끊어지면 새롭게 모든 페이지를 랜더링해야함

### http + ajax
- 특징
    - 자바스크립트와 xml로 비동기 지원
    - 데이터로 xml을 사용하면서 서버와 특정 부분만을 데이터 교활할 수 있도록 함
- 단점
    - 양방향 통신 불가
    - 임시 방편
        - polling
            - 일정 주기마다 지속적으로 요청을 보내 응답을 받는다.
            - 트래픽 부하
        - long polling
            - 클라이언트가 요청을 하면 서버는 연결을 유지하고 있다가 이벤트가 발생할 때 응답을 돌려주는 방식
            - 이벤트가 한번 일어나면 트래픽이 치솟는다.
            - 이벤트가 많으면 결국엔 polling과 동일
        - streaming
            - 연결을 계속 지속시킨다.
            - 보안, 효율 방면에서 좋지 않다.
            - 클라이언트에서 서버로 데이터 송신이 어렵다.

### websocket
- ip와 port(80)으로 통신
- upgrade 헤더를 통해 웹 서버에 요청





# Observer Pattern

옵저버 : 객체의 상태 변화를 관찰하는 관찰자
옵저버 패턴 : 옵저버들의 목록을 객체에 등록하여 상태 변화가 있을 때마다 메서드 등을 통해 객체가 직접 목록의 각 옵저버에게 통지하도록 하는 디자인 패턴, 주로 분산 이벤트 핸들링을 구현하는데 사용됨.

어떤 객체의 상태가 변할 때 그와 연관된 객체들에게 알림을 보내는 디자인 패턴

옵저버 패턴(Observer Pattern)에서는 한 객체의 상태가 바뀌면 그 객체에 의존하는 다른 객체들한테 연락이 가고, 자동으로 내용이 갱신되는 방식으로 일대다(one-to-many) 의존성을 정의한다.

옵저버 패턴은 주제와 옵저버가 느슨하게 결합되어있는 객체 디자인 제공

느슨한 결합의 장점은 다음과 같습니다.

1. 옵저버를 언제든 새로 추가, 제거할 수 있다.
2. 새로운 형식의 옵저버라 할 지라도 주제를 전혀 변경할 필요가 없다.
3. 주제와 옵저버는 서로 독립적으로 재사용 할 수 있다.
4. 주제나 옵저버가 바뀌더라도 서로에게 영향을 미치지 않는다.


### JAVA 에서의 Observer Pattern

**내부 메서드는 링크 통해 확인**

Observable class : https://docs.oracle.com/javase/8/docs/api/index.html?java/util/Observable.html

Observer interface : https://docs.oracle.com/javase/8/docs/api/index.html?java/util/Observer.html

이름만 보고 당연히 Observable이 인터페이스인 줄 알았다..
Observer가 인터페이스고 Observable은 클래스다.

[블로그 (출처)](https://velog.io/@hanna2100/%EB%94%94%EC%9E%90%EC%9D%B8%ED%8C%A8%ED%84%B4-2.-%EC%98%B5%EC%A0%80%EB%B2%84-%ED%8C%A8%ED%84%B4-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%98%88%EC%A0%9C-observer-pattern) 에서 말하는 java 내장 옵저버의 단점


1. Observable은 클래스이다

    인터페이스가 아니기 때문에 주제로 할 객체를 서브클래스로 만들 수 밖에 없습니다. 만약 이미 다른 수퍼클래스가 있다면 사용을 할 수 없는 것이죠. 인터페이스가 없다는 것은 해당 라이브러리를 커스텀하여 사용할 수 없다는 점도 있습니다.
2. Observable API는 Protected로 선언되었다

    setChanged() 메소드를 보면 Protected 선언이 되어있습니다. 즉 Observable의 서브클래스에서만 setChanged()를 호출할 수 있죠. 즉 Observable를 구현한 주제객체를 다른 패키지에서 인스턴스변수로 써먹을 수 없습니다. 이런 디자인은 상속보다는 구성을 사용한다는 디자인 원칙에도 위배됩니다.

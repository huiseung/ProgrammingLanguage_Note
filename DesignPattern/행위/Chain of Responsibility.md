- 다수의 분기 조건문을 없애고 싶을 때 사용
- 요청을 처리할 수 있을 만한 객체들을 연쇄적으로 연결해 둔 다
- 순차적으로 각 객체들은 자신이 처리할 수 있는지 확인후 처리 후 종료, 없다면 다음으로 넘긴다


## exmplae code

```java
interface RequestHandler {
    void setNext(RequestHandler handler);
    void handle(String request);
}

```


```java

    // 체인 구성
    RequestHandler auth = new AuthHandler();
    RequestHandler logger = new LogHandler();
    RequestHandler data = new DataHandler();
    auth.setNext(logger);
    logger.setNext(data);

    // 다양한 요청 테스트
    auth.handle("auth");
    auth.handle("log");
    auth.handle("data");
    auth.handle("unknown");


```

## spring example
- Filter Chain
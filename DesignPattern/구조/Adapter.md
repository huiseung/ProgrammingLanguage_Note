
## example

```java
// 변경 불가 코드
// 외부 클래스 또는 레거시 시스템
@Bean
public class LegacyPaymentGateway {
    public void process(String customerId, int cents) {
        System.out.println("Legacy 결제 처리: " + cents + " cents, 고객: " + customerId);
    }
}

```


```java
// 우리가 사용하려는 인터페이스
public interface PaymentService {
    void pay(String userId, double amount);
}

```


```java
@Service
public class LegacyPaymentAdapter implements PaymentService {
    private final LegacyPaymentGateway legacyPaymentGateway;

    public LegacyPaymentAdapter() {
        this.legacyPaymentGateway = new LegacyPaymentGateway();
    }

    @Override
    public void pay(String userId, double amount) {
        int cents = (int) (amount * 100);
        legacyPaymentGateway.process(userId, cents);
    }
}
```
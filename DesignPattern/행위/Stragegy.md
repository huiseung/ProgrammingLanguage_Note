- 분기처리에서 동작하는 작업을 클래스로 분리해 런타임 상황에서 어떤 클래스를 사용할지 교체

```java
interface PaymentStrategy {
    void pay(int amount);
}

class CardPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("신용카드로 " + amount + "원 결제");
    }
}

class PayPalPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("PayPal로 " + amount + "원 결제");
    }
}
```

```java
class ShoppingCart {
    private PaymentStrategy strategy;

    // 전략 변경
    public void setStrategy(PaymentStrategy strategy) {
        this.strategy = strategy;
    }

    // 전략 사용
    public void checkout(int amount) {
        strategy.pay(amount);
    }
}
```

```java
ShoppingCart cart = new ShoppingCart();
cart.setStrategy(new CardPayment());
cart.checkout(5000);

cart.setStrategy(new PayPalPayment());
cart.checkout(10000);

```
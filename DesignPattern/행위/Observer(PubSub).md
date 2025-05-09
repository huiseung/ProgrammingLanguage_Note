- 피관찰자가 발행한 이벤트를 다양한 형태의 관찰자가 각자의 책임에 맞춰 처리
- 피관찰자에게 발행 이벤트를 처리할 관찰자 등록
- 피관찰자: Subject, Publisher, Producer, EventEmitter
- 관찰자: Observer, Subscriber, Consumer, EventListener

```java
class Publisher{
    private List<Subscriber> subscribers = new ArrayList<>();

    // 자신을 관찰할 관찰자 등록
    public void subscribe(Subscriber s){
        this.subscribers.add(s);
    }

    // 관찰자에게 메세지 전달
    public void notifyAll(String msg){
        for(Subscriber s : subscribers){
            s.update(msg);
        }
    }
}
```


```java
interface Subscriber{
    void update(String message);
}

class EmailSubscriber implements Subscriber{
    public void update(String message){}
}

class SmsSubscriber implments Subscriber{

}
```
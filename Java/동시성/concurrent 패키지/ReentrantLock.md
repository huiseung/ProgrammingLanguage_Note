# synchronized 단점
- blocked 상태 스레드는 잠금을 얻을 때 까지 대기한다
- blocked 상태에 스레드 중 어떤 스레드가 잠금을 획득할 지 알 수 없다, 최악의 경우 장기 blocked 스레드 발생할 수 있다

# ReentrantLock
- Lock 인턴페이스 구현체
- AbstractQueuedSynchronizer 이용해 락 상태, 대기 큐 관리
- LockSupport 를 이용해 실제 스레드 정지및 재개 수행



# LockSupport
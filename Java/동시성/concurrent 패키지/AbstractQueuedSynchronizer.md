- synchronize 키워드 사용하지 않고 CAS 연산, volatile 변수를 이용해 동기화 구현
- ReentrantLock, Semaphore, CoutDownLatch, FutureTask에서 사용

## 필드
- state: int

## 메서드
- compareAndSetState()
- acquire()
- release()
- tryAcquire()
- tryRelease()

## inner class
- Node
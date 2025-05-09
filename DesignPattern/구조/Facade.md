- 여러 클래스의 메서드 사용을 하나의 클래스 메서드로 묶음

```java
// 쓰고 싶은 메서드들
class CPU {
    public void start() { System.out.println("CPU 시작"); }
}

class Memory {
    public void load() { System.out.println("메모리 로드"); }
}

class HardDrive {
    public void read() { System.out.println("하드디스크 읽기"); }
}
```

```java
class ComputerFacade {
    private CPU cpu;
    private Memory memory;
    private HardDrive hdd;

    public ComputerFacade() {
        cpu = new CPU();
        memory = new Memory();
        hdd = new HardDrive();
    }

    //
    public void startComputer() {
        cpu.start();
        memory.load();
        hdd.read();
        System.out.println("컴퓨터 부팅 완료");
    }
}

```
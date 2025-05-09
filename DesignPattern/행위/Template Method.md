- 하위 클래스가 상위 클래스의 메서드 동작 일부를 재정의
  - 공통 로직 고정, 세부 로직 유연하게 수정

## example
```java
abstract class ReportGenerator {
    // 템플릿 메서드
    public final void generateReport() {
        fetchData();
        processData();
        formatReport();
        printReport();
    }

    // 하위 클래스에서 구현할 부분
    protected abstract void fetchData();
    protected abstract void processData();

    // 공통 로직 (변경하지 않음)
    protected void formatReport() {
        System.out.println("[공통] 보고서 포맷팅");
    }

    protected void printReport() {
        System.out.println("[공통] 보고서 출력 완료");
    }
}
```

```java
// 구체화
class SalesReportGenerator extends ReportGenerator {
    protected void fetchData() {
    }

    protected void processData() {
    }
}

class InventoryReportGenerator extends ReportGenerator {
    protected void fetchData() {
    }

    protected void processData() {
    }
}
```
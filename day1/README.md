# 자바 시작하기
자바 프로그래밍을 공부하는 이유?
- 기업에서 서버 프로그래밍시 가장 많이 사용하는 언어
### 자바 언어의 특징
- 객체지향 언어
- 자바 언어는 느리지만, 버전업되면서 다른 언어들의 장점을 흡수하고 있다. (모던 자바)
    - 람다(Lambda): 함수형 프로그래밍
    - Stream API: 라다 표현식과 메서드 참조 등의 기능과 결합해서 매우 복잡하고 어려운 데이터 처리 작업을 쉽게 조회하고 필터링하고 변환하고 처리할 수 있도록 한다.
    - 병렬 프로그래밍: 여러개의 CPU 코어에서 작업을 배분해서 동시에 작업을 수행한다.
### 자바 프로그램 작성과 실행
- JDK(Java Development Kit)이라는 프로그램을 다운로드하고 설치해야 한다.
- 여러 종류의 JDK가 존재한다. OpenJDK, Oracle JDK, Azul Julu JDK, Amazon Corretto OpenJDK, Adoptium Temurin 등
- 이클립스 재단(The Eclipse Foundation)의 어댑티움(Adoptium) 프로젝트가 '이클립스 테무린(Ecplipse Temurin) 자바 SE 바이너리'의 첫 번째 릴리즈를 출시했다. 이는 인텔 64비트 프로세서 기반 윈도우, 리눅스, 맥 OS용 자바 SE8, 자바 SE11, 자바 SE16의 최신 버전을 다루는 오픈JDK(OpenJDK)의 '프로덕션 레디(production-ready)' 빌드다.

JDK 설치 후 JAVA_HOME 및 PATH 환경변수를 설정한다.

Visual Studio Code를 실행한 후 Hello.java 파일을 생성하여 아래와 같이 작성한다.
```java
public class Hello {
  public static void main(String[] args){
    System.out.println("Hello!");
  }
}
```
파일명과 public class 뒤에 나오는 것이 꼭 같아야한다.
### 자바 프로그램 작성과 실행
- java 컴파일러 javac 명령으로 Hello.java를 컴파일 한다.
`javac Hello.java`
- 컴파일이 성공하면 오류메시지가 없이 `Hello.class` 파일이 생성된다.
- `ls -la` 명령으로 파일이 생성되었는지 확인한다.
- JVM(자바 가상 머신)으로 `Hello.class`를 실행한다. java 명령이 JVM을 의미한다. 이 때 확장자는 입력하지 않는다.
`java Hello`
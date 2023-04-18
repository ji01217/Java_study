# IntelliJ를 이용한 자바프로그래밍

### IDE?

- IDE: 통합 개발 환경(Integrated Development Environment, IDE)은 코딩, 디버그, 컴파일, 배포 등 프로그램 개발에 관련된 모든 작업을 하나의 프로그램 안에서 처리하는 환경을 제공하는 소프트웨어이다.
- 대표적인 Java 언어를 위한 IDE: Eclipse, IntelliJ

## IntelliJ

- Jetbrains사에서 만든 IDE.
- 무료 버전인 Community 버전과 유료 버전인 Ultimate 버전으로 나뉜다.
- 자바 언어를 공부할 때는 둘 중 무엇이든 상관없다.

### 프로젝트 생성하기

- IDEA에서 프로그램 개발을 시작하려면 가장 먼저 해야할 일은 프로젝트를 생성하는 것이다. "New Project" 버튼을 클릭한다.
- 라이브러리와 프레임워크를 선택하게 되어있는데 아무것도 선택하지 않고, 우측 하단의 "Next" 버튼을 클릭한다.

### 한글 메뉴 사용하기

- 프로젝트를 열면 창이 열리고 우측 하단에 IntelliJ를 로컬라이즈화하여 사용할 것이냐는 작은 창이 보인다. 확인을 누르면 IntelliJ가 다시 열리면서 메뉴 등이 한글로 표시된다. 영어로 사용하길 원한다면 창을 그냥 닫도록 한다.

### IntelliJ IDE에서 만든 프로젝트 구조

- 프로젝트 폴더 아래의 .idea 폴더는 IntelliJ에서 프로젝트를 관리하기 위한 파일이다. 직접 수정하거나 삭제하면 안된다.
- HappyJava.iml 파일은 IntelliJ의 설정 파일이다. 직접 수정하거나 삭제하면 안된다.
- 사용자는 src 폴더에 Java 소스코드를 작성하게 된다.
  ![폴더구조](https://velog.velcdn.com/images/ji01217/post/97fabc81-5d62-47b3-a246-d87c69becad8/image.png)

### Hello.java 클래스를 작성한다.

1. src 폴더를 선택하고 마우스 우측버튼을 클릭힌다.
2. 새로 만들기를 클릭한다.
3. Java 클래스를 선택한다.
4. 창이 열리면 클래스를 선택한다.
5. Hello라고 클래스 이름을 입력한다. 이때 .java는 작성하지 않는다. 엔터를 입력한다.
6. src 폴더에 Hello 클래스가 작성된 것을 알 수 있다. 파일 탐색기로 가보면 Hello.java 파일이 생성된 것을 알 수 있다.

### Hello.java 클래스를 다음과 같이 수정한다.

```java
public class Hello {
	public static void main(String[] args) {
    	System.out.println("Hello IntelliJ IDEA");
    }
}
```

### Hello 클래스 실행하기

1. Hello 클래스를 선택하고, 우측 버튼을 클릭한다.
2. 실행 'Hello.main()'을 선택한다.
3. IntelliJ IDEA의 화면 아래쪽에 Hello 클래스를 java 명령으로 실행한 결과가 출력된다.
4. IntelliJ는 자동으로 컴파일하고 실행을 하게 된다. 파일을 수정했을 때 컴파일 되는 것은 아니다.

### 프로젝트 구조

- HappyJava 프로젝트 폴더 아래에 out 폴더가 생성되고 그 아래에 또 몇가지 폴더가 생성된 후, Hello.class 파일이 생성된 것을 알 수 있다. IntelliJ가 Hello 클래스를 실행하면 아래의 경로에 컴파일한 결과물을 생성하고, 해당 클래스를 실행하게 된다.

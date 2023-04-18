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

### 이름, 이메일, 성별 출력하기

1. 다음과 같은 MyProfile 클래스를 작성한다.

```java
public class MyProfile {
	public static void main (String[] args) {
    	System.out.println("김지영");
        System.out.println("~~@naver.com");
        System.out.println("여자");
    }
}
```

2. 실행한다.

```
김지영
~~@naver.com
여자
```

### main() 메소드 안의 내용은 차례대로 실행된다.

- main() 메소드 안의 내용이 한줄씩 한줄씩 실행된다.
- System.out.println("김지영");
  - 위의 코드는 "김지영"이라는 이름을 출력한다.
    - 그리고 줄바꿈을 하게 된다. 그렇기 때문에 다음 줄에 이메일이 출력된다.

### println() 메소드를 print()로 바꿔보기

```java
public class MyProfile {
	public static void main (String[] args) {
    	System.out.print("김지영");
        System.out.print("~~@naver.com");
        System.out.print("여자");
    }
}
```

- 위와 같이 코드를 수정한 후 실행한 결과는 다음과 같다.
  `김지영~~@naver.com여자`

### print() 메소드는 줄바꿈을 하지 않는다.

- println() 메소드는 괄호 안의 내용을 출력하고 줄바꿈을 하지만, print() 메소드는 괄호 안의 내용만 출력한다. 줄바꿈을 하지 않는다.
- `System.out.println();`는 아무것도 출력하지 않고 줄바꿈만 한다.

### 연습

- 다음과 같은 결과를 출력하는 Rectangle 클래스를 작성한다. (너비가 별 10개, 높이가 별 10개인 사각형)

```
**********
**********
**********
**********
**********
**********
**********
**********
**********
**********
```

```java
public class Practice {
    public static void main (String[] args) {
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
        System.out.println("**********");
    }
}
```

### 높이가 200인 사각형을 출력하려면?

- 만약 높이가 10,000인 사각형을 출력하라고 문제가 바뀐다면?
- 컴퓨터가 가장 잘하는 일은 반복하는 일이다.

### while 반복문을 이용해 높이가 10인 사각형 출력하기

- 다음과 같이 Rectangle2 클래스를 작성한다.

```java
public class Rectangle2 {
	public static void main (String[] args) {
    	int i = 1;
        while(i <= 10) {
        	System.out.println("**********");
            i = i + 1;
        }
    }
}
```

### while 반복문

- main 메소드 안의 내용은 한줄씩 실행해 나간다. JVM이 한줄씩 읽어나가면서 해석하고 실행한다.
- 정수 타입(type) 변수 i에 1을 저장한다. 자바 프로그래밍에서 =는 `같다.`라는 의미가 아니라, 우측의 값을 좌측에 저장한다는 의미이다.
  `int i = 1`
- while(i <= 10)은 i가 10보다 작거나 같을 때까지 중괄호 안의 내용을 반복하라는 의미이다. 이 부분을 while 블록(block)이라고 읽는다. 중괄호 부분을 블록이라고 한다. 즉, i가 10보다 크다면 반복하지 말라는 이야기이다.
- 괄호 안의 `i = i + 1`은 i에 저장된 값에 1을 더한 후 다시 i에 저장하라는 뜻이다.

```java
while (i <= 10) {
	...
    i = i + 1;
}
```

- 즉 아래의 코드는 i는 1부터 시작해서 while 블록 안의 내용을 반복할 때마다 i를 1씩 증가시키라는 의미이다.
- 이 때 i가 10보다 작거나 같을 경우는 계속 반복하게 된다. 어느 시점에 i가 11이 되는 경우가 발생하는데, 이 때는 while 블록을 종료하게 되고, 그 다음 줄을 실행하게 된다.

```java
int i = 1;
while(i <= 10){
	System.out.println("**********");
    i = i + 1;
}
```

### 연습

- 높이가 1000인 사각형을 출력하자.

```java
public class Practice {
    public static void main (String[] args) {
        int i = 1;
        while (i <= 1000) {
            System.out.println("**********");
            i = i + 1;
        }
    }
}
```

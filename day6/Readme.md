# 정수, 실수, 산술연산자

### 정수형 타입 byte, short, int, long

- byte: 1byte
- short: 2byte
- int: 4byte
- long: 8byte
- 리터럴 값인 숫자 5는 int 타입이다.
- 리터럴 값인 숫자 5L은 long 타입이다. (숫자 뒤에 L 또는 l이 붙는다.)

### 실수형 타입 float, double

- float: 4byte
- double: 8byte
- 리터럴 값인 숫자 5.2는 double 타입이다.
- 리터럴 값인 숫자 5.2f는 float 타입이다. (숫자 뒤에 F 또는 f가 붙는다.)

### 산술 연산자

- 정수와 실수는 덧셈(+), 뺄셈(-), 곱셈(\*), 나눗셈(/), 나머지구하기(%)를 할 수 있다.
- 정수를 정수로 나누면 잘림 현상이 발생한다. (ex. d = 5 / 2 => 2)
- 나머지 연산자는 앞의 숫자를 나누고 나눈 나머지 값을 구한다.

### 증가 연산자와 감소 연산자

- 증가 연산자(++)를 사용하면 1이 증가된다.
- 감소 연산자(--)를 사용하면 1이 감소된다.
- 증가 연산자와 감소 연산자는 변수의 앞에 붙으면 전위 증가 연산자와 전위 감소 연산자라 부르고, 변수의 뒤에 붙으면 후위 증가 연산자와 후위 감소 연산자라 말한다.
  `++a, a++, --a, a--`
- a++은 `a = a + 1`과 같은 뜻이다.
- b--는 `b = b - 1`과 같은 뜻이다.

### 산술 대입 연산자

- 산술 대입 연산자는 +=, -=, \*=, /=, %=가 있다.

```
a = 5;
a += 3;

b = 4;
b -= 2;

c = 8;
c *= 2;

d = 4;
d /= 2;

e = 5;
e %= 2;
```

- `a += 3`은 `a = a + 3`을 줄인 식이다. a는 8이 된다.
- `b -= 2`는 `b = b - 2`를 줄인 식이다. b는 2가 된다.

### 괄호 ()

- 괄호가 있을 경우 괄호 안의 내용부터 계산한다.

```
a = 3;
b = 5;

c = a * (b + 5);
d = a * b + 5;
```

c = 30, d = 20

### 정수와 실수의 최솟값, 최댓값

- int와 double이 가지는 최솟값과 최댓값을 출력한다.

```java
public class NumberExam01 {
    public static void main(String[] args) {
        int maxInt = Integer.MAX_VALUE;
        int minInt = Integer.MIN_VALUE;

        double maxDouble = Double.MAX_VALUE;
        double minDouble = Double.MIN_VALUE;

        System.out.println(maxInt);
        System.out.println(minInt);

        System.out.println(maxDouble);
        System.out.println(minDouble);
    }
}
```

### 오버플로우(overflow)

- 아래의 프로그램은 결과가 얼마나 나올까?
- 계산 결과가 최댓값을 넘거나, 최솟값보다 작을 경우 음수는 양수로, 양수는 음수로 바뀌는 문제가 발생한다. 이를 오버플로우라고 한다.

```java
public class NumberOverflow {
    public static void main(String[] args) {
        int value = 10;
        int maxInt = Integer.MAX_VALUE;

        System.out.println(value + 1);
        System.out.println(maxInt + 1);
    }
}
```

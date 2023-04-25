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

# 타입의 변환

### double형 타입은 정수값이 잘 대입된다.

```java
double d1 = 50;
double d2 = 500L;
```

- 이를 묵시적 타입 변환(자동 타입 변환, implicit conversion)이라고 한다.
- int형 리터럴 50, long형 리터럴 500L이 모두 d1, d2에 저장된다.

### int형 타입에 실수를 대입하면 오류가 발생한다.

```java
int i1 = 50.0;
int i2 = 25.4f;
```

- 실수는 정수를 포함하지만, 정수는 실수를 포함할 수 없기 때문에 아래의 코드는 컴파일 오류가 발생한다.

### 실수 값을 정수에 저장하려면 형변환을 해야한다.

```java
int i1 = (int) 50.0;
int i2 = (int) 25.6f;
```

- 실수 값을 정수타입의 변수에 저장하려면 정수타입으로 형변환 해야한다. 변환하고자 하는 값 앞에 (int)를 붙인다.
- 주의해야할 점은 소수점 이하 부분은 잘린다.
- 이를 명시적 타입 변환(강제 타입 변환, explicit conversion)이라고 한다.

### 크기가 큰 타입은 작은 타입을 저장할 수 있다.

```java
short s = 5;
int i = s;
long x = i;
```

- long 타입의 변수는 byte, short, int 타입의 값을 저장할 수 있다.
- int 타입의 변수는 byte, short 타입의 값을 저장할 수 있다.
- short 타입의 변수는 byte 타입의 값을 저장할 수 있다.

### 형변환시 주의할 점

- 크기가 큰 타입을 작은 타입에 저장할 때에는 오버플로우를 조심해야 한다.

# 문자(char)타입

### 문자타입

- 문자는 작은 따옴표로 묶인 문자 하나를 말한다.
- 문자는 2byte 크기를 가지며 유니코드 값을 가진다.

### 문자타입은 정수타입이기도 하다.

- 문자타입은 0부터 65535까지 저장할 수 있는 정수 타입이기도 하다.

### 문자를 정수형으로, 정수를 문자로 변환

- 유니코드 97번째 값은 문자 'a'이다.

```java
public class CharExam2 {
    public static void main(String[] args) {
        char c1 = 'a';
        System.out.println((int) c1);
        char c2 = (char) 97;
        System.out.println(c2);
    }
}
```

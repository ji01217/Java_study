**컬렉션 프레임웍**이란?

- 데이터 군을 저장하는 클래스들을 표준화한 설계
- **컬렉션(Collection)**은 다수의 데이터(데이터 그룹), **프레임웍**은 표준화된 프로그래밍 방식을 의미
- 컬렉션, 다수의 데이터를 다루는 데 필요한 **다양하고 풍부한 클래스들을 제공**하고, 인터페이스와 다형성을 이용한 **객체지향적 설계**를 통해 **표준화**되어 있기 때문에 사용법을 익히기에 편리하고
  재사용성이 높은 코드를 작성할 수 있다.

## 1. 컬렉션 프레임웍의 핵심 인터페이스

컬렉션 데이터 그룹을 크게 3가지 타입으로 나누고 각 컬렉션을 다루는데 필요한 기능을 가진 **3개의 인터페이스**를 정의
인터페이스 **List**와 **Set**의 공통된 부분을 다시 뽑아서 **새로운 인터페이스**인 ** Collection**을 추가로 정의

- 컬렉션 프레임웍의 핵심 인터페이스간의 상속계층도
  ![컬렉션 프레임웍의 핵심 인터페이스간의 상속계층도](https://velog.velcdn.com/images/ji01217/post/9c431d42-3b9e-4393-929b-3d852e3aa44c/image.png)
- 컬렉션 프레임웍의 핵심 인터페이스와 특징
  ![컬렉션 프레임웍의 핵심 인터페이스와 특징](https://velog.velcdn.com/images/ji01217/post/e84e3004-8aff-43d5-afc2-addf975e7486/image.png)
- 컬렉션 프레임웍의 모든 컬렉션 클래스들은 List, Set, Map 중의 하나를 구현하고 있다.

### Collection 인터페이스

- Collection 인터페이스에 정의된 메서드
  ![Collection인터페이스에 정의된 메서드](https://velog.velcdn.com/images/ji01217/post/595949c7-a1f8-453a-880d-84890cd311eb/image.png)

### List 인터페이스

List 인터페이스는 **중복을 허용**하면서 **저장순서가 유지**되는 컬렉션을 구현하는데 사용된다.

- List의 상속계층도
  ![List의 상속계층도](https://velog.velcdn.com/images/ji01217/post/d8222e03-dad4-4039-afd6-4276930cf4df/image.png)
- List 인터페이스의 메서드
  ![List 인터페이스의 메서드](https://velog.velcdn.com/images/ji01217/post/6c4ab802-28d6-43a9-bbc4-db2c1dd6119c/image.png)

### Set 인터페이스

Set 인터페이스는 중복을 허용하지 않고 저장순서가 유지되지 않는 컬렉션 클래스를 구현하는데 사용된다. Set 인터페이스를 구현한 클래스로는 HashSet, TreeSet 등이 있다.

- Set의 상속계층도
  ![Set의 상속계층도](https://velog.velcdn.com/images/ji01217/post/cf56981c-4709-452f-9c18-40fd7f8817c3/image.png)

### Map 인터페이스

Map 인터페이스는 키(key)와 값(value)을 하나의 쌍으로 묶어서 저장하는 컬렉션 클래스를 구현하는 데 사용된다. 키는 중복될 수 없지만 값은 중복을 허용한다.

- Map의 상속계층도
  ![Map의 상속계층도](https://velog.velcdn.com/images/ji01217/post/fc3b0903-f5d8-4106-ac5c-e4ba7feb1169/image.png)
- Map 인터페이스의 메서드
  ![Map 인터페이스의 메서드](https://velog.velcdn.com/images/ji01217/post/bc8b275c-66f5-4365-8db1-e18eecfef677/image.png)
  Map 인터페이스에서 값(value)은 중복을 허용하기 때문에 `values()`의 반환타입은 `Collection`이고, 키(key)는 중복을 허용하지 않기 때문에 `keySet()`의 반환타입은 `Set`
  이다.

### Map.Entry 인터페이스

Map.Entry 인터페이스는 Map 인터페이스의 내부 인터페이스로, Map에 저장되는 key-value쌍을 다루기 위해 내부적으로 Entry 인터페이스를 정의한 것이다. Map 인터페이스를 구현하는 클래스에서는
Map.Entry 인터페이스도 함께 구현해야 한다.

```java
public interface Map {
	...

    interface Entry {
        Object getKey();

        Object getValue();

        Object setValue(Object value);

        boolean equals(Object o);

        int hashCode();
        ...
    }
}
```

- Map.Entry 인터페이스의 메서드
  ![Map.Entry 인터페이스의 메서드](https://velog.velcdn.com/images/ji01217/post/1c0bfe10-b7a8-4fc9-9188-5c0444a66ac6/image.png)

## 2. ArrayList

- 컬렉션 프레임웍에서 가장 많이 사용되는 컬렉션 클래스
- List 인터페이스를 구현하기 때문에 데이터의 저장순서가 유지되고 중복을 허용한다.
- Object 배열을 이용해서 데이터를 **순차적**으로 저장한다.

```java
public class ArrayList extends AbstractList implements List, RandomAccess, Cloneable, java.io.Serializable {
	...
    transient Object[] elementData; // Object 배열
    ...
}
```

- ArrayList의 생성자와 메서드
  ![ArrayList의 생성자와 메서드](https://velog.velcdn.com/images/ji01217/post/b9bbe87c-d6c2-4c6c-8c41-4cf6046d98c5/image.png)
- ArrayList 예제1
  ArrayList의 메서드 사용하기

```java
import java.util.*;

class ArrayListEx1 {
    public static void main(String[] args) {
        ArrayList list1 = new ArrayList(10);
        list1.add(new Integer(5));
        list1.add(new Integer(4));
        list1.add(new Integer(2));
        list1.add(new Integer(0));
        list1.add(new Integer(1));
        list1.add(new Integer(3));

        ArrayList list2 = new ArrayList(list1.subList(1, 4));
        print(list1, list2);

        Collections.sort(list1); // list1과 list2를 정렬한다.
        Collections.sort(list2); // Collections.sort(List l)
        print(list1, list2);

        System.out.println("list1.containsAll(list2): " + list1.containsAll(list2));

        list2.add("B");
        list2.add("C");
        list2.add(3, "A");
        print(list1, list2);

        list2.set(3, "AA");
        print(list1, list2);

        // list1에서 list2와 겹치는 부분만 남기고 나머지는 삭제한다.
        System.out.println("list1.retainAll(list2): " + list1.retainAll(list2));
        print(list1, list2);

        // list2에서 list1에 포함된 객체들을 삭제한다.
        for (int i = list2.size() - 1; i >= 0; i--) {
            if (list1.contains(list2.get(i)))
                list2.remove(i);
        }
        print(list1, list2);
    } // main의 끝

    static void print(ArrayList list1, ArrayList list2) {
        System.out.println("list1: " + list1);
        System.out.println("list2: " + list2);
        System.out.println();
    }
} // class
```

- ArrayList 예제2
  문자열 데이터를 원하는 길이로 잘라서 ArrayList에 담은 후 출력하기

```java
import java.util.*;

class ArrayListEx2 {
    public static void main(String[] args) {
        final int LIMIT = 10; // 자르고자 하는 글자의 개수를 지정한다.
        String source = "0123456789abcdefghijABCDEFGHIJ!@#$%^&*()zzz";
        int length = source.length();

        List list = new ArrayList(length / LIMIT + 10); // 크기를 약간 여유있게 잡는다.

        for (int i = 0; i < length; i += LIMIT) {
            if (i + LIMIT < length)
                list.add(source.substring(i, i + LIMIT));
            else
                list.add(source.substring(i));
        }

        for (int i = 0; i < list.size(); i++) {
            System.out.println(list.get(i));
        }
    } // main()
}
```

- Vector 예제1
  Vector의 용량과 크기

```java
import java.util.*;

class VectorEx1 {
    public static void main(String[] args) {
        Vector v = new Vector(5); // 용량(capacity)이 5인 Vector를 생성한다.
        v.add("1");
        v.add("2");
        v.add("3");
        print(v);

        v.trimToSize(); // 빈 공간을 없앤다. (용량과 크기가 같아진다.)
        System.out.println("=== After trimToSize() ===");
        print(v);

        v.ensureCapacity(6);
        System.out.println("=== After ensureCapacity(6) ===");
        print(v);

        v.setSize(7);
        System.out.println("=== After setSize(7) ===");
        print(v);

        v.clear();
        System.out.println("=== After clear() ===");
        print(v);
    }

    public static void print(Vector v) {
        System.out.println(v);
        System.out.println("size: " + v.size());
        System.out.println("capacity: " + v.capacity());
    }
}
```

- 실행결과

```
 [1, 2, 3]
size: 3
capacity: 5
=== After trimToSize() ===
[1, 2, 3]
size: 3
capacity: 3
=== After ensureCapacity(6) ===
[1, 2, 3]
size: 3
capacity: 6
=== After setSize(7) ===
[1, 2, 3, null, null, null, null]
size: 7
capacity: 12
=== After clear() ===
[]
size: 0
capacity: 12
```

- 실행과정

1. capacity가 5인 Vector 인스턴스 v를 생성하고, 3개의 객체를 저장한다.
2. v.trimToSize()를 호출하면 v의 빈 공간을 없애서 size와 capacity를 같게 한다. 배열은 크기를 변경할 수 없기 때문에 새로운 배열을 생성해서 그 주소값을 변수 v에 할당한다. 기존의
   Vector 인스턴스는 더 이상 사용할 수 없으며, 후에 가비지컬렉터(garbage collector)에 의해서 메모리에서 제거된다.
3. v.ensureCapacity(6)은 v의 capacity가 최소한 6이 되도록 한다. 만일 v의 capacity가 6이상이라면 아무 일도 일어나지 않는다. 현재는 v의 capacity가 3이므로 크기가 6인
   배열을 생성해서 v의 내용을 복사한다. 기존의 인스턴스를 다시 사용하는 것이 아니라 새로운 인스턴스를 생성한다.
4. v.setSize(7)는 v의 size가 7이 되도록 한다. 만일 v의 capacity가 충분하면 새로 인스턴스를 생성하지 않아도 되지만 지금은 capacity가 6이므로 새로운 인스턴스를 생성해야한다.
   Vector는 capacity가 부족할 경우 자동적으로 기존의 크기보다 2배의 크기로 증가된다. 그래서 v의 capacity는 12가 된다.
5. v.clear()는 v의 모든 요소를 삭제한다.

- ArrayList나 Vector 같이 배열을 이용한 자료구조는 데이터를 읽어오고 저장하는 데는 효율이 좋지만, 용량을 변경해야할 때는 새로운 배열을 생성한 후 기존의 배열로부터 새로 생성된 배열로 데이터를
  복사해야하기 때문에 상당히 효율이 떨어진다.

## 3. LinkedList

- 배열은 구조가 간단하며 사용하기 쉽고 데이터를 읽어오는데 걸리는 시간(접근시간, access time)이 가장 빠르다.
- 그러나 크기를 변경할 수 없고, 비순차적인 데이터의 추가 또는 삭제에 시간이 많이 걸린다는 단점이 있다.
- 링크드 리스트(Linked list)는 이러한 배열의 단점을 보완하기 위해 모든 데이터가 연속적으로 존재하는 배열과 달리 **불연속적으로 존재하는 데이터를 서로 연결(link)한 형태**로 구성되어 있다.
- 배열과 링크드 리스트
  ![배열과 링크드 리스트](https://velog.velcdn.com/images/ji01217/post/a24c11e2-4e37-4246-8ba5-48a747660f3c/image.png)
- 링크드 리스트의 각 요소(node)들은 자신과 연결된 
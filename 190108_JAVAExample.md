과제
===

과제1
---

- ArrayList 2개를 만든다.
- 첫번째 ArrayList 에는 0~9까지 값을 넣는다 (반복문사용)
- 두번째 ArrayList 에는 첫번째 ArrayList 의 값을 하나씩 확인하여 5보다 작으면 true, 그렇지않으면 false를 넣는다 (반복문사용)

```java
public  static void main(String[] args) {

    ArrayList<Integer> ArrayList1 = new ArrayList<>();
    ArrayList<Boolean> ArrayList2 = new ArrayList<>();

    for(int i = 0; i <= 9; i++) {
        ArrayList1.add(i);
    }

    for(int i = 0; i < ArrayList1.size(); i++) {

        if(ArrayList1.get(i) < 5) {
            ArrayList2.add(true);
        } else {
            ArrayList2.add(false);
        }
    }

    System.out.println(ArrayList1);
    System.out.println(ArrayList2);

}
```

- `ArrayList<Integer>` 로 배열의 타입을 숫자로 지정
- `ArrayList<Boolean>` 로 배열의 타입을 `boolean` 으로 지정
- for 문을 돌면서 0~9까지 추가되도록 `ArrayList1.add(i)`
- 생성된 배열의 값만큼 for 반복을 돌리고 `ArrayList1.size()`
- 내부에서는 비교연산자로 비교 결과에 따른 if 문 수행

과제2
---

- 0~9 까지 들어있는 배열을 만든다.
- 배열안에있는 홀수의 갯수를 리턴하는 함수를 만든다.


```java
public class Method {

    public  static void main(String[] args) {

        ArrayList<Integer> list = new ArrayList<>();
        for(int i = 0; i < 10; i++) {
            list.add(i);
        }
        System.out.println(howManyOdds(list));
    }

    public static int howManyOdds(ArrayList<Integer> list) {
        int result = 0;
        for(int i = 0; i < list.size(); i++) {
            if(list.get(i) % 2 == 1) {
                result++;
            }
        }
        return  result;
    }

}
```

과제3
---

- 0~9까지 들어있는 ArrayList 생성
- 9~0까지 들어있는 ArrayList 생성
- 두 ArrayList 의 같은 `index` 값들의 곱을 출력

```java
public class Method {

    public static void main(String[] args) {
        ArrayList<Integer> order1 = new ArrayList<>();
        ArrayList<Integer> order2 = new ArrayList<>();

        for(int i = 0; i < 10; i++) {
            order1.add(i);
        }

        for(int i = 9; i >= 0; i--) {
            order2.add(i);
        }

        System.out.println(order1);
        System.out.println(order2);

        multipleTwoArrayLists(order1, order2);
    }

    public static void multipleTwoArrayLists(ArrayList<Integer> order1, ArrayList<Integer> order2) {

        for(int i = 0; i < order1.size(); i++) {
            int result = order1.get(i) * order2.get(i);
            System.out.println(result);
        }
    }
}
```

---

CLASS 과제
===

**계산기 클래스 만들기**

- 계산기는 `이전계산결과`를 기억하고 있어야 한다.
- 계산기는 `이전계산결과`에, 정수에 대한 +, -, *, /, % 연산을 수행할 수 있어야 한다.
- 생성자를 통해서 이전 계산 변수의 초기값을 설정한다.
- 계산결과가 int가 아닌 경우에는 반올림하여 int 로 만들어 준다.
- 계산 결과가 음수인 경우 0으로 한다.
- 최종 결과를 리턴하는 함수가 있어야 한다.

**Calculator_instance.java**

```java
public class Calculator_instance {
    int previousResult;

    public Calculator_instance(int previousResult) {
        this.previousResult = previousResult;
    }

    public void add(int a) {
        previousResult += a;
        minusCheck();
    }

    public void multiple(int value) {
        previousResult *= value;
        minusCheck();
    }

    public void percent(int value) {
        previousResult %= value;
        minusCheck();
    }

    public void minus(int value) {
        previousResult -= value;
        minusCheck();
    }

    public void minusCheck() {
        if(this.previousResult < 0) {
            previousResult = 0;
        }
    }

    public void getResult() {
        System.out.println(previousResult);
    }
}
```

**Calculator_User.java**

```java
public class Calculator_User {
    public static void main(String[] args) {
        Calculator_instance calculator = new Calculator_instance(10);
        calculator.add(3);
        calculator.getResult();
        calculator.multiple(2);
        calculator.getResult();
        calculator.percent(4);
        calculator.getResult();
        calculator.minus(5);
        calculator.getResult();
    }
}
```
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

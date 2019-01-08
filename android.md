패스트캠퍼스 올인원 패키지: 모바일 앱 개발
===

```
JAVA 설치
Android Studio 설치
```

190108
---
- 안드로이드 스튜디오를 통한 안드로이드 앱 개발 과정 

View
---

```xml
<TextView 
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="안녕하세요"
    android:textSize="30dp"
    android:background="@color/colorAccent"
/>
```
- `android:layout_width` 안드로이드 스튜디오에서는 px 이 아닌 db로 값을 설정
- `"wrap_content"` 는 내부에 주어진 텍스트 값의 넓이와 높이에 맞게 값을 자동으로 설정
- `"match_parent"` 는 디바이스의 전체 넓이와 높이를 내부의 값과 상관없이 꽉 채우는 값


LinearLayout
---

- 자식 뷰들의 위치 / 방향 / 비중값 을 조절 가능

```xml
<!-- 부모요소 -->
<LinearLayout 
    android:orientation="vertical"
/>
```

- `android:orientation="vertical"` 자식 요소들의 레이아웃 방향을 지정 지정하지않게되면 기본 값은 horizontal 

```xml
<!-- 자식요소 -->
<TextView
    android:layout_width="0dp"
    android:layout_weight="1"
    android:layout_height="100dp"
    android:background="@color/colorAccent"
/>
```

- `android:layout_weight="1"` 해당 요소의 가중치를 설정 사용하려면 해당하는 넓이나 높이의 기본값은 `0dp` 로 만들어 주어야 한다.


```xml
<!-- 부모요소 -->
<LinearLayout 
    android:gravity="bottom"
>
</LinearLayout>
```

- `android:gravity` 자식 요소의 위치를 지정

RelativeLayout
---
- 자식뷰의 배치를 부모View 를 기준으로 배치

```xml
<!-- 부모요소 -->
<RelativeLayout>
 <TextView 
    android:layout_width="100dp"
    android:layout_height="100dp"
    android:background="@color/colorPrimaryDark"
    android:layout_alignParentRight="true"
 />
 <TextView
    android:layout_width="100dp"
    android:layout_height="100dp"
    android:background="@color/colorPrimaryDark"
    android:layout_centerInParent="true"
    />
</RelativeLayout>
```

- `android:layout_alignParentRight` 부모요소 기준으로 오른쪽으로 위치
- `android:layout_centerInParent="true"` 부모 요소 기준으로 양옆 위아래 가운데 위치

```xml
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/center"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorPrimaryDark"
        android:layout_centerInParent="true"
    />

    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_toRightOf="@+id/center"
        />

    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_above="@+id/center"
        />

    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_below="@+id/center"
        />
</RelativeLayout>
```

- 위의 예제는 `RelativeLayout` 안에서 기준요소를 정하고 그 기준요소를 기준으로 위치를 이동시키는 방법
- `android:id="@+id/center"` 기준 요소로 지정하기 위한 아이디값 설정
- `android:layout_toRightOf="@+id/center"` 기준요소의 끝라인에 맞춰서 오른쪽으로 이동
- `android:layout_above="@+id/center"` 기준요소의 윗라인에 맞춰서 이동

FrameLayout
---

- 뷰 컴포넌트들을 겹쳐보이고 싶을때

```xml
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@color/colorAccent"
        >
    </LinearLayout>

    <LinearLayout
        android:layout_width="300dp"
        android:layout_height="300dp"
        android:background="@color/colorPrimaryDark"
        >
    </LinearLayout>

    <LinearLayout
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:background="@color/colorPrimary"
        >
    </LinearLayout>

</FrameLayout>
```


ScrollView
---
- 오직 하나의 자식 뷰만을 가진다
- 단 자식의 자식을 여러개 갖는건 가능하다.

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:fillViewport="true"
        android:scrollbars="vertical">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"
            android:orientation="vertical">

            <TextView
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:layout_marginBottom="16dp"
                android:background="@color/colorPrimary" />

            <TextView
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:layout_marginBottom="16dp"
                android:background="@color/colorPrimary" />

            <TextView
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:layout_marginBottom="16dp"
                android:background="@color/colorPrimary" />
        </LinearLayout>
    </ScrollView>
</LinearLayout>
```

- `android:fillViewport="true"` 스크롤 영역을 채움
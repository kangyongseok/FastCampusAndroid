과제
===

과제1
---
- View 는 전부 동일한 크기를 갖는다.
- 임의로 크기를 지정해서는 안된다
- RelativeLayout 을 사용하면 안된다.
- 뷰끼리의 간격을 6dp 이다.

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:orientation="vertical"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal"
        android:layout_weight="1">
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent" 
            android:background="@color/colorAccent"/>
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"
            android:layout_marginRight="6dp"
            android:layout_marginLeft="6dp"/>
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:layout_marginTop="6dp"
        android:layout_marginBottom="6dp">
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"/>
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"
            android:layout_marginRight="6dp"
            android:layout_marginLeft="6dp"/>
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1">
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"/>
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"
            android:layout_marginRight="6dp"
            android:layout_marginLeft="6dp"/>
        <TextView
            android:layout_width="0dp"
            android:layout_weight="1"
            android:layout_height="match_parent"
            android:background="@color/colorAccent"/>
    </LinearLayout>

</LinearLayout>
```

- 전체 `LinearLayout` 내부에 `LinearLayout * 3` 
- 최상위 `LinearLayout` 에는 `oriental:vertical` 로 방향을 위에서 아래로
- 내부 `LinearLayout` 에는 넓이는 전체 뷰의 넓이 높이는 갯수에 따라 자동으로 지정되도록 `layout_weight="1"`
- 내부 `LinearLayout` 자식컴포넌트로 `TextView * 3`
- `TextView` 에는 넓이값 0dp `layout_weight="1"` 높이는 `layout_height="match_parent"`
- 그리고 여백을 가질수 있도록 6dp 설정

과제2
---

- 뷰의 크기는 100dp
- LinearLayout 사용금지
- 뷰끼리의 간격 6dp

```xml
<RelativeLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/colorPrimary"
    xmlns:android="http://schemas.android.com/apk/res/android">

    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:id="@+id/center"
        android:layout_centerInParent="true"
        android:layout_margin="6dp"/>
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_above="@+id/center"
        android:layout_toLeftOf="@+id/center"/>
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_toRightOf="@+id/center"
        android:layout_above="@+id/center"
        />
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_below="@+id/center"
        android:layout_centerInParent="true"
        />
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_toLeftOf="@+id/center"
        android:layout_centerInParent="true"
        />
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_above="@+id/center"
        android:layout_centerInParent="true"
        />
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_toRightOf="@+id/center"
        android:layout_centerInParent="true"
        />
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_toRightOf="@+id/center"
        android:layout_below="@+id/center"
        />
    <TextView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorAccent"
        android:layout_toLeftOf="@+id/center"
        android:layout_below="@+id/center"
        />
</RelativeLayout>
```

- `RelativeLayout` 사용
- 총 9개의 `TextView`
- 기준 컴포넌트를 잡고 `layout_toLeftOf` / `layout_toRightOf` / `layout_above` / `layout_below` 로 위치를 잡음 
- 기준값에 여백주니 나머지는 자동으로 여백이 들어감

과제3
---

- 모든 뷰는 화면의 정중앙으로 정렬
- FrameLayout 사용

```xml
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:orientation="vertical"
    android:layout_height="match_parent">

   <LinearLayout
       android:layout_width="match_parent"
       android:layout_height="match_parent"
       android:background="@color/colorPrimaryDark"/>
    <LinearLayout
        android:layout_width="300dp"
        android:layout_height="300dp"
        android:background="@color/colorPrimary"
        android:layout_gravity="center"/>
    <LinearLayout
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:background="@color/colorAccent"
        android:layout_gravity="center"/>
    <LinearLayout
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@color/colorPrimary"
        android:layout_gravity="center"/>
</FrameLayout>
```
- `layout_gravity="center"` 가운데 정렬
- `LinearLayout` 으로 겹칠 레이아웃들을 생성
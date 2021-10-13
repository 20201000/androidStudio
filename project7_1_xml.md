# **string.xml**
## 7장 실습 7-1

![image](https://user-images.githubusercontent.com/79977182/137048150-ac84f840-3534-4d7c-b816-be198a54f6f4.png)

![image](https://user-images.githubusercontent.com/79977182/137048245-7f65c9ff-2b60-4bf7-b189-2fc65844f6a0.png)

```java
<resources>
    <string name="app_name">project7_1</string>
    <string name="tv1">오른쪽 위 메뉴 버튼을 누르세요</string>
    <string name="btn1">이건 버튼</string>
</resources>
```

# **activity_main.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:id="@+id/baseLayout"
    android:orientation="vertical">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/tv1"
        android:textSize="20dp"/>

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/btn1"
        android:layout_gravity="center"
        android:backgroundTint="#C8CDE3"/>

</LinearLayout>
```

# **menu1.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <item
        android:id="@+id/itemRed"
        android:title="배경색(빨강)">
    </item>
    <item
        android:id="@+id/itemGreen"
        android:title="배경색(초록)">
    </item>
    <item
        android:id="@+id/itemBlue"
        android:title="배경색(파랑)">
    </item>
    <item android:title="버튼 변경 >>">
        <menu>
            <item
                android:id="@+id/subRotate"
                android:title="버튼 45도 회전"/>
            <item
                android:id="@+id/subSize"
                android:title="버튼 2배 확대"/>
        </menu>
    </item>
</menu>
```
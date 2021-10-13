# **strings.xml**
## 7장 직접 풀어보기 7-1

![image](https://user-images.githubusercontent.com/79977182/137050450-42014838-a04e-49b6-805f-9fa1e00bf1ec.png)

![image](https://user-images.githubusercontent.com/79977182/137050638-f97d3a97-91a1-4ce0-9ecf-1f1ed9c497cb.png)

```java
<resources>
    <string name="app_name">project7_1</string>
    <string name="tv1">각도 입력</string>
</resources>
```

# **activity_main.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:id="@+id/baseLayout">

    <TextView
        android:id="@+id/tv1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/tv1"
        android:textSize="20dp"/>

    <EditText
        android:id="@+id/et1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toEndOf="@+id/tv1"/>

    <ImageView
        android:id="@+id/iv"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/et1"
        android:src="@drawable/sky"/>

</RelativeLayout>
```

# **menu1.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <item
        android:id="@+id/itemRotate"
        android:title="그림 회전">
    </item>
    <group
        android:checkableBehavior="single">
        <item
            android:id="@+id/option1"
            android:title="사진1"
            android:checked="true"/>
        <item
            android:id="@+id/option2"
            android:title="사진2"/>
        <item
            android:id="@+id/option3"
            android:title="사진3"/>
    </group>
</menu>
```
# **string.xml**
## 5장 연습문제 4번

![image](https://user-images.githubusercontent.com/79977182/136690754-0589c9ce-efd6-48f3-9115-016f852e0831.png)

![5장연습문제4번](https://user-images.githubusercontent.com/79977182/136689730-ce9fed5d-ae0d-49f8-9766-bb7f4fd10009.png)

```java
<resources>
    <string name="app_name">project5_4</string>
    <string name="tv1">전화번호</string>
    <string name="btn1">입력</string>
    <string name="btn2">취소</string>
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
    android:orientation="vertical">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/tv1" />

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />

    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="right">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:backgroundTint="#234122"
            android:text="@string/btn1"/>

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:backgroundTint="#349233"
            android:text="@string/btn2"/>

    </LinearLayout>

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/tv1"
            android:text="@string/tv1"
            android:layout_alignParentLeft="true"
            android:layout_alignParentTop="true"/>

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:id="@+id/et1"
            android:layout_toRightOf="@+id/tv1"/>

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/btn1"
            android:backgroundTint="#ff2392"
            android:id="@+id/btn1"
            android:layout_below="@+id/et1"
            android:layout_toLeftOf="@+id/btn2"/>

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/btn2"
            android:backgroundTint="#ff999111"
            android:id="@+id/btn2"
            android:layout_below="@+id/et1"
            android:layout_alignParentRight="true"/>

    </RelativeLayout>

</LinearLayout>
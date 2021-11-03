# **activity_main.xml**
## 7장 직접 풀어보기 7-3

![211103-7](https://user-images.githubusercontent.com/79977182/140001763-22c4052f-144e-4eb5-ba3a-561e8c567174.jpg)

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">

    //EditText로 수정됨
    <EditText
        android:id="@+id/etName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="사용자 이름"/>

    //EditText로 수정됨
    <EditText
        android:id="@+id/etEmail"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="이메일"/>

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="여기를 클릭"
        android:layout_gravity="center"/>

</LinearLayout>
```

# **dialog1.xml**

>수정사항 없음

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="사용자 이름"/>

    <EditText
        android:id="@+id/dlgEdt1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="이메일"/>

    <EditText
        android:id="@+id/dlgEdt2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

</LinearLayout>
```

# **toast1.xml**

>수정사항 없음

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="horizontal"
    android:gravity="center"
    android:background="#ff0000"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@android:drawable/btn_star_big_on"/>

    <TextView
        android:id="@+id/toastText1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="TextView"/>

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@android:drawable/btn_star_big_on"/>

</LinearLayout>
```
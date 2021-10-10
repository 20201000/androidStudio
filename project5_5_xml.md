# **activity_main.xml**
## 5장 연습문제 5번

![image](https://user-images.githubusercontent.com/79977182/136690819-38a7ffe5-4ca9-44c6-9ad6-607b5b27c69c.png)

![5장연습문제5번](https://user-images.githubusercontent.com/79977182/136689851-9c4c24d5-2b4c-4b01-a3df-80a4247dfb8f.png)

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/center"
        android:layout_width="150dp"
        android:layout_height="150dp"
        android:layout_centerInParent="true"
        android:text="기준위젯"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignTop="@+id/center"
        android:text="1번"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignBottom="@+id/center"
        android:text="2번"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_toLeftOf="@+id/center"
        android:text="3번"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignLeft="@+id/center"
        android:text="4번"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_alignRight="@+id/center"
        android:text="5번"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_above="@+id/center"
        android:layout_alignParentRight="true"
        android:text="6번"/>

</RelativeLayout>
```

> java 파일에는 변경 사항이 없음
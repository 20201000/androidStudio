# **activity_main.xml**
## 8장 예제 8-8

![8장예제8번](https://user-images.githubusercontent.com/79977182/141416856-7724e86e-bf78-47f6-b528-ecc171390277.png)

>raw 파일 읽어오기

</br>

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">

    <Button
        android:id="@+id/btnRead"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="/res/raw에서 파일 읽기"/>

    <EditText
        android:id="@+id/edtRaw"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:lines="10"/>

</LinearLayout>
```
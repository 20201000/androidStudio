# **activity_main.xml**
## 8장 예제 8-1

![211110-9](https://user-images.githubusercontent.com/79977182/141040603-9ccfcacd-b343-4993-ac9f-9db451f3ed34.png)

>일기장 앱

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

    <DatePicker
        android:id="@+id/datePicker1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:calendarViewShown="false"
        android:datePickerMode="spinner"/>

    <EditText
        android:id="@+id/edtDiary"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="#00ff00"
        android:lines="8"/>

    <Button
        android:id="@+id/btnWrite"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:enabled="false"
        android:text="Button"/>

</LinearLayout>
```
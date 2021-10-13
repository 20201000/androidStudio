# **strings.xml**
## 7장 실습 7-2

![211013-8](https://user-images.githubusercontent.com/79977182/137054847-6b68d4c0-3a4f-4316-8266-f36682f6c6eb.png)

![image](https://user-images.githubusercontent.com/79977182/137054828-c03bc241-9b0b-4af1-9f0b-54c82790ed86.png)

```java
<resources>
    <string name="app_name">project7_2</string>
    <string name="btn1">배경색 변경</string>
    <string name="btn2">버튼 변경</string>
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
    android:orientation="vertical"
    android:id="@+id/baseLayout">

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="@string/btn1"
        android:backgroundTint="#B3E3CD"/>

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="@string/btn2"
        android:backgroundTint="#B3E3CD"/>

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

</menu>
```

# **menu2.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <item
        android:id="@+id/subRotate"
        android:title="버튼 45도 회전"/>
    <item
        android:id="@+id/subSize"
        android:title="버튼 2배 확대"/>

</menu>
```
# **activity_main.xml**
## 7장 연습문제 7-6

![211110-7](https://user-images.githubusercontent.com/79977182/141036104-88423b4c-ee35-47fd-bbba-ebe32937a23c.jpg)

![211110-8](https://user-images.githubusercontent.com/79977182/141036108-034918a4-f1b1-4f58-9418-18369a9bbefd.png)

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">

    <RadioGroup
        android:id="@+id/rGroup1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">

        <RadioButton
            android:id="@+id/rDog"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="강아지"/>

        <RadioButton
            android:id="@+id/rCat"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="고양이"/>

        <RadioButton
            android:id="@+id/rRabbit"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="토끼"/>

        <RadioButton
            android:id="@+id/rHorse"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="말"/>

    </RadioGroup>

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="그림보기"/>

</LinearLayout>
```

# **dialog.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"/>

</LinearLayout>
```
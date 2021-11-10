# **activity_main.xml**
## 7장 연습문제 7-5

![211110-6](https://user-images.githubusercontent.com/79977182/141029705-b05b8fc4-975a-40b4-802e-c4c2ba8cfd9c.jpg)

![211110-4](https://user-images.githubusercontent.com/79977182/141029700-10a2ee34-6fd1-4a52-87c4-34b2894b82b5.png)

![211110-5](https://user-images.githubusercontent.com/79977182/141029703-aad59d83-1929-4d9e-8b02-611efcbb11c6.png)

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:gravity="center">

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="토스트 보이기"
        android:layout_gravity="center"
        android:backgroundTint="#F7BCB5"/>

</LinearLayout>
```

# **toast1.xml**

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center">

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@drawable/r"
        android:layout_gravity="center"/>

</LinearLayout>
```
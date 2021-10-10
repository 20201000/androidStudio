# **activity_main.xml**
## 5장 연습문제 6번

![image](https://user-images.githubusercontent.com/79977182/136690800-ae85ebfb-62ba-481b-bd12-81ed4464e3df.png)

![5장연습문제6번](https://user-images.githubusercontent.com/79977182/136690002-ee4eff60-73b0-4dfe-bd31-d4aa10ca28f5.png)

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:background="#80F08F"
    android:gravity="center">

    <LinearLayout
        android:id="@+id/linear250"
        android:layout_width="250dp"
        android:layout_height="250dp"
        android:background="#F0B185"
        android:gravity="center">

        <LinearLayout
            android:id="@+id/linear150"
            android:layout_width="150dp"
            android:layout_height="150dp"
            android:background="#7150D9"
            android:gravity="center">

            <LinearLayout
                android:id="@+id/linear50"
                android:layout_width="50dp"
                android:layout_height="50dp"
                android:background="#F87F0C"
                android:orientation="horizontal">

            </LinearLayout>

        </LinearLayout>

    </LinearLayout>

</LinearLayout>
```
# **activity_main.xml**
## 6장 연습문제 6번

![image](https://user-images.githubusercontent.com/79977182/136690855-3c6bfe36-f936-4929-9cdf-f4d12f135a25.png)

![6장연습문제6번](https://user-images.githubusercontent.com/79977182/136690184-8f7e7dd5-c441-4e99-92a8-242b8dc3f1dd.png)

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="여긴 서랍 밖입니다."
        android:gravity="center"/>

    <SlidingDrawer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:content="@+id/content1"
        android:handle="@+id/handle1">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/handle1"
            android:text="서랍 손잡이"/>

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:id="@+id/content1"
            android:background="#8D60D6"
            android:gravity="center"
            android:orientation="vertical">


            <SlidingDrawer
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:content="@+id/content2"
                android:handle="@+id/handle2">

                <Button
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:id="@+id/handle2"
                    android:text="안 서랍 손잡이"/>

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:id="@+id/content2"
                    android:background="#4ED9B1"
                    android:gravity="center|bottom"
                    android:orientation="vertical">

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:text="여긴 두번째 서랍 안입니다."
                        android:gravity="center"
                        android:layout_gravity="bottom"/>

                </LinearLayout>
            </SlidingDrawer>
        </LinearLayout>

    </SlidingDrawer>


</LinearLayout>
```

> java파일에는 수정사항이 없음
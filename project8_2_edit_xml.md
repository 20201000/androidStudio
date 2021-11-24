# **activity_main.xml**
## 8장 직접 풀어보기 8-2

![211124-6](https://user-images.githubusercontent.com/79977182/143157193-83a43d19-ef8f-48de-9f7b-07fecf5091cf.jpg)

![211124-5](https://user-images.githubusercontent.com/79977182/143156849-e4e25d50-aab9-493b-8cfa-a9193fe8d469.png)

</br>

## 주의
</br>

![211124-3](https://user-images.githubusercontent.com/79977182/143153786-a829ebc9-07fd-4d0e-8cb6-1994f49a6c3d.png)

build.gradle > targetSdk를 29로
</br>
그 이상 버전은 SD카드 접근이 어려움

</br>

![211124-4](https://user-images.githubusercontent.com/79977182/143153789-230bae8f-41da-4d00-a4d5-89f77fae1df1.png)

AndroidManifest에서
</br>
uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"
</br>
android:requestLegacyExternalStorage="true"
</br>
추가하기

</br>

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <Button
            android:id="@+id/btnPrev"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="이전 그림" />

        //TextView 추가, 나머지 동일
        <TextView
            android:id="@+id/tv"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:gravity="center"
            android:text="1/5" />

        <Button
            android:id="@+id/btnNext"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="다음 그림" />
    </LinearLayout>

    <com.example.project8_2.myPictureView
        android:id="@+id/myPictureView1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

</LinearLayout>
```
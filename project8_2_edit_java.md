# **MainActivity.java**
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
package com.example.project8_2;

import androidx.appcompat.app.AppCompatActivity;
import androidx.core.app.ActivityCompat;

import android.Manifest;
import android.app.Activity;
import android.os.Bundle;
import android.os.Environment;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

import java.io.File;

public class MainActivity extends Activity {
    Button btnPrev, btnNext;
    myPictureView myPicture;
    int curNum = 1;
    File[] imageFiles;
    String imageFname;
    TextView tv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        setTitle("간단 이미지 뷰어");
        ActivityCompat.requestPermissions(this, new String[]{Manifest.permission.WRITE_EXTERNAL_STORAGE}, MODE_PRIVATE);
        btnPrev = (Button) findViewById(R.id.btnPrev);
        btnNext = (Button) findViewById(R.id.btnNext);
        myPicture = (myPictureView) findViewById(R.id.myPictureView1);
        tv = (TextView) findViewById(R.id.tv);

        imageFiles = new File(Environment.getExternalStorageDirectory().getAbsolutePath() + "/Pictures").listFiles();
        imageFname = imageFiles[1].toString();
        myPicture.imagePath = imageFname;

        tv.setText(curNum + "/" + (imageFiles.length - 1));

        btnPrev.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                curNum--;
                if (curNum == 0)
                    curNum = 6;
                imageFname = imageFiles[curNum].toString();
                myPicture.imagePath = imageFname;
                myPicture.invalidate();
                tv.setText(curNum + "/" + (imageFiles.length - 1));
            }
        });

        btnNext.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                curNum++;
                if (curNum == 7)
                    curNum = 1;
                imageFname = imageFiles[curNum].toString();
                myPicture.imagePath = imageFname;
                myPicture.invalidate();
                tv.setText(curNum + "/" + (imageFiles.length - 1));
            }
        });
    }
}
```

# **myPictureView.java**
> 동일
# **MainActivity.java**
## 7장 직접 풀어보기 7-1

![image](https://user-images.githubusercontent.com/79977182/137050450-42014838-a04e-49b6-805f-9fa1e00bf1ec.png)

![image](https://user-images.githubusercontent.com/79977182/137050638-f97d3a97-91a1-4ce0-9ecf-1f1ed9c497cb.png)

```java
package com.example.project7_1;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.graphics.Color;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ImageView;
import android.widget.LinearLayout;
import android.widget.RelativeLayout;

public class MainActivity extends AppCompatActivity {
    RelativeLayout baseLayout;
    ImageView imageView;
    EditText editText;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        setTitle("풍경");

        baseLayout = (RelativeLayout) findViewById(R.id.baseLayout);
        imageView = (ImageView) findViewById(R.id.iv);
        editText = (EditText) findViewById(R.id.et1);
    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        super.onCreateOptionsMenu(menu);
        MenuInflater mInflater = getMenuInflater();
        mInflater.inflate(R.menu.menu1, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {
        switch (item.getItemId()) {
            case R.id.itemRotate:
                //edit text로부터  숫자 가져오기
                imageView.setRotation(Integer.parseInt(editText.getText().toString()));
                return true;
            case R.id.option1:
                //체크 항목 바꾸기 - 함수 인자 item 이용
                item.setChecked(true);
                imageView.setImageResource(R.drawable.sky);
                return true;
            case R.id.option2:
                item.setChecked(true);
                imageView.setImageResource(R.drawable.daylight);
                return true;
            case R.id.option3:
                item.setChecked(true);
                imageView.setImageResource(R.drawable.fall);
                return true;
        }
        return false;
    }
}
```
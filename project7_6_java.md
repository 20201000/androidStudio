# **MainActivity.java**
## 7장 연습문제 7-6

![211110-7](https://user-images.githubusercontent.com/79977182/141036104-88423b4c-ee35-47fd-bbba-ebe32937a23c.jpg)

![211110-8](https://user-images.githubusercontent.com/79977182/141036108-034918a4-f1b1-4f58-9418-18369a9bbefd.png)

</br>

```java
package com.example.project7_6;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;
import android.widget.RadioButton;
import android.widget.RadioGroup;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    Button button1;
    ImageView imageView;
    View dialogView;
    RadioGroup rGroup;
    RadioButton rDog, rCat, rRabbit, rHorse;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        button1 = (Button) findViewById(R.id.button1);
        rGroup = (RadioGroup) findViewById(R.id.rGroup1);
        rDog = (RadioButton) findViewById(R.id.rDog);
        rCat = (RadioButton) findViewById(R.id.rCat);
        rRabbit = (RadioButton) findViewById(R.id.rRabbit);
        rHorse = (RadioButton) findViewById(R.id.rHorse);

        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                AlertDialog.Builder dlg = new AlertDialog.Builder(MainActivity.this);
                dialogView = (View) View.inflate(MainActivity.this, R.layout.dialog, null);

                //주의 dialogView.
                //없으면 null pointer exception으로 setImageResource에서 죽음
                imageView = (ImageView) dialogView.findViewById(R.id.imageView);

                dlg.setView(dialogView);
                dlg.setPositiveButton("닫기", null);

                switch (rGroup.getCheckedRadioButtonId()) {
                    case R.id.rDog:
                        imageView.setImageResource(R.drawable.dog);
                        dlg.setTitle("강아지");
                        dlg.show();
                        break;
                    case R.id.rCat:
                        imageView.setImageResource(R.drawable.cat);
                        dlg.setTitle("고양이");
                        dlg.show();
                        break;
                    case R.id.rRabbit:
                        imageView.setImageResource(R.drawable.rabbit);
                        dlg.setTitle("토끼");
                        dlg.show();
                        break;
                    case R.id.rHorse:
                        imageView.setImageResource(R.drawable.horse);
                        dlg.setTitle("말");
                        dlg.show();
                        break;
                    default:
                        Toast.makeText(getApplicationContext(), "동물 먼저 선택하세요", Toast.LENGTH_SHORT).show();
                }
            }
        });
    }
}
```
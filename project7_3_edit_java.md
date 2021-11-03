# **MainActivity.java**
## 7장 직접 풀어보기 7-3

![211103-7](https://user-images.githubusercontent.com/79977182/140001763-22c4052f-144e-4eb5-ba3a-561e8c567174.jpg)

</br>

```java
package com.example.project7_3;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.DialogInterface;
import android.os.Bundle;
import android.view.Display;
import android.view.Gravity;
import android.view.View;
import android.view.WindowManager;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    //이름 변경
    TextView EtName, EtEmail;
    Button Button1;
    EditText DlgEdt1, DlgEdt2;
    TextView ToastText1;
    View Dialog1, Toast1;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        EtName = (TextView) findViewById(R.id.etName);
        EtEmail = (TextView) findViewById(R.id.etEmail);
        Button1 = (Button) findViewById(R.id.button1);

        Button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Dialog1 = (View) View.inflate(MainActivity.this, R.layout.dialog1, null);
                AlertDialog.Builder dlg = new AlertDialog.Builder(MainActivity.this);
                dlg.setTitle("사용자 정보 입력");
                dlg.setIcon(R.drawable.emo_im_foot_in_mouth);
                dlg.setView(Dialog1);

                //연결
                DlgEdt1 = (EditText) Dialog1.findViewById(R.id.dlgEdt1);
                DlgEdt2 = (EditText) Dialog1.findViewById(R.id.dlgEdt2);

                //activity_main의 Et 값을 DlgEdt에 대입
                DlgEdt1.setText(EtName.getText().toString());
                DlgEdt2.setText(EtEmail.getText().toString());

                dlg.setPositiveButton("확인", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {

                        //위에서 연결해 줘서 연결 내용 지움
                        EtName.setText(DlgEdt1.getText().toString());
                        EtEmail.setText(DlgEdt2.getText().toString());
                    }
                });
                dlg.setNegativeButton("취소", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        Toast toast = new Toast(MainActivity.this);
                        Toast1 = (View) View.inflate(MainActivity.this, R.layout.toast1, null);
                        ToastText1 = (TextView) Toast1.findViewById(R.id.toastText1);
                        ToastText1.setText("취소했습니다.");
                        toast.setView(Toast1);

                        //수정된 부분
                        Display display = ((WindowManager) getSystemService(WINDOW_SERVICE)).getDefaultDisplay();

                        //랜덤으로 토스트 메시지 위치 설정
                        int xOffset = (int) (Math.random() * display.getWidth());
                        int yOffset = (int) (Math.random() * display.getHeight());

                        //위치시키기
                        toast.setGravity(Gravity.TOP | Gravity.LEFT, xOffset, yOffset);

                        toast.show();
                    }
                });
                dlg.show();
            }
        });
    }
}
```

> 실행화면

![211103-4](https://user-images.githubusercontent.com/79977182/140001636-2bbae43c-1ee8-4bab-bc22-0fccc69e1675.png)

![211103-5](https://user-images.githubusercontent.com/79977182/140001642-8be5be8e-d7e9-46d5-a024-6894924dde02.png)

![211103-6](https://user-images.githubusercontent.com/79977182/140002156-cbaed415-2711-47df-a4ae-72dd5666eeed.png)
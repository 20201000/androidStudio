# **MainActivity.java**
## 8장 예제 8-1

![211110-9](https://user-images.githubusercontent.com/79977182/141040603-9ccfcacd-b343-4993-ac9f-9db451f3ed34.png)

![8장1번직접풀어보기](https://user-images.githubusercontent.com/79977182/141416837-8dff7cad-b6fd-48ef-b8af-3098b55bc1cc.png)

>일기장 앱</br>
처음 앱을 실행했을 때 저장된 데이터를 불러오기

</br>

```java
package com.example.project8_1;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Context;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.CalendarView;
import android.widget.DatePicker;
import android.widget.EditText;
import android.widget.Toast;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Calendar;

public class MainActivity extends AppCompatActivity {
    DatePicker dp;
    EditText edtDiary;
    Button btnWrite;
    String fileName;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        setTitle("간단 일기장");

        dp=(DatePicker) findViewById(R.id.datePicker1);
        edtDiary=(EditText) findViewById(R.id.edtDiary);
        btnWrite=(Button) findViewById(R.id.btnWrite);

        Calendar cal = Calendar.getInstance();
        int cYear=cal.get(Calendar.YEAR);
        int cMonth=cal.get(Calendar.MONTH);
        int cDay=cal.get(Calendar.DAY_OF_MONTH);

        //추가된 부분
        fileName = Integer.toString(cYear)+"_"+Integer.toString(cMonth+1)+"_"+Integer.toString(cDay)+".txt";
        String str=readDiary(fileName);
        edtDiary.setText(str);
        btnWrite.setEnabled(true);
        //
        
        dp.init(cYear, cMonth, cDay, new DatePicker.OnDateChangedListener() {
            @Override
            public void onDateChanged(DatePicker datePicker, int year, int monthOfYear, int dayOfMonth) {
                fileName = Integer.toString(year)+"_"+Integer.toString(monthOfYear+1)+"_"+Integer.toString(dayOfMonth)+".txt";
                String str=readDiary(fileName);
                edtDiary.setText(str);
                btnWrite.setEnabled(true);
            }
        });

        btnWrite.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                try {
                    FileOutputStream outFs=openFileOutput(fileName, Context.MODE_PRIVATE);
                    String str=edtDiary.getText().toString();
                    outFs.write(str.getBytes());
                    outFs.close();
                    Toast.makeText(getApplicationContext(), fileName+" 이 저장됨", Toast.LENGTH_SHORT).show();
                }catch (IOException e){}
            }
        });
    }
    String readDiary(String fName){
        String diaryStr=null;
        FileInputStream inFs;
        try {
            inFs=openFileInput(fName);
            byte[] txt = new byte[500];
            inFs.read(txt);
            inFs.close();
            diaryStr=(new String(txt)).trim();
            btnWrite.setText("수정하기");
        }catch (IOException e){
            edtDiary.setHint("일기 없음");
            btnWrite.setText("새로 저장");
        }
        return diaryStr;
    }
}
```
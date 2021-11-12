# **MainActivity.java**
## 8장 예제 8-8

![8장예제8번](https://user-images.githubusercontent.com/79977182/141416856-7724e86e-bf78-47f6-b528-ecc171390277.png)

>raw 파일 읽어오기

</br>

```java
package com.example.project8_8;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import java.io.IOException;
import java.io.InputStream;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btnRead = (Button) findViewById(R.id.btnRead);
        final EditText edtRaw = (EditText) findViewById(R.id.edtRaw);

        btnRead.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                try {
                    //R.raw.파일명
                    InputStream inputS = getResources().openRawResource(R.raw.hi);
                    byte[] txt = new byte[inputS.available()];
                    inputS.read(txt);
                    edtRaw.setText(new String(txt));
                    inputS.close();
                } catch (IOException e){
                }
            }
        });
    }
}
```
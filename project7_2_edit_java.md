# **MainActivity.java**
## 7장 직접 풀어보기 7-2

![211013-8](https://user-images.githubusercontent.com/79977182/137054847-6b68d4c0-3a4f-4316-8266-f36682f6c6eb.png)

</br>

> ### **java코드로만 구현해보기**

</br>

![image](https://user-images.githubusercontent.com/79977182/137060169-59894a2c-c655-4f12-bd77-56274bdc7cd3.png)

```java
package com.example.project7_2_edit;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.graphics.Color;
import android.os.Bundle;
import android.view.ContextMenu;
import android.view.Gravity;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.view.View;
import android.widget.Button;
import android.widget.LinearLayout;

public class MainActivity extends AppCompatActivity {
    LinearLayout baseLayout;
    Button button1, button2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setTitle("java 코드로만 구현");

        LinearLayout.LayoutParams params = new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.MATCH_PARENT,
                LinearLayout.LayoutParams.MATCH_PARENT
        );

        baseLayout = new LinearLayout(this);
        button1 = new Button(this);
        button2 = new Button(this);

        //params for button
        LinearLayout.LayoutParams params1 = new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.WRAP_CONTENT,
                LinearLayout.LayoutParams.WRAP_CONTENT
        );

        baseLayout.setOrientation(LinearLayout.VERTICAL);
        setContentView(baseLayout, params);

        button1.setText("배경색 변경");
        button2.setText("버튼 변경");

        baseLayout.addView(button1, params1);
        baseLayout.addView(button2, params1);
        registerForContextMenu(button1);
        registerForContextMenu(button2);
    }

    @Override
    public void onCreateContextMenu(ContextMenu menu, View v, ContextMenu.ContextMenuInfo menuInfo) {
        super.onCreateContextMenu(menu, v, menuInfo);

        MenuInflater mInflater = getMenuInflater();
        if(v==button1) {
            menu.setHeaderTitle("배경색 변경");

            menu.add(0, 1, 0, "배경색(빨강)");
            menu.add(0, 2, 0, "배경색(초록)");
            menu.add(0, 3, 0, "배경색(파랑)");
        }
        if (v == button2) {
            menu.add(0, 4, 0, "버튼 45도 회전");
            menu.add(0, 5, 0, "버튼 2배 확대");
        }
    }

    @Override
    public boolean onContextItemSelected(@NonNull MenuItem item) {
        switch (item.getItemId()) {
            case 1:
                baseLayout.setBackgroundColor(Color.RED);
                return true;
            case 2:
                baseLayout.setBackgroundColor(Color.GREEN);
                return true;
            case 3:
                baseLayout.setBackgroundColor(Color.BLUE);
                return true;
            case 4:
                button2.setRotation(45);
                return true;
            case 5:
                button2.setScaleX(2);
                return true;
        }
        return false;
    }
}
```

> java 코드로 버튼을 가운데 수직 정렬하는 방법을 찾지 못했다.
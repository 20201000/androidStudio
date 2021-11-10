# **MainActivity.java**
## 7장 연습문제 7-5

![211110-6](https://user-images.githubusercontent.com/79977182/141029705-b05b8fc4-975a-40b4-802e-c4c2ba8cfd9c.jpg)

![211110-4](https://user-images.githubusercontent.com/79977182/141029700-10a2ee34-6fd1-4a52-87c4-34b2894b82b5.png)

![211110-5](https://user-images.githubusercontent.com/79977182/141029703-aad59d83-1929-4d9e-8b02-611efcbb11c6.png)

</br>

```java
package com.example.project7_5;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.Display;
import android.view.Gravity;
import android.view.View;
import android.view.WindowManager;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    Button button1;
    View toastView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        button1 = (Button) findViewById(R.id.button1);

        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast toast = new Toast(MainActivity.this);
                Display display = ((WindowManager) getSystemService(WINDOW_SERVICE)).getDefaultDisplay();
                int xOffset = (int) (Math.random()*display.getWidth());
                int yOffset = (int) (Math.random()*display.getHeight());
                toastView = (View) View.inflate(MainActivity.this, R.layout.toast1, null);
                toast.setView(toastView);
                toast.setGravity(Gravity.TOP|Gravity.LEFT, xOffset, yOffset);
                toast.show();
            }
        });
    }
}
```
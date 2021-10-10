# **MainActivity.java**
## 5장 연습문제 6번

![image](https://user-images.githubusercontent.com/79977182/136690800-ae85ebfb-62ba-481b-bd12-81ed4464e3df.png)

![5장연습문제6번](https://user-images.githubusercontent.com/79977182/136690002-ee4eff60-73b0-4dfe-bd31-d4aa10ca28f5.png)

```java
package com.example.project5_6;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.LinearLayout;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    LinearLayout linear250, linear150, linear50;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        setTitle("연습문제 5-6");

        linear250=(LinearLayout) findViewById(R.id.linear250);
        linear150=(LinearLayout) findViewById(R.id.linear150);
        linear50=(LinearLayout) findViewById(R.id.linear50);

        linear250.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(getApplicationContext(), "폭:" + view.getWidth() + "너비: " + view.getHeight(), Toast.LENGTH_SHORT).show();
            }
        });

        linear150.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(getApplicationContext(), "폭:" + view.getWidth() + "너비: " + view.getHeight(), Toast.LENGTH_SHORT).show();
            }
        });

        linear50.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(getApplicationContext(), "폭:" + view.getWidth() + "너비: " + view.getHeight(), Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```
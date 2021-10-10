# **MainActivity.java**
## 5장 연습문제 7번

![image](https://user-images.githubusercontent.com/79977182/136690811-37198451-087a-422a-b1b3-5518b43e1f2f.png)

![5장연습문제7번](https://user-images.githubusercontent.com/79977182/136690100-a81335e4-4e86-422c-823c-440e45c02327.png)

```java
package com.example.project5_7;

import androidx.appcompat.app.AppCompatActivity;

import android.graphics.Color;
import android.os.Bundle;
import android.widget.LinearLayout;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
//        setContentView(R.layout.activity_main);
        setTitle("연습문제 5-7");

        LinearLayout.LayoutParams params = new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.MATCH_PARENT,
                LinearLayout.LayoutParams.MATCH_PARENT
        );

        LinearLayout baseLayout = new LinearLayout(this);
        baseLayout.setOrientation(LinearLayout.VERTICAL);
        baseLayout.setBackgroundColor(Color.rgb(13, 80, 230));
        setContentView(baseLayout, params);

        LinearLayout.LayoutParams params_1 = new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.MATCH_PARENT,
                LinearLayout.LayoutParams.MATCH_PARENT
        );
        params_1.weight = 1;

        LinearLayout layout_1 = new LinearLayout(this);
        layout_1.setOrientation(LinearLayout.HORIZONTAL);
        layout_1.setBackgroundColor(Color.rgb(133, 8, 230));
        baseLayout.addView(layout_1, params_1);

        LinearLayout layout_2 = new LinearLayout(this);
        layout_2.setBackgroundColor(Color.rgb(133, 80, 230));
        layout_1.addView(layout_2, params_1);

        LinearLayout layout_3 = new LinearLayout(this);
        layout_3.setOrientation(LinearLayout.VERTICAL);
        layout_1.addView(layout_3, params_1);

        LinearLayout layout_4 = new LinearLayout(this);
        layout_4.setBackgroundColor(Color.rgb(143,252,232));
        layout_3.addView(layout_4, params_1);

        LinearLayout layout_5 = new LinearLayout(this);
        layout_5.setBackgroundColor(Color.rgb(62,230,81));
        layout_3.addView(layout_5, params_1);

        LinearLayout layout_6 = new LinearLayout(this);
        layout_6.setBackgroundColor(Color.rgb(252,13,92));
        baseLayout.addView(layout_6, params_1);
    }
}
```

> java 파일로만 정렬하는 문제 </br> xml파일이 없음
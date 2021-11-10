# **MainActivity.java**
## 7장 연습문제 7-4

![211110-3](https://user-images.githubusercontent.com/79977182/141027624-1496599c-535b-46f1-b4ca-2f676b77b909.jpg)

> java 코드로만 구현해 보기

![211110-2](https://user-images.githubusercontent.com/79977182/141027503-aefbb117-3a5e-4768-883b-20f2dc18749f.png)

</br>

```java
package com.example.project7_4;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.widget.ImageView;
import android.widget.LinearLayout;

public class MainActivity extends AppCompatActivity {
    LinearLayout baseLayout;
    ImageView imageView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        LinearLayout.LayoutParams params = new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.MATCH_PARENT,
                LinearLayout.LayoutParams.MATCH_PARENT
        );

        baseLayout = new LinearLayout(this);

        baseLayout.setOrientation(LinearLayout.VERTICAL);
        setContentView(baseLayout, params);

        imageView = new ImageView(this);
        baseLayout.addView(imageView);
    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        super.onCreateOptionsMenu(menu);

        menu.add(0,1,0,"강아지");
        menu.add(0,2,0,"고양이");
        menu.add(0,3,0,"토끼");

        return true;
    }

    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {
        switch (item.getItemId()) {
            case 1:
                imageView.setImageResource(R.drawable.dog);
                return true;
            case 2:
                imageView.setImageResource(R.drawable.cat);
                return true;
            case 3:
                imageView.setImageResource(R.drawable.rabbit);
                return true;
        }
        return false;
    }
}
```
# **MainActivity.java**
## 6장 연습문제 7번

![image](https://user-images.githubusercontent.com/79977182/136690844-716cf807-8f37-486d-a23d-e339b90b6ff1.png)

![6장연습문제7번](https://user-images.githubusercontent.com/79977182/136690266-bbf0ba03-5700-4c1f-8ec0-68e746f904e3.png)

```java
package com.example.project6_7;

import androidx.annotation.Nullable;
import androidx.appcompat.app.ActionBar;
import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.FragmentTransaction;

import android.graphics.Color;
import android.graphics.drawable.Drawable;
import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import android.widget.LinearLayout;

public class MainActivity extends AppCompatActivity implements ActionBar.TabListener {
    ActionBar.Tab tabDog, tabCat, tabRabbit, tabHorse;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
//        setContentView(R.layout.activity_main);

        ActionBar bar = getSupportActionBar();
        bar.setNavigationMode(ActionBar.NAVIGATION_MODE_TABS);

        tabDog = bar.newTab();
        tabDog.setIcon(R.drawable.dog_icon); //그림 경로
        tabDog.setText("강아지");
        tabDog.setTabListener(this);
        bar.addTab(tabDog);

        tabCat = bar.newTab();
        tabCat.setIcon(R.drawable.cat_icon); //그림 경로
        tabCat.setText("고양이");
        tabCat.setTabListener(this);
        bar.addTab(tabCat);

        tabRabbit = bar.newTab();
        tabRabbit.setIcon(R.drawable.rabbit_icon); //그림 경로
        tabRabbit.setText("토끼");
        tabRabbit.setTabListener(this);
        bar.addTab(tabRabbit);

        tabHorse = bar.newTab();
        tabHorse.setIcon(R.drawable.horse_icon); //그림 경로
        tabHorse.setText("말");
        tabHorse.setTabListener(this);
        bar.addTab(tabHorse);
    }

    MyTabFragment myFrags[] = new MyTabFragment[4];

    @Override
    public void onTabSelected(ActionBar.Tab tab, FragmentTransaction ft) {
        MyTabFragment myTabFrag = null;

        if(myFrags[tab.getPosition()] == null) {
            myTabFrag = new MyTabFragment();
            Bundle data = new Bundle();
            data.putString("tabName", tab.getText().toString());
            myTabFrag.setArguments(data);
            myFrags[tab.getPosition()] = myTabFrag;
        }
        else {
            myTabFrag = myFrags[tab.getPosition()];
        }

        ft.replace(android.R.id.content, myTabFrag);
    }

    @Override
    public void onTabUnselected(ActionBar.Tab tab, FragmentTransaction ft) {

    }

    @Override
    public void onTabReselected(ActionBar.Tab tab, FragmentTransaction ft) {

    }

    public static class MyTabFragment extends androidx.fragment.app.Fragment {
        String tabName;

        @Override
        public void onCreate(@Nullable Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            Bundle data = getArguments();
            tabName = data.getString("tabName");
        }
        public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
            View myView = inflater.inflate(R.layout.activity_main, null);
            ImageView imageView = (ImageView) myView.findViewById(R.id.imageView);

            if(tabName == "강아지") imageView.setImageResource(R.drawable.dog); //그림 경로
            if(tabName == "고양이") imageView.setImageResource(R.drawable.cat); //그림 경로
            if(tabName == "토끼") imageView.setImageResource(R.drawable.rabbit); //그림 경로
            if(tabName == "말") imageView.setImageResource(R.drawable.horse); //그림 경로
            return myView;
        }
    }
}
```
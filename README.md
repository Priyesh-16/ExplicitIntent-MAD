# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
MainActivity.java

package com.example.explicit;

import android.app.Activity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

        EditText numberInput = findViewById(R.id.numberInput);
        Button factorialButton = findViewById(R.id.factorialButton);

        factorialButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String number = numberInput.getText().toString();

                Intent intent = new Intent(
                        MainActivity.this,
                        SecondActivity.class
                );

                intent.putExtra("number", number);

                startActivity(intent);
            }
        });
    }
}

activity_main.xml

<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center">

    <EditText
        android:id="@+id/numberInput"
        android:layout_width="250dp"
        android:layout_height="wrap_content"
        android:hint="Enter a number"
        android:inputType="number" />

    <Button
        android:id="@+id/factorialButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="FACTORIAL"
        android:layout_marginTop="30dp" />

</LinearLayout>

SecondActivity.java

package com.example.explicit;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class SecondActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_second);

        TextView resultText = findViewById(R.id.resultText);
        Button backButton = findViewById(R.id.backButton);

        String numberString = getIntent().getStringExtra("number");

        int number = Integer.parseInt(numberString);

        long factorial = 1;

        for (int i = 1; i <= number; i++) {
            factorial = factorial * i;
        }

        resultText.setText(
                "Factorial of " + number + " = " + factorial
        );

        backButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                finish();
            }
        });
    }
}

activity_second.xml

<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center">

    <TextView
        android:id="@+id/resultText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial Result"
        android:textSize="22sp" />

    <Button
        android:id="@+id/backButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="BACK"
        android:layout_marginTop="30dp" />

</LinearLayout>


```

## OUTPUT
<img width="1918" height="1198" alt="Screenshot 2026-07-31 090837" src="https://github.com/user-attachments/assets/82cf6a0a-a6ea-4c97-aeb9-dbd1a1a0af07" />

<img width="1918" height="1198" alt="Screenshot 2026-07-31 090846" src="https://github.com/user-attachments/assets/87fa4d1b-dd67-44ae-b79b-9618917d58b6" />


## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.



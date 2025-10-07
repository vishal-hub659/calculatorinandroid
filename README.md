# Ex_5_-Develop a simple calculator using android studio.
Develop a program to create a simple calculator using Android Studio.

## AIM:
To develop a program to create a simple calculator using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min. required Artic Fox)


## ALGORITHM:
Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as SMSIntent and click Next.

Step 3: Select the Minimum SDK below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally, click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Perform the Calculator Operation in MainActivity.java

Step 7: Save and run the application.


## Program:
``` 
Program to create simple calculator using Android Studio.


Developed by: Vishal S
RegisterNumber: 212224040365
```

## MainActivity.java:
```
package com.example.calculatorapp;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    EditText etNum1, etNum2;
    TextView tvResult;
    Button btnAdd, btnSub, btnMul, btnDiv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        etNum1 = findViewById(R.id.etNum1);
        etNum2 = findViewById(R.id.etNum2);
        tvResult = findViewById(R.id.tvResult);

        btnAdd = findViewById(R.id.btnAdd);
        btnSub = findViewById(R.id.btnSub);
        btnMul = findViewById(R.id.btnMul);
        btnDiv = findViewById(R.id.btnDiv);

        btnAdd.setOnClickListener(v -> calculate("+"));
        btnSub.setOnClickListener(v -> calculate("-"));
        btnMul.setOnClickListener(v -> calculate("*"));
        btnDiv.setOnClickListener(v -> calculate("/"));
    }

    private void calculate(String op) {
        String n1 = etNum1.getText().toString();
        String n2 = etNum2.getText().toString();

        if (n1.isEmpty() || n2.isEmpty()) {
            tvResult.setText("Please enter numbers");
            return;
        }

        double a = Double.parseDouble(n1);
        double b = Double.parseDouble(n2);
        double res = 0;

        switch (op) {
            case "+": res = a + b; break;
            case "-": res = a - b; break;
            case "*": res = a * b; break;
            case "/":
                if (b != 0) res = a / b;
                else { tvResult.setText("Cannot divide by 0"); return; }
                break;
        }
        tvResult.setText(n1 + " " + op + " " + n2 + " = " + res);
    }
}




```


## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="16dp"
    android:background="#FFF0F5">

    <!-- Title -->
    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Calculator"
        android:textSize="24sp"
        android:textStyle="bold"
        android:layout_marginBottom="20dp"/>

    <!-- First Number -->
    <EditText
        android:id="@+id/etNum1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:gravity="center"/>

    <!-- Second Number -->
    <EditText
        android:id="@+id/etNum2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:gravity="center"/>

    <!-- Result -->
    <TextView
        android:id="@+id/tvResult"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Result"
        android:textSize="18sp"
        android:gravity="center"
        android:layout_marginTop="20dp"
        android:background="#FFFFFF"
        android:padding="10dp"/>

    <!-- Buttons -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center"
        android:layout_marginTop="20dp">

        <Button
            android:id="@+id/btnAdd"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="+"
            android:backgroundTint="#FF6666"
            android:layout_margin="5dp"/>

        <Button
            android:id="@+id/btnMul"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="x"
            android:backgroundTint="#FF6666"
            android:layout_margin="5dp"/>

        <Button
            android:id="@+id/btnSub"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="-"
            android:backgroundTint="#FF6666"
            android:layout_margin="5dp"/>

        <Button
            android:id="@+id/btnDiv"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="/"
            android:backgroundTint="#FF6666"
            android:layout_margin="5dp"/>
    </LinearLayout>
</LinearLayout>



```

## Output:

![WhatsApp Image 2025-10-07 at 14 30 47_206eec5d](https://github.com/user-attachments/assets/061b6ff4-fbcd-4b7a-a0cd-1517f6134299)



## Result:
Thus a Simple Android Application to create a calculator using Android Studio was developed and executed successfully.

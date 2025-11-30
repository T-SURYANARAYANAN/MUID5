# Ex.No:5 Develop a program to create a simple calculator using android studio.
## AIM:
To Develop a program to create a simple calculator using android studio.

## EQUIPMENTS REQUIRED:
Android Studio(Min. required Artic Fox)

## ALGORITHM:
1. Initialize Project: Create a new Android Studio project using the Empty Views Activity template.

2. Design Layout: Finish activity_main.xml ensuring unique IDs for your two inputs, result display, and four operator buttons.

3. Link UI Elements: In MainActivity.java, use findViewById() to connect all XML elements to corresponding Java variables.

4. Create Logic Method: Define a single Java function (e.g., calculateAndDisplay) that takes the required operator as input.

5. Attach Listeners: Set up OnClickListener for all four buttons, each calling the logic method with its specific operator character.

6. Perform Calculation: Inside the logic method, convert inputs to numbers and use a switch statement to execute the correct math (and check for divide-by-zero).

7.Display Output: Update the tvResult TextView with the final answer or show an appropriate error message using Toast.

## PROGRAM:
```txt
Program to print the text create your own content providers to get contacts details.
Developed by: SURYANARAYANAN T
Registeration Number : 212224040341
```
### MainActivity.java
```java
package com.example.calculator;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

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
### activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<!--<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"-->
<!--    xmlns:app="http://schemas.android.com/apk/res-auto"-->
<!--    xmlns:tools="http://schemas.android.com/tools"-->
<!--    android:id="@+id/main"-->
<!--    android:layout_width="match_parent"-->
<!--    android:layout_height="match_parent"-->
<!--    tools:context=".MainActivity"/>-->
<!--    <?xml version="1.0" encoding="utf-8"?>-->
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:background="#F4E3FF"
android:gravity="center"
android:orientation="vertical"
android:padding="16dp">

<!-- Title -->
<TextView
    android:id="@+id/tvTitle"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginBottom="20dp"
    android:text="Calculator"
    android:textSize="24sp"
    android:textStyle="bold" />

<!-- First Number -->
<EditText
    android:id="@+id/etNum1"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:gravity="center"
    android:hint="Enter first number"
    android:inputType="numberDecimal" />

<!-- Second Number -->
<EditText
    android:id="@+id/etNum2"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:gravity="center"
    android:hint="Enter second number"
    android:inputType="numberDecimal" />

<!-- Result -->
<TextView
    android:id="@+id/tvResult"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_marginTop="20dp"
    android:background="#FFFEFE"
    android:gravity="center"
    android:padding="10dp"
    android:text="Result"
    android:textSize="18sp" />

<!-- Buttons -->
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_marginTop="20dp"
    android:gravity="center"
    android:orientation="horizontal">

    <Button
        android:id="@+id/btnAdd"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:backgroundTint="#050505"
        android:text="+" />

    <Button
        android:id="@+id/btnMul"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:backgroundTint="#1E756E"
        android:text="x" />

    <Button
        android:id="@+id/btnSub"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:backgroundTint="#FF0000"
        android:text="-"
        android:textSize="20sp" />

    <Button
        android:id="@+id/btnDiv"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="5dp"
        android:backgroundTint="#006DFF"
        android:text="/" />
</LinearLayout>
</LinearLayout>
```
## OUTPUT
### MainActivity.java
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0948ca3e-4716-4704-971c-73d14edea7cf" />

### activity_main.xml
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/73e23df4-e5e1-468b-bf4b-af02c72a949e" />

### Execution
<img width="374" height="779" alt="image" src="https://github.com/user-attachments/assets/5682bf07-c8f9-443d-83ed-50c8a5209157" />

## RESULT
Thus a Simple Android Application to create your own simple calculator using Android Studio is developed and executed successfully.

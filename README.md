# DEVELOPING-AN-ANDROID-APPLICATION-TO-PERFORM-MATHEMATICAL-OPERATION.-

## AIM:
To develop an android application to perform mathematical operation.

## APPARATUS REQUIRED:
ØComputer
ØAndroid studio software


## THEORY:
The platform uses signed two's complement integer arithmetic with int and long primitive types. The developer should choose the primitive type to ensure that arithmetic operations consistently produce correct results, which in some cases means the operations will not overflow the range of values of the computation. The best practice is to choose the primitive type and algorithm to avoid overflow. In cases where the size is int or long and overflow errors need to be detected, the methods add, subtract multiply, and throw an Arithmetic exception when the results overflow. For other arithmetic operations such as divide, absolute value, increment by one, decrement by one, and negation, overflow occurs only with a specific minimum or maximum value and should be checked against the minimum or maximum as appropriate.



## PROCEDURE:
1. Open Android Studio and then click on File -> New -> New project. 2. Then type the application name as “ex.no.1″ and click Next.
3. Then select the Minimum SDK as shown below and click next. 4. Then select the Empty Activity and click next.
5. Finally click Finish.
6. Click on app -> java -> com.example -> MainActivity.java
7. Now click on Text and type the program, so now the programming part of the main activity is completed.
8. Click on app -> res -> layout -> activity_main.xml.
9. Now click on Text and type the program, so now the designing part of Activity main is also completed.
10. Select the suitable available device to display the output. 11. Now run the application to see the output. 


## PROGRAM:

 package com.example.myapplication3;
 import android.os.Bundle;
 import android.view.View;
 import android.widget.Button;
 import android.widget.EditText;
 import android.widget.TextView;
 import android.widget.Toast;
 import androidx.activity.EdgeToEdge;
 import androidx.appcompat.app.AppCompatActivity;
 import androidx.core.graphics.Insets;
 import androidx.core.view.ViewCompat;
 import androidx.core.view.WindowInsetsCompat;
 public class MainActivity extends AppCompatActivity implements View.OnClickListener 
{
    Button buttonAdd, buttonSub, buttonMul, buttonDiv;
    EditText editTextN1, editTextN2;
    TextView textView;
    int num1, num2;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        buttonAdd = findViewById(R.id.btn_add);
        buttonSub = findViewById(R.id.btn_sub);
        buttonMul = findViewById(R.id.btn_mul);
        buttonDiv = findViewById(R.id.btn_div);
        editTextN1 = findViewById(R.id.number1);
        editTextN2 = findViewById(R.id.number2);
        textView = findViewById(R.id.answer);
        buttonAdd.setOnClickListener(this);
        buttonSub.setOnClickListener(this);
        buttonMul.setOnClickListener(this);
        buttonDiv.setOnClickListener(this);
    }
    public int getIntFromEditText(EditText editText) {
        if (editText.getText().toString().equals("")) {
            Toast.makeText(this, "Enter number", Toast.LENGTH_SHORT).show();
            return 0;
        } else
            return Integer.parseInt(editText.getText().toString());
    }
    @Override
    public void onClick(View view) {
        num1 = getIntFromEditText(editTextN1);
        num2 = getIntFromEditText(editTextN2);
        int id = view.getId(); // Get the ID once
        if (id == R.id.btn_add) {
            textView.setText("Answer = " + (num1 + num2));
        } else if (id == R.id.btn_sub) {
            textView.setText("Answer = " + (num1 - num2));
        } else if (id == R.id.btn_mul) {
            textView.setText("Answer = " + (num1 * num2));
        } else if (id == R.id.btn_div) {
            // Ensure num2 is not zero to avoid division by zero error
            if
            (num2 == 0) {
                Toast.makeText(this, "Cannot divide by zero", 
Toast.LENGTH_SHORT).show();
                textView.setText("Answer = Error");
            } else {
                textView.setText("Answer = " + ((float) num1 / (float) num2));
            }
        }
    }
 }
activity_main.xml
<?xml version="1.0" encoding="utf-8"?>

 

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android" android:orientation="vertical" android:layout_width="match_parent" android:layout_height="match_parent" android:padding="16dp">

 

<EditText android:id="@+id/num1" android:hint="Enter Number 1" android:layout_width="match_parent" android:layout_height="wrap_content"

android:inputType="numberDecimal"/>

 

<EditText android:id="@+id/num2" android:hint="Enter Number 2" android:layout_width="match_parent" android:layout_height="wrap_content"

android:inputType="numberDecimal"/>

 

<LinearLayout android:orientation="horizontal" android:layout_width="match_parent" android:layout_height="wrap_content">

 

<Button android:id="@+id/addBtn" android:text="+" android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>

 

<Button android:id="@+id/subBtn" android:text="-" android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>

 

<Button android:id="@+id/mulBtn" android:text="*" android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>

 

<Button android:id="@+id/divBtn" android:text="/" android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>

 

</LinearLayout>

 

<TextView android:id="@+id/result" android:text="Result:" android:layout_width="match_parent" android:layout_height="wrap_content"

android:paddingTop="10dp"/>

 

</LinearLayout>

## OUTPUT:
<img width="1434" height="729" alt="Screenshot 2026-02-27 112900" src="https://github.com/user-attachments/assets/09e172c3-9a99-4850-a18f-48aeca66456f" />




## RESULT:
Thus, the Android app for basic operations (addition, subtraction, multiplication, and division) is developed and the output is verified.


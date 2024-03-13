# Ex.No:3b To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by:Ranjeeth B K
Registeration Number :212222040132
*/
```
#In Mainactivity,java
```java
package com.example.explicitintent;

// MainActivity.java
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    private EditText numberEditText;
    private Button factorialButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        numberEditText = findViewById(R.id.numberEditText);
        factorialButton = findViewById(R.id.factorialButton);

        factorialButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                int number = Integer.parseInt(numberEditText.getText().toString());
                int factorial = calculateFactorial(number);

                Intent intent = new Intent(MainActivity.this, ResultActivity.class);
                intent.putExtra("factorial", factorial);
                startActivity(intent);
            }
        });
    }

    private int calculateFactorial(int n) {
        if (n == 0)
            return 1;
        else
            return n * calculateFactorial(n - 1);
    }
}
```
```


## OUTPUT
![image](https://github.com/RANJEETH17/ExplicitIntent-MAD/assets/120718823/3f12a7ba-ee39-4494-9468-2ff751ec6da4)
![image](https://github.com/RANJEETH17/ExplicitIntent-MAD/assets/120718823/06fb7f1b-3de8-4446-9b96-94b736f0761e)
![image](https://github.com/RANJEETH17/ExplicitIntent-MAD/assets/120718823/49dbd6e1-4f94-4613-871d-2d3355c61bae)







## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.



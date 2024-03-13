# Ex.No:3b To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Step 1: Create a New Project in Android Studio

Step 2: Working with the activity_main.xml File

Step 3: Working with the MainActivity File

Step 4: Working with the activity_main2.xml File

Step 5: Working with the resultctivity File

Step 6: Working with the manifest File



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
# In activity_main.xml
```xml
<!-- res/layout/activity_main.xml -->
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center">

    <EditText
        android:id="@+id/numberEditText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="Enter a number"
        android:inputType="number"/>

    <Button
        android:id="@+id/factorialButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Calculate Factorial"/>

</LinearLayout>
```
# in resultactivity.java
```
package com.example.explicitintent;

// ResultActivity.java
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class ResultActivity extends AppCompatActivity {
    private TextView resultTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_result);

        resultTextView = findViewById(R.id.resultTextView);

        Intent intent = getIntent();
        int factorial = intent.getIntExtra("factorial", 0);

        resultTextView.setText("Factorial: " + factorial);
    }
}
```
# In activity_result.xml
```xml
<!-- res/layout/activity_result.xml -->
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center">

    <TextView
        android:id="@+id/resultTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="20sp"/>

</LinearLayout>


```
# in Androidmanifest.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    package="com.example.explicitintent">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Explicitintent"
        tools:targetApi="31">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <!-- Declaration for SecondActivity -->
        <activity android:name=".ResultActivity" />
    </application>

</manifest>
```



## OUTPUT
![image](https://github.com/RANJEETH17/ExplicitIntent-MAD/assets/120718823/3f12a7ba-ee39-4494-9468-2ff751ec6da4)
![image](https://github.com/RANJEETH17/ExplicitIntent-MAD/assets/120718823/06fb7f1b-3de8-4446-9b96-94b736f0761e)
![image](https://github.com/RANJEETH17/ExplicitIntent-MAD/assets/120718823/49dbd6e1-4f94-4613-871d-2d3355c61bae)







## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.



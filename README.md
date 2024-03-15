# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
```
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as ExplicitIntent and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display factorial number using Explicit Intents in MainActivity file.

Step 7: Save and run the application.
```



## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by:ch.geethika
Registeration Number :212221040032
*/
```
## Activity_main.xml
```

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editTextText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:fontFamily="sans-serif-black"
        android:hint="ENTER THE NUMBER"
        android:inputType="text"

        android:textSize="24sp"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.496"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.271" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial"
        android:textColor="#353333"
        android:textSize="34sp"
        app:iconTint="#AE6525"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.468"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.582" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
## Activity_main2.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-black"
        android:text="TextView"
        android:textSize="48sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.367" />
</androidx.constraintlayout.widget.ConstraintLayout>

```
## MainActivity.java
```
package com.example.explicitintent;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    EditText edt1;
    Button btn1;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        edt1 = findViewById(R.id.editTextText);
        btn1 = findViewById(R.id.button);
        Intent i = new Intent(MainActivity.this,MainActivity2.class);
        btn1.setOnClickListener(View->{
            i.putExtra("number",edt1.getText().toString());
            startActivity(i);
        });

    }
}

```
## Main Activity2.java
```
package com.example.explicitintent;
import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;

import android.os.Bundle;

import android.view.View;
import android.widget.TextView;


public class MainActivity2 extends AppCompatActivity {
    TextView txt2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        Bundle b = getIntent().getExtras();

        int no = Integer.parseInt(b.getString("number"));
        long f=1;

        for(int i=no; i>0; i--)
        {
            f = f * i;
        }

        txt2 = findViewById(R.id.textView);
        txt2.setText("Factorial of " + no + " is " + f);
    }
}


```
## OUTPUT
![Screenshot (317)](https://github.com/chgeethika/ExplicitIntent-MAD/assets/142209368/6a49ff47-795b-4ad5-907e-74fa0980b002)
![Screenshot (318)](https://github.com/chgeethika/ExplicitIntent-MAD/assets/142209368/8f25464c-2ac4-4bf8-8ef1-3379d247a26d)
![Screenshot (319)](https://github.com/chgeethika/ExplicitIntent-MAD/assets/142209368/8908d15a-e8d7-4544-aa69-9743a544f96f)







## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.



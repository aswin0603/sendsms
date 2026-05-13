
# Ex.No:6 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by: Aswin B
Registeration Number : 212224110007
*/
```
### activity_main.xml:
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Experiment 03 - Send SMS"
        android:textSize="22sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.19" />

    <EditText
        android:id="@+id/etPhone"
        android:layout_width="295dp"
        android:layout_height="40dp"
        android:layout_marginTop="84dp"
        android:ems="10"
        android:inputType="text"
        android:hint="Enter the Number"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView"
        tools:ignore="MissingConstraints" />

    <EditText
        android:id="@+id/etMessage"
        android:layout_width="295dp"
        android:layout_height="40dp"
        android:layout_marginTop="36dp"
        android:ems="10"
        android:inputType="text"
        android:hint="Enter the Message"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/etPhone"
        tools:ignore="MissingConstraints" />

    <Button
        android:id="@+id/btnSend"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="64dp"
        android:text="Send SMS"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/etMessage" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### MainActivity.java
```java
package com.example.sendsms;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    EditText etMessage,etPhone;
    Button btnSend;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        etMessage=findViewById(R.id.etMessage);
        etPhone=findViewById(R.id.etPhone);
        btnSend=findViewById(R.id.btnSend);
        btnSend.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                sendSMS();
            }
        });
    }

    private void sendSMS() {
        String message=etMessage.getText().toString();
        String phoneNo=etPhone.getText().toString();
        Intent intent=new Intent(Intent.ACTION_VIEW);
        intent.setData(Uri.parse("sms:"+phoneNo));
        intent.putExtra("sms_body",message);
        startActivity(intent);
    }
}
```

## OUTPUT:
<img width="1920" height="1200" alt="Screenshot (142)" src="https://github.com/user-attachments/assets/87d1f3c5-8863-45c1-a161-d3db9a39b51b" />
<img width="1920" height="1200" alt="Screenshot (143)" src="https://github.com/user-attachments/assets/3acf3e2c-74f3-432e-b0d2-9a6c64b20c37" />
<img width="1920" height="1200" alt="Screenshot (144)" src="https://github.com/user-attachments/assets/927f645e-b2a5-4e96-825f-ed99072786fd" />






## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.

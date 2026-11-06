
# Ex.No:3 Design an android application Send SMS using Intent.


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
Developed by: Vikaskumar M
Registeration Number : 212224220122
*/
```
MainActivity.java
```python
package com.example.exp_03;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.widget.EditText;
import android.widget.Button;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    EditText phoneBox, messageBox;
    Button sendBtn;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        phoneBox = findViewById(R.id.etNumber);
        messageBox = findViewById(R.id.etMessage);
        sendBtn = findViewById(R.id.btnSend);
        sendBtn.setOnClickListener(v -> {
            String phoneNo = phoneBox.getText().toString();
            String message = messageBox.getText().toString();
            Uri uri = Uri.parse("smsto:" + phoneNo);
            Intent intent = new Intent(Intent.ACTION_SENDTO, uri);
            intent.putExtra("sms_body", message);
            startActivity(intent);
        });
    }
}
```
activity_main.xml
```python
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="25dp"
    android:background="#F2F5FF">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="SMS APPLICATION"
        android:textSize="26sp"
        android:textStyle="bold"
        android:textColor="#303F9F"
        android:layout_marginBottom="35dp"/>

    <EditText
        android:id="@+id/etNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Mobile Number"
        android:inputType="phone"
        android:padding="15dp"
        android:backgroundTint="#303F9F"/>

    <EditText
        android:id="@+id/etMessage"
        android:layout_width="match_parent"
        android:layout_height="130dp"
        android:hint="Enter Your Message"
        android:inputType="textMultiLine"
        android:gravity="top"
        android:padding="15dp"
        android:layout_marginTop="20dp"
        android:backgroundTint="#303F9F"/>

    <Button
        android:id="@+id/btnSend"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="SEND SMS"
        android:textSize="18sp"
        android:textStyle="bold"
        android:backgroundTint="#303F9F"
        android:textColor="#FFFFFF"
        android:layout_marginTop="30dp"/>

</LinearLayout>

```
## OUTPUT

<img width="1222" height="688" alt="Screenshot 2026-11-06 183512" src="https://github.com/user-attachments/assets/73efff5c-ee3e-4a90-9b4e-b5304a59224d" />

<img width="1218" height="684" alt="Screenshot 2026-11-06 183628" src="https://github.com/user-attachments/assets/e8e4f9d9-00a6-47ed-90e4-0a0ac1e849bf" />

<img width="313" height="625" alt="Screenshot 2026-11-06 183803" src="https://github.com/user-attachments/assets/10d5020b-f858-4161-836e-c060a2d45d17" />
<img width="336" height="619" alt="Screenshot 2026-11-06 183845" src="https://github.com/user-attachments/assets/d7155795-9904-423c-a987-3ed9738352c3" />

## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.

# App-development-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Onboarding and Environment Setup</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: #e9f1ef;
    padding: 25px;
}

.container {
    max-width: 1200px;
    margin: auto;
    background: white;
    
    package com.example.backendapp;

import android.os.Bundle;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

import org.json.JSONObject;

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;
import java.net.HttpURLConnection;
import java.net.URL;

public class MainActivity extends AppCompatActivity {

    Button getButton, postButton;
    TextView resultText;

    String apiUrl =
    "https://jsonplaceholder.typicode.com/posts";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        getButton = findViewById(R.id.getButton);
        postButton = findViewById(R.id.postButton);
        resultText = findViewById(R.id.resultText);

        getButton.setOnClickListener(v -> getData());

        postButton.setOnClickListener(v -> postData());
    }

    // GET API
    private void getData() {

        resultText.setText("Loading...");

        new Thread(() -> {

            HttpURLConnection connection = null;

            try {
                URL url = new URL(apiUrl);
                connection = (HttpURLConnection)
                        url.openConnection();

                connection.setRequestMethod("GET");
                connection.setConnectTimeout(10000);
                connection.setReadTimeout(10000);

                int responseCode =
                        connection.getResponseCode();

                if (responseCode == 200) {

                    BufferedReader reader =
                            new BufferedReader(
                            new InputStreamReader(
                            connection.getInputStream()));

                    StringBuilder response =
                            new StringBuilder();

                    String line;

                    while ((line = reader.readLine()) != null) {
                        response.append(line);
                    }

                    reader.close();

                    JSONObject json =
                            new JSONObject(
                            response.toString().substring(1,
                            response.toString().indexOf("}") + 1));

                    String title = json.getString("title");
                    String body = json.getString("body");

                    runOnUiThread(() ->
                            resultText.setText(
                            "Title: " + title +
                            "\n\nBody: " + body));

                } else {
                    throw new Exception(
                            "Server Error: " + responseCode);
                }

            } catch (Exception e) {

                runOnUiThread(() ->
                        resultText.setText(
                        "Error: " + e.getMessage()));

            } finally {
                if (connection != null) {
                    connection.disconnect();
                }
            }

        }).start();
    }

    // POST API
    private void postData() {

        new Thread(() -> {

            HttpURLConnection connection = null;

            try {

                URL url = new URL(apiUrl);

                connection = (HttpURLConnection)
                        url.openConnection();

                connection.setRequestMethod("POST");
                connection.setDoOutput(true);

                connection.setRequestProperty(
                        "Content-Type",
                        "application/json; charset=UTF-8");

                JSONObject json = new JSONObject();

                json.put("title", "Android App");
                json.put("body", "Backend API Integration");
                json.put("userId", 1);

                OutputStream os =
                        connection.getOutputStream();

                os.write(json.toString().getBytes("UTF-8"));
                os.close();

                int responseCode =
                        connection.getResponseCode();

                runOnUiThread(() -> {
                    if (responseCode == 201) {
                        resultText.setText(
                                "Data sent successfully!");
                    } else {
                        resultText.setText(
                                "Error Code: " + responseCode);
                    }
                });

            } catch (Exception e) {

                runOnUiThread(() ->
                        resultText.setText(
                        "Error: " + e.getMessage()));

            } finally {
                if (connection != null) {
                    connection.disconnect();
                }
            }

        }).start();
    }
}: 40px;
    border-radius: 15px;
    border: 3px solid #168b75;
    box-shadow: 0 5px 20px #aaa;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 2px solid #168b75;
    padding-bottom: 15px;
}

.header h1 {
    color: #00695c;
    font-size: 32px;
}

.logo {
    text-align: right;
    color: #075d51;
}

.logo h2 {
    color: #087c68;
}

.logo p {
    margin-top: 5px;
}

.timeline {
    text-align: right;
    margin: 15px 0;
    color: #333;
}

.task {
    color: #683b87;
    font-size: 22px;
    font-weight: bold;
}

h3 {
    color: #087c68;
    margin: 18px 0 10px;
}

p, li {
    font-size: 17px;
    line-height: 1.7;
    color: #333;
}

ul {
    padding-left: 25px;
}

.section {
    margin-top: 20px;
}

.day {
    color: #087c68;
    font-weight: bold;
    font-size: 19px;
}

.content {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 25px;
    margin-top: 20px;
}

.illustration {
    background: linear-gradient(135deg, #d8f3ec, #e7e6fa);
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 100px;
    min-height: 300px;
}

footer {
    text-align: center;
    margin-top: 25px;
    padding: 12px;
    background: #e0f2ed;
    color: #087c68;
    border-radius: 8px;
}

@media(max-width: 700px) {
    .container {
        padding: 20px;
    }

    .header {
        flex-direction: column;
        gap: 15px;
    }

    .header h1 {
        font-size: 25px;
        text-align: center;
    }

    .logo {
        text-align: center;
    }

    .content {
        grid-template-columns: 1fr;
    }

    .illustration {
        min-height: 180px;
        font-size: 70px;
    }
}
</style>
</head>

<body>

<div class="container">

    <div class="header">
        <h1>Onboarding and Environment Setup</h1>

        <div class="logo">
            <h2>✦ ApexPlanet</h2>
            <p>Software Pvt Ltd</p>
        </div>
    </div>

    <div class="timeline">
        <h3>TimeLine : 9 Days</h3>
        <div class="task">TASK - 1</div>
    </div>

    <div class="content">

        <div>

            <h3>Objective :</h3>
            <ul>
                <li>Complete onboarding and setup development environment.</li>
            </ul>

            <h3>Activities :</h3>

            <div class="section">
                <p class="day">1. Days 1-2 : Onboarding</p>
                <ul>
                    <li>Attend orientation sessions to understand company culture and internship goals.</li>
                    <li>Introduction to team members and mentors.</li>
                </ul>
            </div>

            <div class="section">
                <p class="day">2. Days 3-5 : Environment Setup</p>
                <ul>
                    <li>Install and configure Android Studio.</li>
                    <li>Install necessary SDKs and tools (e.g., Java/Kotlin, Gradle).</li>
                    <li>Set up Git and create a GitHub account.</li>
                    <li>Familiarize with Android Studio interface and basic features.</li>
                </ul>
            </div>

            <div class="section">
                <p class="day">3. Days 6-9 : Basics of Android Development</p>
                <ul>
                    <li>Review Android development fundamentals (activities, fragments, layouts).</li>
                    <li>Complete introductory tutorials and small projects in Android Studio.</li>
                </ul>
            </div>

            <h3>Deliverables :</h3>
            <ul>
                <li>GitHub repository initialized with basic setup and initial tutorials.</li>
                <li>LinkedIn post summarizing the onboarding process and environment setup.</li>
            </ul>

        </div>

        <div class="illustration">
            📱 🤖
        </div>

    </div>

    <footer>
        ApexPlanet Software Pvt Ltd | Task 1
    </footer>

</div>

</body>
</html>
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F4F7F6">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="20dp">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Backend Integration and API Development"
            android:textColor="#00695C"
            android:textSize="25sp"
            android:textStyle="bold"
            android:gravity="center"
            android:padding="12dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Objective:"
            android:textColor="#00796B"
            android:textSize="20sp"
            android:textStyle="bold"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Integrate backend services and APIs into the app."
            android:textSize="16sp"
            android:textColor="#333333"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Activities:"
            android:textColor="#00796B"
            android:textSize="20sp"
            android:textStyle="bold"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="1. Days 19-21 : Backend Services Introduction"
            android:textColor="#00695C"
            android:textStyle="bold"
            android:textSize="17sp"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Learn about backend services and REST APIs.\n• Explore tools like Firebase for backend integration."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="2. Days 22-24 : API Integration"
            android:textColor="#00695C"
            android:textStyle="bold"
            android:textSize="17sp"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Set up API calls to fetch and send data.\n• Implement data handling and parsing in Android Studio."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="3. Days 25-27 : Error Handling and Debugging"
            android:textColor="#00695C"
            android:textStyle="bold"
            android:textSize="17sp"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Implement error handling for API requests.\n• Debug and resolve any issues with data integration."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Deliverables:"
            android:textColor="#00796B"
            android:textSize="20sp"
            android:textStyle="bold"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• GitHub repository updated with backend integration and API functionality.\n\n• LinkedIn post detailing the backend integration process and challenges faced."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

    </
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F4F7F6">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="20dp">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Backend Integration and API Development"
            android:textColor="#00695C"
            android:textSize="25sp"
            android:textStyle="bold"
            android:gravity="center"
            android:padding="12dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Objective:"
            android:textColor="#00796B"
            android:textSize="20sp"
            android:textStyle="bold"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Integrate backend services and APIs into the app."
            android:textSize="16sp"
            android:textColor="#333333"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Activities:"
            android:textColor="#00796B"
            android:textSize="20sp"
            android:textStyle="bold"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="1. Days 19-21 : Backend Services Introduction"
            android:textColor="#00695C"
            android:textStyle="bold"
            android:textSize="17sp"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Learn about backend services and REST APIs.\n• Explore tools like Firebase for backend integration."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="2. Days 22-24 : API Integration"
            android:textColor="#00695C"
            android:textStyle="bold"
            android:textSize="17sp"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Set up API calls to fetch and send data.\n• Implement data handling and parsing in Android Studio."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="3. Days 25-27 : Error Handling and Debugging"
            android:textColor="#00695C"
            android:textStyle="bold"
            android:textSize="17sp"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• Implement error handling for API requests.\n• Debug and resolve any issues with data integration."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Deliverables:"
            android:textColor="#00796B"
            android:textSize="20sp"
            android:textStyle="bold"
            android:paddingTop="12dp"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="• GitHub repository updated with backend integration and API functionality.\n\n• LinkedIn post detailing the backend integration process and challenges faced."
            android:textColor="#333333"
            android:textSize="16sp"
            android:padding="8dp"/>

    </LinearLayout>
</ScrollView>

package com.example.myapp

import android.Manifest
import android.app.NotificationChannel
import android.app.NotificationManager
import android.content.Context
import android.content.pm.PackageManager
import android.os.Build
import android.os.Bundle
import android.widget.*
import android.util.Log
import androidx.appcompat.app.AppCompatActivity
import androidx.core.app.ActivityCompat
import androidx.core.app.NotificationCompat
import androidx.core.app.NotificationManagerCompat
import com.google.firebase.auth.FirebaseAuth

class MainActivity : AppCompatActivity() {

    private lateinit var auth: FirebaseAuth

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        auth = FirebaseAuth.getInstance()

        val email = findViewById<EditText>(R.id.email)
        val password = findViewById<EditText>(R.id.password)
        val loginBtn = findViewById<Button>(R.id.loginBtn)
        val registerBtn = findViewById<Button>(R.id.registerBtn)
        val notifyBtn = findViewById<Button>(R.id.notifyBtn)

        // User Login
        loginBtn.setOnClickListener {
            val userEmail = email.text.toString().trim()
            val userPassword = password.text.toString()

            if (userEmail.isEmpty() || userPassword.isEmpty()) {
                Toast.makeText(this, "Enter all details", Toast.LENGTH_SHORT).show()
            } else {
                auth.signInWithEmailAndPassword(userEmail, userPassword)
                    .addOnCompleteListener { task ->
                        if (task.isSuccessful) {
                            Toast.makeText(this, "Login Successful", Toast.LENGTH_SHORT).show()
                        } else {
                            Toast.makeText(this, "Login Failed", Toast.LENGTH_SHORT).show()
                        }
                    }
            }
        }

        // User Registration
        registerBtn.setOnClickListener {
            val userEmail = email.text.toString().trim()
            val userPassword = password.text.toString()

            if (userEmail.isEmpty() || userPassword.length < 6) {
                Toast.makeText(this, "Enter valid details (6+ character password)", Toast.LENGTH_SHORT).show()
            } else {
                auth.createUserWithEmailAndPassword(userEmail, userPassword)
                    .addOnCompleteListener { task ->
                        val message = if (task.isSuccessful) {
                            "Registration Successful"
                        } else {
                            "Registration Failed"
                        }
                        Toast.makeText(this, message, Toast.LENGTH_SHORT).show()
                    }
            }
        }

        // Push Notification
        notifyBtn.setOnClickListener {
            showNotification()
        }

        // Performance Monitoring
        checkPerformance()
    }

    private fun showNotification() {
        val channelId = "my_channel"

        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
            val channel = NotificationChannel(
                channelId,
                "App Notifications",
                NotificationManager.IMPORTANCE_DEFAULT
            )

            val manager = getSystemService(
                Context.NOTIFICATION_SERVICE
            ) as NotificationManager

            manager.createNotificationChannel(channel)
        }

        if (Build.VERSION.SDK_INT >= 33 &&
            ActivityCompat.checkSelfPermission(
                this,
                Manifest.permission.POST_NOTIFICATIONS
            ) != PackageManager.PERMISSION_GRANTED
        ) {
            ActivityCompat.requestPermissions(
                this,
                arrayOf(Manifest.permission.POST_NOTIFICATIONS),
                100
            )
            return
        }

        val notification = NotificationCompat.Builder(this, channelId)
            .setSmallIcon(android.R.drawable.ic_dialog_info)
            .setContentTitle("Welcome")
            .setContentText("Your notification is working!")
            .setPriority(NotificationCompat.PRIORITY_DEFAULT)
            .build()

        NotificationManagerCompat.from(this).notify(1, notification)
    }

    private fun checkPerformance() {
        val startTime = System.currentTimeMillis()

        // App operations

        val endTime = System.currentTimeMillis()

        Log.d("Performance", "Execution Time: ${endTime - startTime} ms")
    }
}

name: Android Build

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '17'

      - uses: gradle/actions/setup-gradle@v4

      - name: Build App
        run: |
          chmod +x gradlew
          ./gradlew assembleDebug test
          

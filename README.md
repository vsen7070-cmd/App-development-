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
    padding: 40px;
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


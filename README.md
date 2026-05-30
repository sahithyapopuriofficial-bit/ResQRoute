# ResQRoute
<h1 align="center">ResQRoute</h1>
<p align="center">
  <strong>Every Second Counts. Every Life Matters.</strong>
</p>

<p align="center">
  <img width="565" height="468" 
       alt="ResqRoute Image"
       src="https://github.com/user-attachments/assets/8f64a8a2-a30b-4749-935e-bb88151968b8" />
</p>

# Emergency Response & Smart Route Optimization Platform with AI
ResQRoute is a smart, location-aware emergency response system designed to reduce delays in road accident assistance by instantly connecting victims to the nearest and most suitable emergency services. It acts as a digital bridge between accident detection, emergency validation, and real-world rescue support such as ambulances, hospitals, and police stations.

Built for real-world road conditions—especially highways, rural areas, and low-network regions—ResQRoute ensures that help reaches faster, decisions are smarter, and false alerts are minimized.

# Table of Contents

- [Overview](#overview)
- [Features](#features)
- [AI Model Training Process](#ai-model-training-process)
- [Getting Started](#getting-started)
- [What was found](#what-was-found)
- [What Worked](#what-worked)
- [What Didn't Work and Future Improvements](#what-didnt-work-and-future-improvements)
- [Pros and Cons of the App](#pros-and-cons-of-the-app)
- [Demo Video](#demo-video)
- [Screenshots](#screenshots)
- [Libraries](#libraries)
- [References](#references)

# Overview
ResQRoute is a smart emergency response system we’re building to help people during road accidents. The main idea is simple — when an accident happens, the system should not wait for someone to call for help. Instead, it should automatically detect the situation, check if it’s a real emergency, and quickly connect the user to nearby help like ambulances, hospitals, or police.

We designed it mainly thinking about real problems in India like:
1. Delay in ambulance arrival
2. Lack of network in highways or rural areas
3. People not knowing whom to contact during emergencies
4. Fake or accidental SOS calls

## 🎯 Why we built this

In most road accidents, the first few minutes are very critical. But in real life, that time is often wasted because:
1. Victim may be unconscious
2. No one nearby reacts quickly
3. Location is not shared properly
4. Network might not work

So the idea behind ResQRoute is:
“What if the system itself takes charge during emergencies?”

# Features
### 1. Accident Detection System
- Detects possible road accidents using motion patterns
- Uses signals like sudden impact, speed drop, and abnormal movement
- Works like a smart trigger instead of manual reporting

### 2. Emergency Validation System
- Checks whether the alert is real or fake
- Asks user confirmation like “Are you safe?”
- Uses wearable signals (heart rate / fall detection simulation)
- Prevents unnecessary or false SOS alerts

### 3. Automatic SOS Activation
- If user doesn’t respond within a time limit, SOS is triggered automatically
- Sends emergency status without manual input
- Works even if the user is unconscious

### 4. Live Location Sharing
- Captures and shares real-time GPS location
- Sends location to ambulance, police, and emergency contacts
- Helps responders reach faster without confusion

### 5. Smart Hospital Recommendation
- Suggests nearest suitable hospital
- Prioritizes trauma centers for critical cases

### 6. Offline Emergency Mode
- Works without internet connection
- Uses stored local data (hospitals, police stations, contacts)
- Sends emergency alerts using SMS fallback
- Useful in rural or highway areas

### 7. Multilingual Support
- Supports English and Tamil
- Emergency messages are shown in user’s language
- Helps non-English users understand instructions clearly

### 8. Wearable Device Integration (Simulated)
- Uses smartwatch-like data:
- Heart rate spikes
- Fall detection
- Inactivity tracking
- Improves accident detection accuracy

### 9. Emergency Alert System
Automatically notifies:
- Ambulance services
- Police stations
- Family/emergency contacts
Sends:
 - Location
 - Severity level
 - User status

### 10. Low Network Compatibility
- Works even in poor network areas
- Switches to offline mode automatically
- Ensures emergency flow is not interrupted

# AI Model Training Process
- The AI model in ResQRoute is trained to detect road accidents using smartphone sensor data like accelerometer, gyroscope, and GPS. We collect data from normal driving (smooth speed, turns, braking) and accident-like situations (sudden impact, sharp speed drop, abrupt rotation). Each data is labeled so the model can learn the difference between normal and emergency conditions.

- Before training, the data is cleaned, normalized, and split into small time intervals. From this, key features like sudden deceleration, impact force, and abnormal movement are extracted. This helps the model clearly understand accident patterns.

- The model is then trained using machine learning to classify whether a situation is normal or an accident. After prediction, a validation step checks with the user (like “Are you safe?”) to avoid false alerts. If there is no response, SOS is triggered automatically.

- Finally, the trained model runs in real time on the device and continuously monitors movement. When an accident is detected, it sends the location and emergency alert to contacts, ensuring quick help without manual input.

# Getting Started
1. Clone the repository using:
```
git clone https://github.com/sahithyapopuriofficial-bit/ResQRoute
```
2. Navigate into the project folder:
```cd resqroute```
3. Install required dependencies:
```npm install or yarn install```
4. Run the project locally:
```npm run dev```
5. Open the app in browser:
```http://localhost:3000```
6. Create production build:
```npm run build```
7. Deploy using Netlify:
- Go to https://netlify.com
- Connect GitHub or upload build folder
- Click Deploy
- Get live website link
8. Final output:
Your website will be live on a public URL

# What was found
-   Challenges in Accident Detection Model Training:
Training the AI model for accident detection was challenging because it required a large amount of sensor data from different driving conditions. Collecting balanced data for normal driving, harsh braking, potholes, and actual crash-like situations was important to avoid incorrect predictions.
-  Accurate Accident Detection with Proper Data:
With well-labeled and properly processed sensor data, the model is able to detect sudden impacts, speed drops, and abnormal movement patterns accurately and trigger emergency responses.
-  False Alert Conflicts in Similar Road Events:
Events like pothole hits, speed breakers, and sudden braking can sometimes look similar to accidents. Differentiating between these cases required careful feature selection and model tuning to reduce false SOS alerts.
- Sensor Data and Feature Tracking:
The system uses accelerometer, gyroscope, and GPS data to track movement. These sensors help identify changes in speed, direction, and orientation of the device, which represent vehicle motion patterns.
- Real-Time Monitoring and Continuous Analysis:
The AI model runs in real time and continuously analyzes incoming sensor data every few seconds. This ensures instant detection of abnormal events without delay.
- Confidence Score and Alert Decision:
The model generates a confidence score for each prediction. If the confidence of an accident is high, the system proceeds to the validation stage before triggering SOS.
- Emergency Validation Layer:
After detecting a possible accident, the system checks user safety through a confirmation step (like “Are you safe?”). If there is no response, the system automatically escalates to SOS mode.
Use of Detected Data for Training Improvement:
The collected real-time sensor data can be used to further improve the model, making future predictions more accurate and reducing false alerts over time.

# What Worked
### 1. Real-Time Accident Detection Worked Effectively
- The core accident detection system works well in real time using sensor data from accelerometer, gyroscope, and GPS. It successfully identifies sudden impacts, sharp deceleration, and abnormal motion patterns. Because it runs continuously in the background, it can detect emergencies instantly without needing user input.

### 2. Feature-Based Pattern Recognition Improved Accuracy
- The system performs better after extracting key features like sudden speed drop, strong impact force, and unexpected orientation changes. These features helped the model clearly separate normal driving events (like braking or speed breakers) from actual accident situations.

### 3. Reduced False Alarms with Validation Layer
- One of the most important things that worked is the emergency validation step. After detecting an accident-like event, the system asks the user a confirmation like “Are you safe?”. This simple step significantly reduced false SOS alerts caused by potholes or sudden braking.

### 4. GPS-Based Location Tracking Worked Smoothly
- The GPS module successfully captures real-time location during emergency detection. This ensures that when SOS is triggered, the exact accident location is shared quickly with emergency contacts or services.

### 5. Confidence Score System Helped Decision Making
- The model’s confidence scoring mechanism worked well in filtering predictions. Only high-confidence accident predictions move to the validation stage, which improves reliability and avoids unnecessary alerts.

### 6. Real-Time Processing Without Delay
- The system runs continuously and processes sensor data in short time windows. This allowed fast detection of unusual movement patterns, making the response time almost instant during simulated accident conditions.

### 7. Automatic SOS Trigger Worked Reliably
- If the user does not respond after an accident detection alert, the system automatically triggers SOS. This ensures emergency help is still sent even if the user is unconscious or unable to respond.

### 8. Continuous Monitoring and Background Operation
- The application works in the background without interrupting the user’s normal phone usage. This continuous monitoring makes the system practical for real-world driving scenarios.

### 9. Overall System Stability Improved with Testing
After multiple test simulations, the system became more stable and consistent in detecting events. Adjustments in thresholds and feature tuning improved overall performance and reduced random detections.

# What didn't work and future improvements
- The model sometimes confused accidents with similar events like potholes, speed breakers, and sudden braking, leading to occasional false alerts.
- Sensor data was not always stable, and small fluctuations in accelerometer and gyroscope readings affected accuracy.
- Performance varied across devices, especially between high-end and low-end smartphones due to sensor quality differences.
- Continuous background tracking sometimes increased battery usage and faced restrictions on some phones.
- GPS location was slightly delayed or less accurate in low signal or indoor conditions.
- Even after validation steps, a few false SOS triggers still happened in extreme movement cases.

Future improvements:
- Improve the AI model using deep learning techniques like LSTM for better time-based accident detection.
- Train the system with more real-world driving data to increase accuracy and reduce false alerts.
- Integrate wearable devices (smartwatch/fitness band) for better validation using heart rate and fall detection.
- Optimize battery usage by reducing continuous sensor load and using smarter data sampling.
- Enhance location tracking using GPS + network + Wi-Fi for faster and more accurate emergency location sharing.
- Reduce false positives using multi-layer validation combining AI prediction and user behavior patterns.
- Add direct integration with emergency services like ambulance or police for faster response time.

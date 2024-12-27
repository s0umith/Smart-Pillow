# 🛏️ SMART PILLOW

This repository contains the implementation of a Smart Pillow system developed as a project at the Indian Institute of Technology Kanpur (IIT Kanpur). The Smart Pillow aims to monitor and improve sleep quality by incorporating various sensors and Machine Learning models to detect sleep anomalies like sleep apnea and snoring. It provides real-time feedback on sleep quality and offers features such as vibration-induced sleep, environmental monitoring, and pillow reshaping for optimal comfort.

## 📄 Overview

The Smart Pillow is designed to monitor multiple physiological and environmental factors affecting sleep quality. It provides features like:

- Sleep apnea detection using ECG sensors.
- Snoring detection using sound analysis.
- Monitoring room temperature and humidity.
- Vibration-induced sleep using a sound emitter.
- Real-time data monitoring via a web application.

The system consists of an IoT-enabled pillow with ECG and pressure sensors, a server for data processing, and a web app for visualization. The aim is to make sleep monitoring accessible without needing specialized sleep monitoring facilities.

## ⚙️ Features

- **Sleep Monitoring**: Detects sleep apnea events using ECG data.
- **Snoring Detection**: Uses a deep learning model to identify snoring sounds.
- **Temperature and Humidity Monitoring**: Observes the environmental conditions for optimal sleep.
- **Vibration-Induced Sleep (VIS)**: Emits vibrations to induce sleep.
- **Pillow Reshaping**: Adjusts the pillow shape for maximum comfort.
- **Real-time Data Visualization**: Displays live ECG readings and sleep metrics via a web app.

## 📂 Repository Structure

```
- WebApp/           # Front-end web application for monitoring sleep data
- Server/           # Server for data processing and machine learning models
- Pillow/           # IoT code for sensors, including pressure and ECG
- Models/           # Machine Learning models for snoring and sleep apnea detection
- README.md         # Documentation for setting up and running the system
```

## 🚀 Getting Started

### For Windows

*(During the process, you may encounter several errors depending upon the configurations of your system. Please refer to the error messages and fix them accordingly.)*

### Step 1: Install Dependencies

1. **Install NPM and Node**
   - Download Node LTS from the [Node.js website](https://nodejs.org/).
   - Check installation by running the command:
     ```sh
     npm
     ```

2. **Install Yarn**
   - Open a new terminal and run:
     ```sh
     npm install --global yarn
     ```

3. **Install Concurrently**
   - Install concurrently to run multiple commands:
     ```sh
     npm install --global concurrently
     ```

4. **Install Dependencies for WebApp**
   - In the terminal, change the working directory to the `WebApp` folder and run the following command to install the dependencies:
     ```sh
     yarn
     ```

### Step 2: Run the WebApp

- To run the project on localhost:
  ```sh
  yarn dev
  ```
  - This will start the display API on the browser at [localhost:3000](http://localhost:3000).

### Step 3: Install Python Dependencies for Server

- Run the following with the `pip install` command to install the required Python modules:
  ```sh
  pip install http.server socketserver pyqrcode statistics tensorflow matplotlib tensorflow_io seaborn librosa
  ```
- If any module is still missing, try the same with that module name.

### Step 4: Run the Sensors

- Run the files `sensor.py` and `sensor_ecg.py` in the `Pillow` folder to simulate sensor data.

### Step 5: Run the Server

- Run the file `server.py` in the `Server` folder. Note the server IP shown in the output.

### Step 6: Run the Pillow

- Copy the above-noted IP in the `pillow.py` file as the value to the variable `url` followed by `//`. Example:
  ```python
  url = "http://172.17.76.7:8000//"
  ```
- Run the `pillow.py` file in the `Pillow` folder.

## 📊 Methodology

### 1. ML Model to Detect Sleep Apnea

- The ML model uses ECG data, age, and sex to predict sleep apnea events.
- The model consists of LSTM layers and dense layers, with a sigmoid activation function for classification.

### 2. DL Model to Detect Snoring

- Uses a deep learning model to classify snoring and non-snoring sounds.
- The model includes convolution layers and is trained using the Adam optimizer.

### 3. Server and Client

- The server processes sensor data, including ECG and pressure readings, and sends the processed data to the web app for visualization.
- HTTP requests (`GET` and `PUT`) are used for communication between the pillow, sensors, and server.

### 4. Display API

- Real-time ECG data is fetched every 2 seconds and displayed on the web app.
- Sleep apnea events, snoring presence, and deep sleep durations are displayed in the user interface.

## 📈 Results

- The server successfully receives and processes sensor data from the pillow.
- Real-time digitized ECG readings are displayed on the web app.
- The system can detect sleep apnea events, snoring presence, and deep sleep periods.

## 🔧 Future Work

- **Security**: Add secure protocols like JWT Tokens for better authentication.
- **Environmental Control**: Connect the pillow to a room thermostat for optimal temperature regulation.
- **Pillow Shape Adjustment**: Implement pillow reshaping based on pressure sensor readings for better comfort.
- **Enhanced Music Control**: Automate white-noise playback based on sleep conditions.
- **Mobile-Friendly Interface**: Develop a mobile-friendly version of the web app with real-time updates.

## 📜 Conclusion

The Smart Pillow system aims to improve sleep quality by providing real-time monitoring of sleep conditions and helping users detect potential sleep issues such as apnea and snoring. With further improvements, it has the potential to make sleep monitoring more accessible and comfortable for everyday use.

Feel free to explore the repository and collaborate on future enhancements!

## 👥 Team Members

- Ankur Kumar 
- Yukkta Seelam 
- Soumith Batta
- Manas Gupta
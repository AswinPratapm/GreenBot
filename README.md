# GreenBot
PEA WEED CLASSIFICATION, IDENTIFICATION AND PESTICIDE SPRAYING ROBOTIC VEHICLE
<img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExZTJ5dXhkYjBlNjk3Mzk0dDVwOGRjMm9jOWw2cDV0bTNmbWJrM2l2MyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/CytKuRG1UCciXh9SDx/giphy.gif" width="35px"> 
GreenBot is an autonomous robotic vehicle designed for precision agriculture. It leverages a deep learning model to differentiate between pea crops and weeds in real-time, enabling targeted pesticide spraying and intelligent irrigation. The entire system is controlled remotely via a custom Android application.
Key Features

    AI-Powered Weed Detection: Utilizes a custom-trained YOLOv3 model to accurately identify and locate weeds among crops from a live camera feed.

    Remote & Autonomous Operation: The robot can be manually controlled through an Android app, which also displays sensor data and the live video stream.

    Targeted Spraying: Equipped with a pesticide pump that can be precisely activated, minimizing chemical usage and environmental impact.

    Environmental Monitoring: Onboard sensors continuously monitor soil moisture and ambient temperature, allowing for smart irrigation decisions.

    Complete Integrated System: A fully operational prototype built on a Raspberry Pi, integrating hardware control, sensor data processing, and a web-based API for communication.

How It Works

The robot's brain is a Raspberry Pi, which manages all operations. A Pi Camera captures video, which is processed by an OpenCV DNN module running the YOLOv3 object detection model. The model outputs bounding boxes classifying plants as either 'crop' or 'weed'.

Motor control is handled by an L293D IC, while relays switch the pesticide and water pumps. Analog sensor data is read via an ADC. A Flask web server running on the Pi exposes a REST API, allowing the Android application to send commands (e.g., move forward, start pump) and receive data (sensor readings, detection results).
Technology Stack

    Hardware: Raspberry Pi, Pi Camera, L293D Motor Driver, Soil Moisture Sensor, Temperature Sensor, DC Motors, Relays.

    Software: Python, OpenCV, Flask, RPi.GPIO, smbus.

    AI Model: YOLOv3 (You Only Look Once).

Getting Started

To run this project, you will need to have all the required hardware connected to the Raspberry Pi. You can Find the PCB Diagram in Resources

    
    Place the model weights (crop_weed_detection.weights) and the class names file (obj.names) in the same directory.

    Run the main application:

    python FINALCODE.py

    The Flask server will start, and the robot will be ready to receive commands from the Android application.

This project was completed in May 2022 as a final year project for the Bachelor of Technology degree. It is uploaded here for portfolio and demonstration purposes.

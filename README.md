# SSD-IoT
IoT
Features
Uses MobileNetV2 as the base for SSD object detection.
Multi-scale feature extraction using convolutional layers.
Real-time detection from IoT camera (OpenCV).
MQTT integration to send object detection results to the cloud.
MQTT Configuration
The code uses HiveMQ public broker:

Broker URL: broker.hivemq.com
Topic: iot/object_detection
Modify the MQTT_BROKER and MQTT_TOPIC variables if you need a different broker.

How to Run
Connect an IoT Camera or use a built-in webcam.

Run the Python script:

bash
Copy
Edit
python object_detection_iot.py
The system will:

Capture real-time frames.
Process the frames using SSD.
Publish object detection results via MQTT.
Display the live feed with detection.
Press 'q' to exit.

Code Breakdown
1. Model Setup
Loads MobileNetV2 without the top layer.
Adds SSD detection heads (confidence and bounding box layers).
Uses Adam optimizer with classification and localization loss.
2. IoT Communication (MQTT)
Connects to an MQTT broker.
Publishes confidence scores and bounding box locations.
3. Real-Time Processing
Reads frames from the camera.
Preprocesses them and sends them to the SSD model.
Displays the video feed with object detection.
Customization
Change MQTT Broker: Modify MQTT_BROKER and MQTT_TOPIC.
Adjust Model Input Size: Modify input_shape=(300, 300, 3).
Use a Different Object Detection Model: Replace MobileNetV2 with another SSD-compatible model.
License
This project is open-source and free to use.

# ESP32 AWS IoT Core Integration

### Overview
Connect your ESP32 to AWS IoT Core for seamless remote control and monitoring! This project uses MQTT and device shadows to manage the built-in LED of the ESP32, allowing you to send commands from an MQTT dashboard or using Alexa voice commands. Experience real-time communication and easy IoT integration.

### Features
- **MQTT Communication**: Effortlessly connect to AWS IoT Core with MQTT for real-time data transfer.
- **Device Shadows**: Utilize AWS IoT device shadows for reliable state management.
- **Alexa Integration**: Control your ESP32 with simple voice commands through Alexa.
- **Remote Control**: Use an MQTT dashboard to monitor and control the ESP32 LED.

### Setup Instructions
1. Clone this repository.
2. Create a `config.h` file in the `src` folder with the following content:

   ```cpp
   #include <Arduino.h>
   #pragma once
   // Replace with your network credentials
   const char* WIFI_SSID = "your_wifi_ssid";
   const char* WIFI_PASS = "your_wifi_password";

   // Replace with your MQTT broker details
   const char* MQTT_BROKER = "your_mqtt_broker_endpoint";
   const int MQTT_PORT = 8883;
   const char* CLIENT_ID = "ESP-32";

   const char AMAZON_ROOT_CA1[] PROGMEM = R"EOF(
   -----BEGIN CERTIFICATE-----
   Your Amazon Root CA1 certificate here
   -----END CERTIFICATE-----
   )EOF";

   const char CERTIFICATE[] PROGMEM = R"KEY(
   -----BEGIN CERTIFICATE-----
   Your device certificate here
   -----END CERTIFICATE-----
   )KEY";

   const char PRIVATE_KEY[] PROGMEM = R"KEY(
   -----BEGIN RSA PRIVATE KEY-----
   Your private key here
   -----END RSA PRIVATE KEY-----
   )KEY";

3. Upload the code to your ESP32.
4. Connect the ESP32 to your Wi-Fi and watch it communicate with AWS IoT Core!

### Prerequisites
- An AWS IoT account and an IoT thing registered in AWS IoT Core.
- MQTT client (such as MQTT Dashboard app) for testing.
- An Alexa skill set up for voice control (optional).

### Note
**Don't forget** to include your Wi-Fi credentials and MQTT broker details in the `config.h` file before running the project.

### Disclaimer
Ensure you keep your AWS certificates and Wi-Fi credentials secure. Use `.gitignore` to exclude `config.h` from being uploaded to public repositories.


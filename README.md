# IoT Healthcare Monitoring System

This project is an IoT-based healthcare monitoring system using an ESP32 microcontroller. It measures various health parameters such as temperature, ECG, pressure, and SpO2 levels, and then sends these readings to the cloud using MQTT. The system also includes a servo motor, LEDs, and a buzzer for visual and auditory alerts based on the readings.

## Features

- **Temperature Monitoring**: Uses the DS18B20 sensor to measure body temperature.
- **ECG Monitoring**: Measures ECG values using the AD8232 sensor.
- **Pressure Monitoring**: Measures blood pressure using the MPS20N0040D-GDF sensor.
- **SpO2 and Heart Rate Monitoring**: Uses the MAX30100 Pulse Oximeter sensor to measure oxygen saturation and heart rate.
- **Human Detection**: Uses an IR sensor to detect the presence of a person.
- **Servo Motor Control**: The servo motor adjusts its position based on sensor readings and MQTT messages.
- **MQTT Communication**: Sends sensor data to HiveMQ Cloud and receives control commands for the servo motor.
- **Visual and Auditory Alerts**: Includes LEDs and a buzzer for alerts based on health data.

## Hardware Requirements

- ESP32 Development Board
- DS18B20 Temperature Sensor
- AD8232 ECG Sensor
- MPS20N0040D-GDF Pressure Sensor
- MAX30100 Pulse Oximeter
- LiquidCrystal I2C Display (16x2)
- Servo Motor (e.g., SG90)
- IR Sensor
- Green and Red LEDs
- Buzzer
- Resistors, Breadboard, and Connecting Wires

## Software Requirements

- Arduino IDE (with ESP32 board package installed)
- PubSubClient library
- WiFi library
- WiFiClientSecure library
- OneWire library
- DallasTemperature library
- LiquidCrystal I2C library
- MAX30100 Pulse Oximeter library
- ESP32Servo library

## Installation and Setup

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/IoT-Healthcare-Monitoring-System.git
   ```

2. **Install Required Libraries:**
   Ensure you have the required libraries installed in your Arduino IDE. Use the Library Manager to install them.

3. **Hardware Setup:**
   - Connect the sensors to the ESP32 according to the pin definitions provided in the code.
   - Connect the I2C LCD to the appropriate I2C pins (SDA to GPIO 21, SCL to GPIO 22).
   - Connect the servo motor to GPIO 26.

4. **Configure WiFi and MQTT:**
   Update the `ssid`, `pass`, `mqtt_server`, `mqtt_username`, `mqtt_password`, and `mqtt_port` variables in the code with your WiFi credentials and HiveMQ Cloud broker settings.

5. **Upload the Code:**
   - Connect your ESP32 to the computer via USB.
   - Open the Arduino IDE, select the correct board and port, and upload the code.

6. **Monitor Output:**
   - Open the Serial Monitor at 9600 baud to view debug information.
   - The LCD will display sensor readings and classifications.
   - Data will be sent to HiveMQ Cloud, and you can control the servo motor via MQTT messages.

## Usage

- **Sensor Data Display**: The LCD will show real-time sensor data and classifications.
- **MQTT Control**: Use an MQTT client to send commands to the `servo/control` topic to control the servo motor's angle.
- **Alert System**: The system triggers visual and auditory alerts based on abnormal sensor readings.

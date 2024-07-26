

# 🌐 LoRa Communication System with RFM95, Arduino, and DHT11 Sensor

This project demonstrates a communication system using LoRa modules (RFM95) with Arduino and DHT11 sensors. The setup includes two nodes that transmit temperature and humidity data to a server, which responds with an acknowledgment. The communication happens at a frequency of 433.0 MHz.

## 📑 Table of Contents
- [📖 Overview](#overview)
- [🔧 Components](#components)
- [📊 Circuit Diagrams](#circuit-diagrams)
- [⚙️ Setup Instructions](#setup-instructions)
- [💻 Code Overview](#code-overview)
- [📝 Detailed Steps](#detailed-steps)
- [🛠️ Troubleshooting](#troubleshooting)
- [📄 License](#license)
- [💖 Donation](#donation)

## 📖 Overview
The project showcases basic communication between multiple LoRa-enabled devices and a central server using the RFM95 module. Each node reads temperature and humidity data from a DHT11 sensor and sends this data to the server. The server receives the data, prints it, and sends an acknowledgment back to the respective node.

### 🌟 Features
- **📡 LoRa Nodes**: Transmit temperature and humidity data.
- **🖥️ Server**: Receives data and sends acknowledgments.
- **📶 Communication Frequency**: 433.0 MHz.
- **✅ Acknowledgment Mechanism**: Ensures reliable communication.
- **🌡️ DHT11 Sensor**: Measures temperature and humidity.

## 🔧 Components
- **🔌 Arduino Boards**: Used as the microcontroller platform.
- **📡 RFM95 LoRa Modules**: For wireless communication.
- **🌡️ DHT11 Sensors**: For measuring temperature and humidity.
- **📦 SPI Library**: To handle SPI communication.
- **📦 RH_RF95 Library**: To handle LoRa communication.
- **📦 DHT Library**: To handle DHT11 sensor data.

## 📊 Circuit Diagrams
Include the circuit diagram here (replace this text with the actual diagram image).

### 🟢 Server Communication Diagram
![Server Communication Diagram](Scenario%20(2).jpg)

## ⚙️ Setup Instructions
1. **Hardware Connections**:
   - Connect the RFM95 module to the Arduino as per the following pin definitions:
     - `RFM95_CS` to pin 26
     - `RFM95_RST` to pin 12
     - `RFM95_INT` to pin 25
   - Connect a DHT11 sensor to pin 4 on each node Arduino.

2. **Software Setup**:
   - Install the necessary libraries:
     - [SPI](https://www.arduino.cc/en/Reference/SPI)
     - [RH_RF95](https://www.airspayce.com/mikem/arduino/RadioHead/classRH__RF95.html)
     - [DHT](https://github.com/adafruit/DHT-sensor-library)
   - Clone the repository and load the provided node and server device code onto the respective Arduino boards:
     ```bash
     git clone https://github.com/Esmail-Sarhadi/LoRa-Communication-System.git
     cd LoRa-Communication-System
     ```

3. **Operation**:
   - Power the Arduino boards.
   - Open the Serial Monitor at a baud rate of 115200 to view communication logs.
   - Each node will periodically send temperature and humidity data to the server. The server will print the received data and send an acknowledgment.

## 💻 Code Overview

### Node Device Code
- **Initialization**: Sets up the LoRa module, configures the frequency, initializes the DHT11 sensor, and sets the transmission power.
- **Loop**: Continuously reads temperature and humidity from the DHT11 sensor, formats the data, and sends it to the server. If no acknowledgment is received within the timeout period, it resends the data. Upon receiving the correct acknowledgment, it prints the acknowledgment.

### Server Device Code
- **Initialization**: Sets up the LoRa module, configures the frequency, and sets the transmission power.
- **Loop**: Continuously listens for incoming data. Upon receiving data, it parses the message, prints the data, and sends an acknowledgment back to the node.

## 📝 Detailed Steps

### Node Device Setup
1. Connect the RFM95 module and DHT11 sensor to the node Arduino using the defined pins.
2. Load the node device code onto the Arduino.
3. Open the Serial Monitor to observe the sending of temperature and humidity data.

### Server Device Setup
1. Connect the RFM95 module to the server Arduino using the defined pins.
2. Load the server device code onto the Arduino.
3. Open the Serial Monitor to observe the receiving of data and sending of acknowledgments.

## 🛠️ Troubleshooting
- **No Communication**: Ensure the wiring between the Arduino and the RFM95 module is correct.
- **Initialization Failed**: Check if the RFM95 module is correctly connected and powered.
- **No Response from Server**: Ensure the server device is powered and running the correct code.
- **Incorrect Sensor Readings**: Verify the connections and functionality of the DHT11 sensor.

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 💖 Donation
If you found this project helpful, consider making a donation:

<a href="https://nowpayments.io/donation?api_key=REWCYVC-A1AMFK3-QNRS663-PKJSBD2&source=lk_donation&medium=referral" target="_blank">
     <img src="https://nowpayments.io/images/embeds/donation-button-black.svg" alt="Crypto donation button by NOWPayments">
</a>


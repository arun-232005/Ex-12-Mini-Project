# Ex-12 Mini Project
## RASPBERRY PI BASED TEMPERATURE MONITORING AND ALERT SYSTEM USING DHT22
Submitted by:

PETER AMBROSE B, ARUN H, ANBUVIJAYAN S

Department of Electronics and Communication Engineering

Saveetha Engineering College

## ABSTRACT

Temperature monitoring is an important application used in homes, industries, laboratories, agriculture, and storage systems. This project presents the design and implementation of a Raspberry Pi-based temperature monitoring and alert system using a DHT22 sensor to continuously measure temperature and humidity. The Raspberry Pi processes the sensor data and determines the current temperature condition in real time. The measured information can be displayed on a computer or monitoring interface. The system can also provide alerts through an LED and buzzer when the temperature becomes too high or too low, helping to prevent temperature-related damage and maintain safe operating conditions. This project demonstrates the integration of sensors, a Raspberry Pi, and Python programming to create a simple, efficient, and reliable temperature monitoring system. The design is compact, low-cost, and suitable for residential, industrial, agricultural, and educational applications.

## TABLE OF CONTENTS

● Introduction
● Literature Survey
● Proposed Methodology
● Hardware Description
● Software Implementation
● Working Principle
● Applications
● Results and Discussion
● Conclusion and Future Scope
● References

## CHAPTER 1 – INTRODUCTION

Temperature monitoring is the process of measuring and observing the temperature of an environment, device, room, storage area, or industrial system. It is widely used in homes, industries, agriculture, laboratories, and temperature-sensitive storage systems to prevent overheating, freezing, and equipment damage. With the increasing demand for smart and automated monitoring systems, there is a need for compact, low-cost, and reliable temperature monitoring solutions.

This project focuses on developing a Raspberry Pi-based temperature monitoring and alert system using a DHT22 sensor. The DHT22 sensor detects temperature and humidity and sends the measured data to the Raspberry Pi. The Raspberry Pi processes the sensor readings and determines the current temperature condition. The system can provide an alert using an LED and buzzer when the temperature crosses a predefined threshold. This helps users identify abnormal temperature conditions and take necessary action.

## Objectives

● The main objectives of this project are:

● To design a simple temperature monitoring system using Raspberry Pi.

● To measure and monitor temperature and humidity using the DHT22 sensor.

● To process and display the detected temperature in real time.

● To provide alerts when the temperature becomes too high or too low.

● To understand the working of DHT22, Raspberry Pi, and Python programming.

## CHAPTER 2 – LITERATURE SURVEY

Temperature monitoring systems have been widely studied and implemented in various fields such as industries, agriculture, healthcare, laboratories, homes, and storage systems. Traditional methods mainly depend on manual temperature checking, which can be time-consuming and may not provide continuous monitoring. Recent systems use digital temperature sensors connected to microcontrollers or single-board computers for automated and real-time monitoring.

The DHT22 sensor is commonly used for temperature and humidity measurement because it can provide digital output that can be processed by a controller. Raspberry Pi-based monitoring systems have become popular because the Raspberry Pi provides GPIO pins, processing capability, and support for Python programming.

These systems can also include alert mechanisms such as LEDs and buzzers to notify users when temperature values cross predefined limits. Such systems demonstrate that Raspberry Pi and DHT22 can be used to develop compact, cost-effective, and reliable temperature monitoring solutions.

## CHAPTER 3 – PROPOSED METHODOLOGY

The proposed system consists of the following main components:

● Raspberry Pi

● DHT22 Temperature and Humidity Sensor

● LED

● Resistor

● Buzzer

● Jumper Wires

● Breadboard

● Power Supply

● Computer for Monitoring

## CHAPTER 4 – HARDWARE DESCRIPTION
### Raspberry Pi

Raspberry Pi is a compact single-board computer widely used in embedded systems, IoT applications, automation, and educational projects. It provides GPIO pins that can be used to connect sensors and output devices. In this temperature monitoring system, the Raspberry Pi receives temperature and humidity data from the DHT22 sensor, processes the readings, and controls the LED and buzzer based on predefined temperature limits.

### Features:

● Raspberry Pi Single-Board Computer
● GPIO pins for sensor and device interfacing
● USB connectivity
● HDMI connectivity
● Python programming support
● Low-cost and compact design
● Suitable for IoT and embedded applications

The Raspberry Pi acts as the main processing unit of the temperature monitoring system. It receives sensor data from the DHT22, processes the temperature readings, and determines whether the temperature is normal or requires an alert.

### DHT22 Temperature and Humidity Sensor

The DHT22 is a digital temperature and humidity sensor used to measure environmental temperature and relative humidity. It provides digital data to the Raspberry Pi through its data pin.

The DHT22 helps the system monitor the surrounding environmental conditions continuously. The measured temperature is compared with predefined threshold values to determine whether the condition is normal or requires an alert.

### LED

The LED is used as a visual indication of the temperature condition. It can be switched ON when the temperature reaches an abnormal level and switched OFF when the temperature remains within the normal range.

### Buzzer

The buzzer provides an audible alert when the measured temperature crosses the predefined temperature limit. This allows the user to identify abnormal temperature conditions immediately.

### Resistor

A resistor is connected in series with the LED to limit the current flowing through it and protect the LED from excessive current.

### Jumper Wires

Jumper wires are used to establish electrical connections between the Raspberry Pi, DHT22 sensor, LED, resistor, and buzzer. They make the circuit easy to assemble and modify.

### Power Supply

The power supply provides the required electrical power to the Raspberry Pi and connected components. The Raspberry Pi can be powered through its suitable power input or USB connection.

## CIRCUIT DIAGRAM

<img width="521" height="607" alt="image" src="https://github.com/user-attachments/assets/2bc4dfad-0d9e-4563-b327-84ee41e12279" />

## CHAPTER 5 – SOFTWARE IMPLEMENTATION

The system is programmed using Python on the Raspberry Pi. The program reads the temperature and humidity values from the DHT22 sensor and processes the readings. The Raspberry Pi continuously monitors the temperature and compares it with predefined threshold values.

The program performs the following steps:

● Initialize the Raspberry Pi and connected devices.

● Read temperature and humidity values from the DHT22 sensor.

● Process the sensor data.

● Display the temperature and humidity values.

● Compare the temperature with predefined limits.

● Turn ON the LED and buzzer when the temperature crosses the threshold.

● Turn OFF the LED and buzzer when the temperature returns to the normal range.

● Continuously repeat the monitoring process.

## Sample Python Program
```
import time
import random

LED_PIN = 17
BUZZER_PIN = 18

HIGH_TEMP = 30
LOW_TEMP = 20

def led_on():
    print("LED: ON")

def led_off():
    print("LED: OFF")

def buzzer_on():
    print("BUZZER: ON")

def buzzer_off():
    print("BUZZER: OFF")

while True:

    # Simulated DHT22 temperature and humidity
    temperature = round(random.uniform(18, 35), 1)
    humidity = round(random.uniform(40, 90), 1)

    print("\nTemperature:", temperature, "°C")
    print("Humidity:", humidity, "%")

    if temperature > HIGH_TEMP:
        led_on()
        buzzer_on()
        print("STATUS: HIGH TEMPERATURE ALERT!")

    elif temperature < LOW_TEMP:
        led_on()
        buzzer_on()
        print("STATUS: LOW TEMPERATURE ALERT!")

    else:
        led_off()
        buzzer_off()
        print("STATUS: NORMAL")

    time.sleep(2)
```

This program is suitable for a simulation where DHT22 values are generated for testing. For a physical Raspberry Pi, the DHT22 GPIO-reading section would be replaced with the appropriate sensor library/code.

## CHAPTER 6 – WORKING PRINCIPLE

The Raspberry Pi-based temperature monitoring system works based on temperature sensing and microcomputer processing. The DHT22 sensor continuously detects the surrounding temperature and humidity and sends the measured data to the Raspberry Pi.

The Raspberry Pi reads and processes the sensor data using Python programming. The temperature value is then compared with predefined temperature limits.

If the temperature is within the normal range, the LED and buzzer remain OFF and the system displays “STATUS: NORMAL.”

If the temperature becomes higher than the defined maximum limit, the LED and buzzer are activated and the system displays “HIGH TEMPERATURE ALERT!”

Similarly, if the temperature falls below the minimum limit, the LED and buzzer are activated and the system displays “LOW TEMPERATURE ALERT!”

Thus, the system continuously monitors temperature and provides immediate visual and audible alerts for abnormal temperature conditions.

## CHAPTER 7 – APPLICATIONS

The Raspberry Pi-based temperature monitoring and alert system can be used in various applications such as:

● Home temperature monitoring

● Industrial temperature monitoring

● Server room monitoring

● Agricultural environments

● Laboratory monitoring

● Cold storage and food storage

● Electronic equipment protection

● Smart home automation systems

The system can also be used in IoT-based monitoring applications where continuous temperature measurement and automatic alerts are required.

## CHAPTER 8 – RESULTS AND DISCUSSION

The developed Raspberry Pi-based temperature monitoring and alert system successfully monitors temperature and humidity using the DHT22 sensor. The sensor provides temperature readings to the Raspberry Pi, which processes the values and determines the current temperature condition.

The temperature and humidity values are displayed in real time through the simulation or terminal. When the temperature exceeds the predefined high-temperature limit, the LED and buzzer are activated and a high-temperature alert is displayed.

Similarly, when the temperature falls below the predefined low-temperature limit, the LED and buzzer provide an alert. When the temperature remains within the defined range, the system displays the normal status and keeps the alert devices OFF.

This demonstrates the successful integration of Raspberry Pi, DHT22, LED, buzzer, and Python programming to create a simple, reliable, and cost-effective temperature monitoring system.

## CHAPTER 9 – CONCLUSION AND FUTURE SCOPE
### Conclusion

The Raspberry Pi-based temperature monitoring and alert system was successfully designed and implemented using a DHT22 temperature and humidity sensor. The system effectively monitors environmental temperature and displays the measured values in real time.

The system provides visual and audible alerts when the temperature becomes too high or too low. This project helped in understanding the working of DHT22 sensors, Raspberry Pi GPIO interfacing, Python programming, and embedded monitoring systems.

The developed system provides a simple, reliable, and low-cost solution for continuous temperature monitoring and abnormal-temperature detection.

### Future Scope

The system can be further improved by adding Wi-Fi-based remote monitoring, mobile notifications, cloud data storage, graphical temperature monitoring, automatic fan control, and IoT-based remote access.

## OUTPUT

### Expected simulation output:

<img width="446" height="556" alt="image" src="https://github.com/user-attachments/assets/d7a3d2e4-bf0d-44ff-a626-10f0a6039e7c" />

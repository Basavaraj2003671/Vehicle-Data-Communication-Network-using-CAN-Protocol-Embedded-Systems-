# Vehicle-Data-Communication-Network-using-CAN-Protocol-Embedded-Systems-
This project demonstrates real-time sensor data transfer between two Arduino boards using the CAN (Controller Area Network) protocol. A DHT11 sensor connected to an Arduino Nano (Transmitter Node) sends temperature and humidity data via the MCP2515 CAN bus module to an Arduino UNO (Receiver Node), which displays the data on a 16×2 LCD.  
This setup replicates how real automotive ECUs communicate inside vehicles using CAN.

🚀 Features

Real-time temperature & humidity monitoring

Reliable CAN bus communication using MCP2515

Demonstrates message identifiers, DLC, and data bytes

Differential signalling (CAN_H & CAN_L) for noise-immune data transfer

Compatible with automotive & industrial applications

Easy hardware expandability (up to 112 CAN nodes)

🧠 What is CAN Protocol?

The CAN protocol is a serial communication standard designed for automotive and industrial systems.
It works like the nervous system of a car — every ECU (node) can send and listen to messages on the same 2-wire network.

Key CAN Concepts
Parameter	Description
CAN_H & CAN_L	Differential signalling wires
ID (Identifier)	Unique message ID (11-bit or 29-bit)
DLC	Number of data bytes (0–8)
Data Field	Actual sensor/control data
Speed	50 kbps – 1 Mbps

📦 Components Used

Arduino UNO (Receiver)

Arduino Nano (Transmitter)

MCP2515 CAN Module × 2

DHT11 Temperature & Humidity Sensor

16×2 LCD Display

10k Potentiometer

Breadboard & Jumper Wires

Twisted pair cable for CAN_H & CAN_L

🔌 Circuit Diagram Overview
Transmitter (Arduino Nano)

Reads temperature & humidity using DHT11

Sends data frame through MCP2515 via SPI

CAN_H & CAN_L connected to receiver module

Receiver (Arduino UNO)

Receives CAN frames via MCP2515

Extracts humidity & temperature

Displays values on 16×2 LCD

CAN Bus Wiring
Nano MCP2515 H -------------- UNO MCP2515 H
Nano MCP2515 L -------------- UNO MCP2515 L


120Ω termination resistors are placed at both ends of the CAN bus.

🧰 Libraries Used

Install the following Arduino libraries:

SPI.h (built-in)

mcp2515 – CAN controller library
Working Principle

The DHT11 measures humidity and temperature.

Arduino Nano reads the sensor values and creates a CAN data frame.

MCP2515 transfers the frame using CAN_H & CAN_L.

The UNO receives the frame through its MCP2515 module.

The UNO extracts the temperature & humidity bytes.

The LCD displays the updated sensor data in real-time.

This setup simulates a real ECU-to-ECU communication network, used widely in automotive systems.

📊 Results

Successful communication between Arduino Nano and UNO

Temperature & humidity displayed accurately on LCD

Demonstrates real-time CAN data transfer

Reliable even in noisy environments due to differential signalling

🛠️ Applications

Automotive ECU communication

Industrial automation

Sensor networks

Smart monitoring systems

Robotics & embedded communication

DHT.h – DHT11 sensor

LiquidCrystal.h – LCD display

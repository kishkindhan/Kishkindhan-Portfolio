Smart Key Management System
Project Overview

This project is a Smart Key Management System built using an ESP32, RFID reader, relay-controlled lock mechanism, and a 1602 RGB LCD. The system automates key access logging, user authentication, and lock control. Data is transmitted to a backend system for monitoring and record-keeping.

The system demonstrates applied skills in embedded systems, IoT, backend development, and access control logic.

Problem Statement

Traditional key management requires manual tracking, which is prone to lost keys, no accountability, and no real-time monitoring.
There is also no automated method to record which user accessed which lock and at what time.

Objective:
Build a low-cost, fully automated system that authenticates users via RFID, controls a lock electronically, and logs all access activities.

Solution

The system uses RFID for identity authentication, a relay for lock actuation, and an LCD to display access status.
Logs are transmitted to a backend dashboard and stored in a database for administrators.

Flow:

User scans RFID card

ESP32 reads and verifies UID

If authorized:

Relay activates

LCD displays user information + timestamp

Access log uploaded to server/cloud

System resets lock and waits for the next user

System Architecture

Components:

ESP32 Development Board

MFRC522 RFID Module

1602 RGB LCD (I²C)

Relay Module (GPIO Pin 4)

Python backend / Flask dashboard

ThingSpeak / Adafruit IO for IoT logging

Optional MongoDB for log storage

Data Flow:
RFID → ESP32 → Verification → Relay + LCD → Cloud Logging → Dashboard

Key Features

RFID-based authentication

Real-time lock control

LCD display for status feedback

IoT logging (ThingSpeak / Adafruit IO)

Python/Flask backend for access monitoring

Support for multiple authorized users

Auto timestamping for every unlock event

Authorized UIDs (Demo)

A6 A5 5F 5F

C9 A9 B7 89

C3 3E 44 0E

Technologies Used

Hardware: ESP32, MFRC522 RFID, Relay, LCD
Languages: MicroPython, Python, HTML
Tools: Flask, ThingSpeak, Adafruit IO, MongoDB
Concepts: Access control, IoT communication, event logging, embedded programming

Project Implementation
1. RFID Reading & Verification

ESP32 reads card UID and checks against authorized list.

2. Relay Control

Relay (GPIO 4) triggers the electronic lock.

3. LCD Feedback

Displays:

Authorized/Unauthorized

UID

Timestamp

Lock status

4. Data Logging

ThingSpeak Field 1 → UID

Field 2 → Relay status

Field 3 → Access log timestamp

5. Backend Dashboard

Optional Flask app:

Shows real-time logs

Filters by user/date

Simple admin UI

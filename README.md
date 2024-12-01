# README

## Project Overview

This project simulates a building monitoring system using Kafka for real-time data processing and alert generation. Below is a breakdown of the functionality:

### 1. Topic Creation

Three Kafka topics are used to manage data:

- **`kaplan_i_building_sensors`**: Stores data from all sensors.
- **`kaplan_i_temperature_alerts`**: Stores alerts for temperature exceeding allowable limits.
- **`kaplan_i_humidity_alerts`**: Stores alerts for humidity going outside allowable ranges.

### 2. Data Generation and Transmission

A Python script is used to simulate sensor operations:

- **Generated data**:
  - `Sensor ID`
  - `Temperature`: Random values between 25–45°C
  - `Humidity`: Random values between 15–85%
- **Data Transmission**:
  - Sensor data is sent to the `kaplan_i_building_sensors` topic.
- Screenshots demonstrate multiple scripts running simultaneously to simulate data from different sensors.

### 3. Data Processing

A Python script subscribes to the `kaplan_i_building_sensors` topic and processes the received data:

- **Temperature Alerts**:
  - If `Temperature > 40°C`, an alert is generated and sent to `kaplan_i_temperature_alerts`.
- **Humidity Alerts**:
  - If `Humidity < 20%` or `Humidity > 80%`, an alert is generated and sent to `kaplan_i_humidity_alerts`.

**Alert Messages** include:

- Sensor ID
- Measured values
- Timestamp
- Alert description

### 4. Results Display

Alerts are read from their respective topics and displayed in the terminal for verification.

- The system functions as intended, as shown in the provided screenshots.

---

For detailed setup and execution instructions, please refer to the project documentation or scripts.

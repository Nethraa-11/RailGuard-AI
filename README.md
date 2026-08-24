# 🚆 RailGuard AI

## AI-Powered Railway Track Health Monitoring Robot

RailGuard AI is an intelligent railway track monitoring system that combines
computer vision, IoT sensors, artificial intelligence, GPS and a real-time
web dashboard to monitor railway tracks and detect potential cracks and
obstacles.

The system uses an ESP32-S3 camera to capture railway track images and
transmits the data through Wi-Fi to a Python FastAPI backend. The backend
processes the images using YOLO-based computer vision models and sends the
results to the RailGuard AI Command Center dashboard.

---

## 🎯 Problem Statement

Railway tracks require frequent inspection to identify cracks, obstacles and
other potential hazards before they become serious safety problems.

Traditional inspection methods can be:

- Manual and time-consuming
- Difficult to perform continuously
- Dependent on human observation
- Expensive for frequent inspection
- Limited in providing real-time monitoring and alerts

RailGuard AI aims to provide an automated and intelligent approach to railway
track monitoring.

---

## 💡 Our Solution

RailGuard AI is a smart railway track monitoring robot that combines:

- 📷 ESP32-S3 camera
- 🤖 YOLO-based crack detection
- 🔍 General object detection
- 📏 Ultrasonic distance sensing
- 📍 GPS telemetry
- 📡 Wi-Fi communication
- ⚡ FastAPI backend
- 🔄 WebSocket real-time communication
- 🖥️ Web-based monitoring dashboard
- 🗃️ SQLite database
- 🧠 Ollama + Llama 3.2 local AI assistant
- 🗺️ Leaflet.js + OpenStreetMap

The robot captures images while moving along the railway track. The images
are transmitted to the backend, processed using AI models, and the results
are displayed on the dashboard.

---

# 🏗️ System Architecture

```text
                         RAILGUARD AI
                              │
             ┌────────────────┴────────────────┐
             │                                 │
             ▼                                 ▼
      ESP32-S3 Camera                    Ultrasonic Sensor
             │                                 │
             │ Wi-Fi                           │
             └────────────────┬────────────────┘
                              │
                              ▼
                     Python FastAPI
                         Backend
                              │
              ┌───────────────┼───────────────┐
              │               │               │
              ▼               ▼               ▼
           OpenCV          YOLO best.pt     YOLOv8n
              │            Crack Detection   Objects
              │
              └───────────────┬───────────────┘
                              │
                              ▼
                       Data Processing
                              │
                ┌─────────────┴─────────────┐
                │                           │
                ▼                           ▼
             SQLite                      Ollama
            Database                    Llama 3.2
                │                           │
                └─────────────┬─────────────┘
                              │
                              ▼
                    RailGuard Dashboard
                              │
            ┌─────────────────┼─────────────────┐
            │                 │                 │
            ▼                 ▼                 ▼
          Alerts           History          GPS / Map

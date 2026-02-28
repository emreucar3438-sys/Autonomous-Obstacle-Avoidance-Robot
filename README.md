# Autonomous Obstacle Avoidance Robot with Signal Filtering

This project features an intelligent mobile robot designed to navigate autonomously while avoiding obstacles. It stands out by implementing real-time signal processing techniques to ensure reliable sensor data and smooth motion control.

## 🚀 Key Technical Features

* **Signal Processing (Moving Average Filter):** To handle the inherent noise of the HC-SR04 ultrasonic sensor, the system implements a **Circular Buffer-based Moving Average Filter**. This smooths out "spiky" readings and prevents erratic robot behavior.
* **State Machine Logic:** The robot operates on a structured state machine (PATH_CLEAR, OBSTACLE_DETECTED, etc.), ensuring predictable and robust transitions between movements.
* **Dynamic Speed Modulation:** PWM-based velocity control allows the robot to slow down as it approaches obstacles, mimicking more complex industrial robotic systems.
* **Hardware Abstraction:** The code is structured with a clear separation between high-level logic and low-level motor/sensor hardware control.

## 🛠️ Hardware Stack
* **Microcontroller:** Arduino (Uno/Nano)
* **Sensors:** HC-SR04 Ultrasonic Sensor
* **Actuators:** SG90 Servo Motor, DC Gear Motors
* **Motor Driver:** L298N / L293D

## 📈 Algorithm Overview
1.  **Data Acquisition:** Continuous 100ms interval sampling.
2.  **Noise Reduction:** New samples are integrated into a 5-point moving average.
3.  **Proximity Analysis:** Speed is adjusted dynamically (Fast/Medium/Slow) based on the filtered distance.
4.  **Collision Avoidance:** Upon detecting a close obstacle, the robot performs a 180-degree environment scan via servo to find the optimal escape path.

## 💻 Installation
1. Clone the repository.
2. Ensure you have the `NewPing` and `Servo` libraries installed in your Arduino IDE.
3. Upload the `.ino` file to your board.

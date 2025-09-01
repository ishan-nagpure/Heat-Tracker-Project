# Heat-Tracker-Project
Automatically find, follow, and monitor any heat source with this project, a smart, servo-driven device that brings thermal tracking to your workbench. Whether you're a hobbyist looking for a captivating project, a student exploring robotics, or a technician needing a simple monitoring solution, this project is your eye in the world of heat.

This project is built on the powerful ESP32 platform, making it a fantastic educational tool for learning about sensors, robotics, and real-time control systems.

Features
Automatic 180° Scanning: The turret continuously pans across a 180-degree arc to search for heat signatures.

Precise Target Locking: Utilizes a Melexis MLX90614ESF-DCI sensor with a narrow 35° Field of View (FOV) to isolate and lock onto specific heat sources.

Real-Time Tracking: A dual-axis pan-and-tilt mechanism actively follows the detected heat source.

Audible Alarm: An onboard buzzer provides an immediate alert when a target's temperature surpasses a pre-defined critical limit.

Serial Data Monitoring: Outputs live temperature and position data to the Serial Monitor for debugging and monitoring.

How It Works
The system operates in a continuous loop with a simple but effective logic:

Scan Mode: The pan servo sweeps from 0 to 180 degrees. At each step, the MLX90614 sensor takes a temperature reading.

Detect Mode: If a temperature reading exceeds the HEAT_THRESHOLD, the system stops scanning and locks onto that bearing.

Track Mode: The system makes small adjustments with the pan and tilt servos to keep the sensor aimed at the point of maximum heat.

Alarm Mode: If the locked-on temperature exceeds the ALARM_THRESHOLD, the buzzer is activated to signal a critical event.

Reset: If the heat source is lost (temperature drops below the threshold), the system returns to Scan Mode.

Hardware Components
Component

Quantity

Notes

ESP32 Development Board

1

NodeMCU-32S or similar



Melexis MLX90614ESF-DCI

1

Crucially, the DCI version with 35° FOV



SG90 Micro Servo Motors

2

For pan and tilt movement




Active Buzzer

1



Any 3.3V or 5V active buzzer will work Mini Pan/Tilt Camera Platform Bracket

1
Widely available kit for SG90 servos



Jumper Wires

Several

For making connections



External 5V Power Supply (Optional)

1

Recommended for powering the servo motors

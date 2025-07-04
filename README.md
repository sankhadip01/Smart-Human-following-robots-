This robot uses ultrasonic sensors and IR sensors to detect obstacles and line directions, and it automatically moves, turns, or stops based on its surroundings.”
“In this project, I’m using:
The NewPing library for ultrasonic distance measurement.
The Servo library to control a servo motor.
The AFMotor library to control four DC motors through a motor driver shield.
The main components are:
An ultrasonic sensor for obstacle detection.
Two IR sensors for line or path detection.
A servo motor to rotate the ultrasonic sensor for scanning.
Four DC motors to drive the robot.”
“In the `setup()` section:
I start serial communication to monitor sensor data.
The servo motor is attached to pin 10.
The servo sweeps from left to right (0° to 180°) and back to the front (90°). This helps the robot scan its surroundings during startup.
The IR sensors are connected to pins A2 (RIGHT) and A3 (LEFT) and set as inputs.
“In the `loop()` function, the robot:
Measures the distance to obstacles using the ultrasonic sensor.
Reads the IR sensors to detect the presence or absence of a line or path.
Prints this data to the Serial Monitor for debugging.
The robot’s movement decisions are based on sensor values:
✅ If both IR sensors detect the line **and** an object is between 10–30 cm away, the robot moves **forward** slowly.
✅ If the **right sensor is OFF** but the left is ON, the robot turns **right** by running the left motors forward and right motors backward.
✅ If the **left sensor is OFF** but the right is ON, the robot turns **left** by running the right motors forward and left motors backward.
✅ If **both sensors are OFF**, or if there’s no clear path, the robot **stops** by releasing all motors.
✅ If the distance is very close (1–10 cm), the robot also **stops** to avoid a collision.”

If you find this repository useful, consider giving it a star.
robotics-design-notes/
│
├── README.md
│
├── Projects/
│   └── Line_Follower_Robot/
│       ├── README.md
│       ├── Arduino_Code/
│       │   └── line_follower.ino
│       │
│       ├── Circuit_Diagram/
│       │   └── wiring.txt
│       │
│       └── Components/
│           └── components_list.md
│
└── Notes/
    └── Robotics_Fundamentals.md
# robotics-design-notes
A collection of robotics engineering notes, CAD designs, automation projects, Arduino experiments, and learning resources for students and engineers.
# 🤖 Robotics Design & Automation

A collection of robotics engineering notes, CAD designs, projects, and learning resources.

## 🚀 Contents

### 📚 Notes

* Robot Kinematics
* Robot Dynamics
* Control Systems
* Sensors & Actuators

### 🛠 CAD Designs

* Robotic Arm
* Mobile Robot
* End Effector Designs

### 💡 Projects

* Line Follower Robot
* Obstacle Avoidance Robot
* Pick and Place Robot

### 🔧 Tools & Software

* SolidWorks
* AutoCAD
* Fusion 360
* MATLAB
* ROS
* Arduino IDE

## 🎯 Goals

* Learn Robotics Engineering
* Develop Real-World Projects
* Share Engineering Knowledge
* Build a Professional Portfolio

## 👨‍💻 Author

Rabbi

Mechanical Design, Manufacturing & Automation
🔌 Circuit Connections

IR Sensor Left  -> Arduino D2
IR Sensor Right -> Arduino D3

L298N IN1 -> Arduino D8
L298N IN2 -> Arduino D9
L298N IN3 -> Arduino D10
L298N IN4 -> Arduino D11

L298N ENA -> 5V
L298N ENB -> 5V

Motor A -> Left Motor
Motor B -> Right Motor

Battery -> L298N Power Input
Arduino GND -> L298N GND
🤖 Arduino Code

line_follower.ino
#define LEFT_SENSOR 2
#define RIGHT_SENSOR 3

#define IN1 8
#define IN2 9
#define IN3 10
#define IN4 11

void setup() {
pinMode(LEFT_SENSOR, INPUT);
pinMode(RIGHT_SENSOR, INPUT);

pinMode(IN1, OUTPUT);
pinMode(IN2, OUTPUT);
pinMode(IN3, OUTPUT);
pinMode(IN4, OUTPUT);
}

void loop() {

int left = digitalRead(LEFT_SENSOR);
int right = digitalRead(RIGHT_SENSOR);

if(left == 0 && right == 0) {
forward();
}
else if(left == 1 && right == 0) {
turnLeft();
}
else if(left == 0 && right == 1) {
turnRight();
}
else {
stopRobot();
}
}

void forward() {
digitalWrite(IN1, HIGH);
digitalWrite(IN2, LOW);
digitalWrite(IN3, HIGH);
digitalWrite(IN4, LOW);
}

void turnLeft() {
digitalWrite(IN1, LOW);
digitalWrite(IN2, LOW);
digitalWrite(IN3, HIGH);
digitalWrite(IN4, LOW);
}

void turnRight() {
digitalWrite(IN1, HIGH);
digitalWrite(IN2, LOW);
digitalWrite(IN3, LOW);
digitalWrite(IN4, LOW);
}

void stopRobot() {
digitalWrite(IN1, LOW);
digitalWrite(IN2, LOW);
digitalWrite(IN3, LOW);
digitalWrite(IN4, LOW);
}
📖 Project README

Projects/Line_Follower_Robot/README.md
# Line Follower Robot

An Arduino-based autonomous robot that follows a black line using two IR sensors and an L298N motor driver.

## Features

* Automatic line tracking
* Left and right path correction
* Simple Arduino implementation
* Suitable for beginners

## Hardware Used

* Arduino Uno/Nano
* L298N Motor Driver
* 2 IR Sensors
* DC Motors
* Battery Pack

## Working Principle

The IR sensors detect the contrast between the black line and the white surface. The Arduino processes the sensor signals and controls the motors accordingly to keep the robot on the path.

## Author

Rabbi





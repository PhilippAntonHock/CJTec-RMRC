# CJTec-RMRC Robot Building Tutorial

This tutorial explains how to build the robot that the team CJTec used to get 1. Place in the Rapidly Manufactured Robot Challenge (RMRC) at the RoboCup German Open 2025.

---

### Table of Contents

1.0 Introduction

1.1 Abstract

1.2 Motivation

2.0 Mechatronics (Mechanical Engineering + Electrical Engineering)

2.1 Mechanics

2.1.1 General Structure

2.1.2 Suspension

2.1.3 Motor Mounting

2.1.4 3D Printing

2.2 Electronics

2.2.1 Control Unit

2.2.2 Motors

2.2.3 Cameras

2.2.4 Lidar

2.2.5 Router

2.2.6 Power Supply

2.2.7 Wiring

2.2.8 Cooling

4.0 Computer Science

4.1 Requirements

4.2 Abstract Implementation

4.3 Networking

4.4 Control

4.5 Camera and Imaging System

4.6 Vision

4.6.1 QR Code Recognition

4.6.2 Motion Detection

4.6.3 Landolt Ring Detection

4.6.4 Hazmat

4.7 System Diagnostics

5.0 Conclusion

5.1 Summary

5.2 Sources & References

---

### 1.0 Introduction

#### 1.1 Abstract

We are a working group from CJT-Gymnasium with the goal of building a rescue robot. The robot aims to explore hazardous environments, such as burning buildings, and report the situation to emergency services. This is achieved through an all-terrain, six-wheeled robot equipped with cameras for autonomous navigation. The robot is approximately 30 cm long and wide and is controlled by a Raspberry Pi 5 with extension boards. The operator does not see the robot directly during the course but relies on the transmitted camera image.

We have been participating in competitions like RoboCup for years and continuously develop the robot to eventually use it in real-life emergency rescue scenarios. We are preparing to participate in the RMRC sub-competition.

#### 1.2 Motivation

We hope this project will enable rescue services to deploy the robot in the future to help save lives. We have already contacted the volunteer fire department in Hüttenbach, which has shown interest in our rescue robot.

---

# Building the Robot

## 2.0 Mechatronics (Mechanical Engineering + Electrical Engineering)

### 2.1 Mechanics

####2.1.1 General Structure

The robot's base consists of two main plates and an aluminum profile system (Makerbeams). Threaded rods run along both sides, secured with counter nuts. The suspension is attached to these rods, consisting mainly of 3D-printed U-shaped mounts, springs, and additional threaded rods. Special 3D-printed parts secure the motor, while the wheels are attached to hubs designed for optimal fit.

#### 2.1.2 Suspension

We opted for a parallel suspension system. Compared to a single-axis suspension, parallel suspension ensures that the suspended wheel always remains at a 90° angle to the robot. This design allows for greater suspension travel and reduces the risk of the wheel getting stuck on uneven surfaces.

#### 2.1.3 Motor Mounting

Since the motors are mounted directly with the wheels rather than inside the robot, robust motor mounts were necessary. These mounts are designed to absorb radial forces from impacts and include protective features to prevent cable damage.

#### 2.1.4 3D Printing

Most of the robot's components are 3D-printed due to the complex geometries required for the suspension system. Carbon fiber-reinforced PETG was chosen for its strength, durability, and heat resistance. All parts were modeled in Fusion 360 and printed with 0.6mm nozzles for precision.

### 2.2 Electronics

#### 2.2.1 Control Unit

The robot is powered by a Raspberry Pi 5 with 8GB RAM. It controls the robot alongside the Eduart Free Kinematics Kit (FKK) as a motor controller. Custom-designed PCBs connect these components efficiently.

#### 2.2.2 Motors

The robot uses six Faulhaber motors (model 2224U018S R IEH2-512 2081 22GPT 89:1) with continuous torque of 1.3 Nm and peak torque of 3.5 Nm. This ensures smooth movement despite the robot's weight of approximately 6 kg.

#### 2.2.3 Cameras

Two cameras are used, one at the front and one at the back, allowing quick switching between forward and reverse driving. The cameras have a resolution of 1920x1080 pixels.

#### 2.2.4 Lidar

A Lidar is used to create a 2D or 3D map of the surroundings, aiding autonomous navigation.

#### 2.2.5 Router

The TL-WR802 nano router is used to facilitate communication. Despite sponsorship requests, no upgraded router was acquired before submission.

#### 2.2.6 Power Supply

A custom Nickel-Metal Hydride battery (24V, 2450 mAh) powers the robot. It fits snugly between the base plates to lower the center of gravity and improve stability.

#### 2.2.7 Wiring

Wiring was designed to handle a maximum current of 8 A, ensuring safety and efficiency using AWG16 cables.

#### 2.2.8 Cooling

A heatsink and fan are attached to the Raspberry Pi 5 to prevent overheating during operation.

## 4.0 Computer Science

#### 4.1 Requirements

The robot's software must meet requirements for adaptability, reliability, and rapid analysis in hazardous situations.

#### 4.2 Abstract Implementation

The software is built using ROS2, a framework known for reliability in performance-critical applications.

#### 4.3 Networking

The robot utilizes both 5 GHz and 2.4 GHz Wi-Fi technologies to manage data transmission efficiently. Bandwidth optimization techniques are applied to ensure essential data flows in low-signal conditions.

#### 4.4 Control

The robot is controlled using a "Logitech Extreme 3D Pro Joystick," with customized calibration for sensitivity and joystick malfunctions.

#### 4.5 Camera and Imaging System

Multiple camera nodes are implemented with adjustable settings for image quality and transmission frequency.

#### 4.6 Vision

Includes QR code recognition, motion detection, Landolt ring recognition, and Hazmat sign detection using advanced image recognition algorithms.

#### 4.7 System Diagnostics

A diagnostic system monitors the robot's condition, including temperature, internet connectivity, and voltage levels to prevent unexpected failures.

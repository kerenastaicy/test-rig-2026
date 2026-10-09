# test-rig-2026
# INTELLIGENT SORTING SYSTEM


## PROJECT OVERVIEW

The Intelligent Sorting System is an automated conveyor-based sorting mechanism designed to identify and sort objects into designated bins based on their type. The system uses computer vision for object classification and an ESP32 microcontroller for coordinating conveyor movement, sensor input, and servo-controlled sorting.

The system begins with objects placed on the conveyor belt manually. There is no feeder mechanism. Objects are transported to a designated inspection area, where a camera captures images for classification using a Python-based computer vision program. The system classifies each object as a nut, bolt, or miscellaneous object.

Once the classification is complete, the ESP32 controls the conveyor to transport the object towards the sorting end. An IR sensor detects the object's arrival, allowing the controller to stop the conveyor and actuate an MG995B servo motor attached to a movable chute. The chute rotates to the appropriate angle, directing the object into its designated bin through gravity.

The system follows a sequential control process to coordinate object identification, transportation, and sorting while minimizing the possibility of misclassification or mixing consecutive objects.


## SYSTEM ARCHITECTURE

The project consists of the following subsystems:

-Conveyor Mechanism: Transports objects from the inspection area to the sorting end using a NEMA 17 stepper motor.
-Computer Vision: Uses Python and OpenCV to process camera images and classify objects as nuts, bolts, or miscellaneous items.
-Microcontroller: An ESP32 coordinates the conveyor motor, IR sensor, and servo actuator, while communicating with the computer vision program.
-Motor Driver: A DRV8825 drives the NEMA 17 stepper motor responsible for conveyor movement.
-Object Detection Sensor: An IR sensor positioned at the end of the conveyor detects an arriving object and signals the controller.
-Servo-Actuated Sorting Chute: An MG995B servo rotates a gravity-fed chute to direct objects into the appropriate collection bin.
-Power Supply: A 12 V SMPS supplies the motor driver, while a buck converter provides an appropriate regulated supply for the servo.


##WORKING PRINCIPLE
1.Object Placement: An object is placed manually on the conveyor belt.
2.Inspection: The conveyor transports the object to the inspection area, where movement can be paused for image capture and classification.
3.Classification: The computer vision program identifies the object as a nut, bolt, or miscellaneous item.
4.Communication: The classification result is transmitted from the computer to the ESP32.
5.Transportation: The ESP32 resumes conveyor movement, carrying the classified object towards the sorting end.
6.Arrival Detection: The IR sensor detects the object's arrival near the chute and signals the ESP32 to stop the conveyor.
7.Sorting: Based on the stored classification, the ESP32 positions the servo-actuated chute at the corresponding angle, allowing the object to fall into the designated bin.
8.Reset: The chute returns to its home position, and the system prepares for the next object.



##TECHNOLOGY AND COMPONENTS
Programming: Python, C++ (Arduino framework)
Computer Vision: OpenCV
Microcontroller: ESP32 DevKit
Conveyor Drive: NEMA 17 stepper motor and DRV8825 driver
Sorting Actuator: MG995B servo motor
Sensing: IR obstacle detection sensor
Communication: USB serial between the computer and ESP32, with Wi-Fi communication as a potential extension
Mechanical Design: CAD-designed conveyor structure and servo-mounted gravity chute


## FUTURE IMPROVEMENTS
-Improve classification robustness under varying lighting and background conditions.
-Add more object categories and collection bins.
-Implement wireless communication between the computer and ESP32.
-Improve system throughput and handling of consecutive objects.
-Add sorting statistics, event logging, and performance evaluation.

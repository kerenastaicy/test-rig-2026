# test-rig-2026
# INTELLIGENT SORTING SYSTEM


## PROJECT OVERVIEW

This project is an automated system that sorts mixed nuts and
bolts into three categories:
- Nut
- Bolt
- Misc
The system uses a phone camera for image capture, a laptop for
image processing and an ESP32 for mechanism control.


## OVERALL WORKING

1. Mixed objects are loaded into the feeder. A rotating disc moves the objects toward a curved guide, which directs them into an inclined gravity chute with ridges.
2. Feeder Monitoring: An IR beam-break sensor in the chute detects object movement and helps identify possible jams using a timeout.
3. Object Detection: A second IR beam-break sensor near the inspection area detects when an object arrives for classification.
4. Image Capture: The phone camera provides the video feed to the laptop, and the arrival signal triggers the classification process.
5. Classification: The laptop uses OpenCV + ML to classify the object as Nut, Bolt, or Miscellaneous.
6. Control: The classification result is sent to the ESP32 via Wi-Fi, which controls the physical sorting process.
7. Sorting: The ESP32 controls a servo-driven three-way diverter, directing the object into the appropriate bin.




# Gesture Controlled Robot
![Maintenance](https://img.shields.io/badge/Maintenance-Inactive-orange?style=for-the-badge)
## Tech Stack
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PlatformIO](https://img.shields.io/badge/PlatformIO-FF7F00?style=for-the-badge&logo=platformio&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
## Current Progress
![Project Status](https://img.shields.io/badge/Project_Status-Completed-2ea44f?style=for-the-badge)
![OS](https://img.shields.io/badge/OS-Windows_11-0078D4?style=for-the-badge&logo=windows&logoColor=white)
## WHAT
This is a project that uses fingers to move a robot in FBLR directions
> FBLR stands for Forward Backward Left and Right
## WHERE
The tested operating system is on **Windows 10/11** with Python 3.10 for the mediapipe
>[!TIP]
> Any operating system that has Python 3.10 should be able to run this project
## HOW
`mediapipe` detects the fingers and places points on them.Based on the no of fingers a UDP(User Datagram Protocol) running locally broadcasts the no of fingers
and is picked up by the Arduino Code which moves the robot.
>[!WARNING]
> If the UDP setup isn't attempted correctly, the project will not work

## INSTALLATION GUIDELINES
1. Clone the repo to your local directory in a Terminal using this command:
```bash
git clone https://github.com/rbijo/GestureControlledRobot.git
```
2. Then under `code/base code` check the `ArduinoCode.ino` for the SSID and Password. 
3. Plug in your ESP32 and burn the project once or run the `wifi_config.ino` to see the ESP32 WiFi Activated
4. In the WiFi list you should see the ESP32 name as given under SSID and the password will connect it
5. Once the WiFi APIP is setup then it is just a matter of running the `HandTracking.py` and ensuring all library requirements are met
>[!CAUTION]
> The default port used in both `HandTracking.py` and `ArduinoCode.ino` is 4210. If you are changing it, change it in both places

>[!TIP]
> For issues encountered during Installation submit an Issue on Github

## Key Changes 
1. **WHAT: Removed `#include <Arduino.h>` from the headers** <br>
WHY: When you use the espressif library in the Additional Boards URL Arduino compilation is used by default
2. **WHAT: Baud rate changed to 115200 in `Serial.begin(115200);`**<br>
WHY: ESP32 is designed to communicate on 115200 when using WiFi(Acc:Espressif Systems).However too high the rate less stable communication
4. **WHAT: `ledcSetup` and `ledcAttachPin` were removed and `analogWrite(**args)` is used**<br>
WHY: `ledcSetup` and `ledcAttachPin` are not supported fully in Arduino2 and works mostly in PlatformIO

Co-authored and hosted on Github with ❤ by @github/SwastikVoiD

This project was last maintained on 19th August 2026 and will be archived as of 20th August 2026

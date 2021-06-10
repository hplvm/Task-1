# MiniTask_1 of [Task 1]()
*-  Electronics Club*

### Objective
Select 15 distinct projects based on the below mentioned criteria:
- They should strictly deal with **different applications**
- The project should be of **medium-hard difficulty** to replicate
- At Least 8 projects out of 15 should **not include Arduino**


### Table of content

- [Project 1](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#1-ESP8266-01-IoT-Smart-Timer-for-Home-Automation)
- [Project 2](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#2music-reactive-led-strip)
- [Project 3](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#3-Log-temperature-data-to-Google-Sheets)
- [Project 4](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#4-Energy-Meter)
- [Project 5](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#5-Line-Follower-Robot-using-Microcontroller)
- [Project 6](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#6-Simple-Lane-Detection)
- [Project 7](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#7-ATtiny85-Ring-Watch)
- [Project 8](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#8-Make-an-Autonomous-Follow-Me-Cooler)
- [Project 9](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#9-DIY-Gesture-Controlled-Arduino-Based-Air-Mouse-using-Accelerometer)
- [Project 10](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#10-Arduino-Radar)
- [Project 11](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#11-Sun-Tracking-Solar-Panel-Project-using-Microcontroller)
- [Project 12](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#12-RFID-Based-Attendance-System)
- [Project 13](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#13-Third-Eye-for-The-Blind)
- [Project 14](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#14-Wunderpixel)
- [Project 15](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#15-ESP32-VGA-Snake)

---
## 1. [ESP8266-01 IoT Smart Timer for Home Automation](https://www.instructables.com/ESP8266-01-IoT-Smart-Timer-for-Home-Automation/)
### 1.1 WHY?
If user wants to change the duration of the timer of commercial timer,
he has to go to the physical location of the timer, which in typical use case,
far to reach, say for turning on the motor for filling the tank, 
the user needs to reach  the timer and outlets which are generally located 
outside the house. 

![Image](https://content.instructables.com/ORIG/FAO/XWX0/J4IQ6S2Q/FAOXWX0J4IQ6S2Q.jpg?auto=webp&frame=1&fit=bounds&md=2f25d8eb38fff1c7ca7e94f461f585e5)

>Image(s) are used from the [project page](https://www.instructables.com/ESP8266-01-IoT-Smart-Timer-for-Home-Automation/). 

### 1.2 Features
- Adjust timer using internet(**IoT**)
- Operate with minimal user actions(**Smart**)
- Turn On/Off according to set times(**Timer**)

### 1.3 (Main)Components used
- ESP8266-01 
- Relay
- Power supply
### 1.4 Working
ESP8266-01 is programmed to host a web-server in local network, to get
user inputs, and control relay as per the user inputs, which in-turn
controls the appliance connected to it.

### 1.5 Improvements possible(*just my opinion*)
The project use ESP8266-01, as it is cheaper and compact, but it requires additional power-supply, and the size finnaly is quite large. But instead ESP8266 node-mcu can be used, it is bigger than ESP8266-01, but the hassle of power-supply is solved with a basic mobile charger, which considerable decreases the work input needed, with no or little increase in cost.

![Image](https://content.instructables.com/ORIG/F14/OTLV/J4IQ6LOF/F14OTLVJ4IQ6LOF.jpg?auto=webp&frame=1&width=438&fit=bounds&md=c77e84edf6f3aa1c0212d9527b0a580a)

>Image(s) are used from the [project page](https://www.instructables.com/ESP8266-01-IoT-Smart-Timer-for-Home-Automation/). 


[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 2.[Music Reactive LED Strip](https://www.hackster.io/buzzandy/music-reactive-led-strip-5645ed)

![Image](https://hackster.imgix.net/uploads/attachments/391591/screen_shot_2017-12-08_at_11_00_05_am_OmlJE76dy1.png?auto=compress%2Cformat&w=900&h=675&fit=min)



>Image(s) are used from the [project page](https://www.hackster.io/buzzandy/music-reactive-led-strip-5645ed#overview). 

### 2.1 WHY?
It just looks cool!!!!!!!!!!!!!

### 2.2 Features
- To change colour/intensity/saturation of led strip to change according to **sound** in surrounding(music).
- A knob to adjust gain.

### 2.3 (Main)Components used
- Arduino Nano
- WS2812B LED Strip
- Adafruit Electret Microphone / Max4466 Amplifier
- Potentiometer
- 12V Power supply and 5V DC-DC Converter

### 2.4 Working
The surrounding sound is recorded by microphone and amplified, and processed by arduino nano to control LED strip as a function of input sound. 

### 2.5 Improvements possible
Adding a **aux input** would be an better idea, as it eliminates noise.

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 3 [Log temperature data to Google Sheets](https://www.hackster.io/24Ishan/log-temperature-data-to-google-sheets-0b189b)
### 3.1 WHY?
Micro-controllers generally have limited storage, this projects adds potentially infinite **storage to store log data**.

### 3.2 Features
- Measuring temperature every 1 second.
- Logging the temperature data into google sheets.

### 3.3 (Main)Components used
- DFRobot DHT22 Temperature and Humidity Sensor
- NodeMCU ESP8266

### 3.4 Working
- DHT22 communicates with ESP8266 using *single-bus* serial communication to report temperature value.
- A google sheet is been created and google script is written and deployed to access it.
- ESP8266 reads data every second and logs in sheet. 

### 3.5 Improvements possible
*None*

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 4 [Energy Meter](https://www.instructables.com/Arduino-Energy-Meter-V20/)
![image](https://content.instructables.com/ORIG/FZN/ZP7M/JHQJLNFC/FZNZP7MJHQJLNFC.jpg?auto=webp&frame=1&width=687&height=1024&fit=bounds&md=9d3f245d5af505b620e992fa1097f1fb)

### 4.1 WHY?
To be concious on **power consumed** by individual appliance in addition to total consumption.

### 4.2 Features
- Displays power, energy, cost.
- Also integratted to blynk app to view data from phone.
 
### 4.3 Components used
- Wemos D1 mini pro (ESP8266)
- Current Sensor -ACS712
- OLED Display 

### 4.4 Working
![image](https://content.instructables.com/ORIG/F49/K09G/JHKU4C8P/F49K09GJHKU4C8P.jpg?auto=webp&frame=1&fit=bounds&md=291281f0e96567ca732bd2c805ba97dc) 

>Image(s) are used from the [project page](https://www.instructables.com/Arduino-Energy-Meter-V20/). 

### 4.5 Improvements possible
Linking with any **Home assistant**, will make this projectable **scalable**.

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 5 [Line Follower Robot using Microcontroller](https://www.electronicshub.org/line-follower-robot-using-microcontroller/)
![image](https://www.electronicshub.org/wp-content/uploads/2015/10/Line-Follower-Robot-using-Microcontroller-Image-1.jpg)

### 5.1 WHY?
This project can be scaled to be used in industrial applications, such as transporting of parts within factory.

### 5.2 Features
- follows the line

### 5.3 (Main)Components used
- 8051 Microcontroller
- Motor driver Module (L298N)
- Robot Chassis with Motors
- IR Sensors x 2


### 5.4 Working
IR sensors resisitance varies with the amount of IR light recieved, and black surface absorbes all lights. So IR sensors have **different resistances** for Black and White surfaces. The 

### 5.5 Improvements possible
Microcontroller used is old and bulky. Instead ESP8266/ESP32 can be used as they have additional **Wi-Fi** capabilities.

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 6 [Simple Lane Detection](https://www.hackster.io/kemfic/simple-lane-detection-c3db2f)

![image](https://hackster.imgix.net/uploads/attachments/487646/download_eomQtNZs24.png?auto=compress%2Cformat&w=900&h=675&fit=min)

### 6.1 WHY?
- Can be used as support for drivers with **weak vision**.
- Can also also be integrated to automatic driving system.


### 6.2 Feature
Can highlight lanes in road.


### 6.3 (Main)Components used
- Raspberry pi
- Nvidia Jetson TX1(CUDA accelerator)
- Software/Libraries used:
	- OpenCV
	- numpy, matplotlib, moviepy

### 6.4 Working
- Camera module is used to capture images, and which is accessed by raspberry pi.
- Multiple filtors are applied to image, to seperate the lane line, this filtering generally done using matrix multiplication, which is accelerated by nvidia jetson tx1.
- the desired area is filled with colours, and images are stiched into video.


### 6.5 Improvements possible
*none*

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 7 [ATtiny85 Ring Watch](https://www.instructables.com/ATtiny85-Ring-Watch/)
![](https://content.instructables.com/ORIG/FUW/FMUQ/IKFQ06NI/FUWFMUQIKFQ06NI.jpg?auto=webp&frame=1&width=700&height=1024&fit=bounds&md=148146624a1de8300aa1097eb5d80bff)

### 7.1 WHY?
It look cool!!!!!!!

### 7.2 Feature
Display time, day and date.

### 7.3 (Main)Components used
- ATTINY85V-10SU
- CR1220 battery
- SSD1306 display 64x32

### 7.4 Working
- display communicated with attiny85 via i2c communication
- attiny85 updates and keep track o time
- it also updates the display every second 

### 7.5 Improvements possible
*none*

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 8 [Make an Autonomous Follow Me Cooler](https://www.hackster.io/hackershack/make-an-autonomous-follow-me-cooler-7ca8bc)

![](https://hackster.imgix.net/uploads/attachments/304927/cover_x_sm_ryeceUbLlV.gif)

### 8.1 WHY?
This project can be people with weak memory, who forget things. And also for blind people.

### 8.2 Feature
Follow the owner(that connects to a smartphone via Bluetooth and uses GPS to navigate.) 

### 8.3 (Main)Components used

- Arduino UNO
- Parallax PAM-7Q GPS Module
- Adafruit HMC5833l Compass
- HC-05 Bluetooth Module
- Motors and wheels

### 8.4 Working

The gps of owner is send to arduino via bluetooth with the help of HC-05 module. The HMC5833l gps sensors collects the box's location, and arduino calculated the difference in gps of box and owner and controlls motor to move towards the owner.

### 8.5 Improvements possible

The is a bottleneck in this project, the gps can function almost anywhere in the globe, but the maximum distance between owner and box is restricted by bluetooth module to approximately 10m. If the owners gps information is sent to box over the internet, this can be resolved.

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 9 [DIY Gesture Controlled Arduino Based Air Mouse using Accelerometer](https://circuitdigest.com/microcontroller-projects/diy-gesture-controlled-arduino-air-mouse-using-accelerometer)
![](https://circuitdigest.com/sites/default/files/projectimage_mic/DIY-Gesture-Controlled-Arduino-based-Air-Mouse-using-Accelerometer.jpg)

### 9.1 WHY?
In seminar, if the presenter wants to use the cursor, he/she is forced to reach is laptop/pc to do so. But with this project he/she can control the cursor without the hassle.

### 9.2 Features
- Move cursor using gestures

![](https://circuitdigest.com/sites/default/files/inlineimages/u1/Gesture-Controlled-Arduino-based-Air-Mouse-using-Accelerometer.jpg)

### 9.3 (Main)Components used
- Arduino Nano
- Accelerometer ADXL335 Module
- Bluetooth HC-05 Module
- Push buttons
- Python Installed computer

### 9.4 Working
The accelerometer and push buttons data are collected by arduino nano, and mouse controlling data are caculated and send to computer using bluetooth serial, which is read by python using serial module and pyautogui module is used to simulate mouse movements and clicks.


### 9.5 Improvements possible
As data flows to nano then bluetooth then serial then python script, it is pron to noise, and have high latency, in other words it will be less responsive and inaccurate. To resolve above mentioned issues ESP32 can be used instead of arduino nano, as it has inbuilt bluetooth, so can configured to act as bluetooth mouse.

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 10 [Arduino Radar](https://www.instructables.com/Arduino-Radar-1/)


### 10.1 WHY?
Can be used in simple robots which generally uses multiple pairs of static sensors.

### 10.2 Features
Finds obstacles over a field of view of 180 degree

### 10.3 (Main)Components used
- Arduino Board
- Servo motor (mg-996)
- HC-SR04 Ultrasonic sensor

### 10.4 Working
The measurements of ultrasonic sensor is recorded at different angles by setting servo to the angle, it repeats 0-180-0 degree motion to get data continuously. And the data is send to computer using serial, which is processed by the software "processing" to give beatiful animation.

![gif](https://github.com/hplvm/Task-1/blob/main/media/minitask1_prj10.gif)



### 10.5 Improvements possible
*none*

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 11 [Sun Tracking Solar Panel Project using Microcontroller](https://www.electronicshub.org/sun-tracking-solar-panel/)

![gif](https://github.com/hplvm/Task-1/blob/main/media/minitask1_prj11.gif.gif)

### 11.1 WHY?
To increase energy harvested by solar panel..

### 11.2 Features
Moves itself to face towards the san.

### 11.3 (Main)Components used
- Solar panel
- ATmega328 Micro Controller
- Light Dependent Resistor (LDR) x 2

### 11.4 Working
Two LDR's are located on either side of solar panel, if difference of measured values of them are not close to 0, the servo move till their difference is almost 0. 

### 11.5 Improvements possible
We should not spend more energy in the process of harvesting energy, than what extra energy is harvested. For maximum efficiency the microcontroller should take measurement and adjust the panel only every 15 minutes or so, and sleep rest of the time.

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 12 [RFID Based Attendance System](https://www.electronicshub.org/rfid-based-attendance-system/)
![image](https://www.electronicshub.org/wp-content/uploads/2014/06/RFID-Based-Attendance-System-Circuit-Diagram.jpg)

### 12.1 WHY?
Contactless

### 12.2 Features


### 12.3 (Main)Components used
- ATMEGA8 Microcontroller
- RFID Reader
- RFID Tags
- LCD display

### 12.4 Working
When the RFID reader detects the ID card, it will send the unique card no to the microcontroller via serial terminal. With the help of suitable programming, we need to compare the received card no. with the numbers that are already stored in the microcontroller or any database.Once, if any of these numbers are match with the received card no., then the corresponding name stored in that no. is displayed on the LCD display and also the attendance for the name stored in the corresponding number is marked. 

### 12.5 Improvements possible
*none*

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 13 [Third Eye for The Blind](https://www.hackster.io/muhammedazhar/third-eye-for-the-blind-8c246d)
![](https://hackster.imgix.net/uploads/attachments/315304/third2beye2bfor2bthe2bblind_we34TitvS0.jpg?auto=compress%2Cformat&w=900&h=675&fit=min)

![](https://hackster.imgix.net/uploads/attachments/315283/sketch_XO2tmjhP5Y.jpg?auto=compress%2Cformat&w=740&h=555&fit=max)

### 13.1 WHY?
To help blind people to find things in vicinity without touching them. 

### 13.2 Features
The vibrating motor vibrates to notify the user, with intensity proportional to the cloness of the obstacle and rings buzzer if too close.

### 13.3 (Main)Components used
- Arduino pro mini(s)
- Ultrasonic sensors
- Vibrating motors

### 13.4 Working
The Ultrosonic sensors can be used to find the distance to the obstacle, which can be used by arduino pro mini to decide desired output with combination of vibrating motor and buzzers.


### 13.5 Improvements possible
In this 5 arduino pro mini's are used, instead multiplexers could have been used to connect 5 ultrasonic sensors. 

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 14 [Wunderpixel](https://www.hackster.io/leohill/wunderpixel-91b031)
![gif](https://github.com/hplvm/Task-1/blob/main/media/minitask_prj14.gif)

### 14.1 WHY?
Displays provid user with useful easily understandable information. 

### 14.2 Features
LED matrix has 64x32 LED, which can used to display graphic contents.

### 14.3 (Main)Components used
- NodeMCU ESP8266
- Bus Transceiver, 74HC245

### 14.4 Working
The ESP8266 just has approximately 25 GPIO, so the upper limit of no. LED's that can be connected to it also 25, then how is this project posiible?. The circuit uses multiplexing techniques to controll all individual LED's. 


### 14.5 Improvements possible
*none*

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

## 15 [ESP32 VGA Snake](https://www.instructables.com/ESP32-VGA-Snake/)
![](https://content.instructables.com/ORIG/FDA/RC1L/JYWTYJL0/FDARC1LJYWTYJL0.jpg?auto=webp&frame=1&width=877&height=1024&fit=bounds&md=827efd7dc3393dba1c16e492cc63e9ce)

### 15.1 WHY?
Displays provid user with useful easily understandable information.

### 15.2 Features
Can create any graphics(even 3D) in much higher resolution than the displays usually used in electronics projects.

### 15.3 (Main)Components used
- ESP32
- VGA breakout board
- Push buttons

### 15.4 Working
The VGA protocol is mimiced by ESP32 to produce images. 

### 15.5 Improvements possible
*none*

[Table of content](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#Table-of-content)

---

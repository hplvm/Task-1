# MiniTask_1 of [Task 1]()
*-  Electronics Club*

### Objective
Select 15 distinct projects based on the below mentioned criteria:
- They should strictly deal with **different applications**
- The project should be of **medium-hard difficulty** to replicate
- At Least 8 projects out of 15 should **not include Arduino**

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
IR sensors resisitance varies with the amount of IR light recieved, and black surface absorbes all lights. So IR sensors have different resistances for Black and White surfaces. The 

### 5.5 Improvements possible
Microcontroller used is old and bulky. Instead ESP8266/ESP32 can be used as they have additional Wi-Fi capabilities.


---

## 6 [Simple Lane Detection](https://www.hackster.io/kemfic/simple-lane-detection-c3db2f)

![image](https://hackster.imgix.net/uploads/attachments/487646/download_eomQtNZs24.png?auto=compress%2Cformat&w=900&h=675&fit=min)

### 6.1 WHY?
- Can be used as support for drivers with weak vision.
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

---

## 8 [Make an Autonomous "Follow Me" Cooler](https://www.hackster.io/hackershack/make-an-autonomous-follow-me-cooler-7ca8bc)

![](https://hackster.imgix.net/uploads/attachments/304927/cover_x_sm_ryeceUbLlV.gif?auto=format%2Ccompress&gifq=35&w=900&h=675&fit=min&fm=mp4)

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

---

## 9 


### 9.1


### 9.2


### 9.3


### 9.4 


### 9.5

---

# MiniTask_1 of [Task 1](https://github.com/hplvm/Task-1)
*-  Electronics Club*

### Objective
To understand how a project progresses over time.

### Quick links

[Energy Meter](https://github.com/hplvm/Task-1/blob/main/MiniTask_2.md#1-Energy-Meter)

[ESP8266 01 IoT Smart Timer for Home Automation](https://github.com/hplvm/Task-1/blob/main/MiniTask_1.md#2-ESP8266-01-IoT-Smart-Timer-for-Home-Automation)

---

## 1 [Energy Meter](https://www.instructables.com/Arduino-Energy-Meter-V20/)

### 1.1 Problem statement
Make a power monitoring system which calculates "Apparent Power", "Real Power", "Energy Comsumed".(As of now I am skipping integration of this project to Iot platforms link Blynk) and displays output.

### 1.2 Ideation

We know that for DC 
<img src="https://render.githubusercontent.com/render/math?math=Power=Voltage*Current">

But for AC, it is not going to as simple as that.

So the first step is to understand AC voltage, current and power and their relationships.

Let's look at a simple AC circuits, with just either resistive or capacitive or inductive load connected between neutral and phase wires of AC. 
Now let us look at the common Voltage graph and individual Currents graphs.

![img](https://2.bp.blogspot.com/-NtEZnu1EAYw/VManOlRo-SI/AAAAAAAAA2E/2W-9pQqmavg/s1600/Voltage%2Band%2Bcurrent%2Brelationship%2Bin%2Bresistive%2C%2Binductive%2Band%2Bcapacitive%2Bcircuits.jpg)

We can observe that Current need not follow Voltage always.

Now let's observe the Power graph below:

![img](https://2.bp.blogspot.com/-wpTThA7emFk/WICY5Z2KzLI/AAAAAAAAAUA/sZLU0mORUssoGHgdZhCljRVMjnGcqJ7GgCLcB/s1600/A.png)

<img src="https://render.githubusercontent.com/render/math?math=P_i=V_i*I_i">, where i reperesents instantaneous.

Power can take both positive and negative value. 
If the load is purily capacitive or inductive, the current and voltage will shift by an angle of 
<img src="https://render.githubusercontent.com/render/math?math=90^o"> 
the power function will be a sinosodial function.
 

Now, Enery is Power x Time, or more precisely 
<img src="https://render.githubusercontent.com/render/math?math=\int Pdt"> 

Now if we calculate the energy over a complete cycle for capacitive or inductive load, it would be 0, as they act as load for first half of cycle and act as generator the other half.

But if the circuit is comnbination of C, R and L loads(which is usually the case), some power is used to do work, some power is stored temporarly and given back to source. 

The household Electricty bill only includes the power that does work.

The AC Power can be visualized as a vector with two perpendicular components. 

![](https://github.com/hplvm/Task-1/blob/main/media/minitask2_acpower.png)

The apparent power is just the product of Current and Voltage. This can can split into **real power** and **reactive** or **wattless** power. Only Real Power contributes to energy consumtion. And as the name implies wattless power doesn't consume power.

<img src="https://render.githubusercontent.com/render/math?math=P_{real}=P_{apparent}*cos(\phi)"> 

<img src="https://render.githubusercontent.com/render/math?math=P_{wattless}=P_{apparent}*sin(\phi)"> 

where 
<img src="https://render.githubusercontent.com/render/math?math=\phi"> 
is the phase difference between V and I.

There are also other types power, like deformed power which is caused by deformation of sinosodial current wave.

The summary, is power calculation of AC is not simple. We need to take as many as sample of Voltage and Current values and calculate the Power and Energy.

### 1.3 Planning

Sensors --> Microcontroller --> Display

**Parts of pipeline**
1. Sensors

| Sensors |           Use             |    Feasibility    | Advantage | Disadvantage |
|---------|---------------------------|-------------------|-----------|--------------|
| ZMPT101B|Convert High voltages to voltages that microcontroller can read|Easy to use, just connect and use|There are commercial sensors which can convert (-230V,230V) to (0,3.3) |Hard to calibrate to it maps the High voltages into entire voltage range which microcontroller can read|
| SCT013  |Converts mains current to lower current|Easy to use, just connect and use|This sensors clip design so that it can be openned and cliiped around the wire|As it can measure currents upto few 10's of Amp, measuring small currents can be difficult|

2. Microcontroller

| Microcontroller |    Feasibility    |    Advantage    |    Disadvantage    |
|-----------------|-------------------|-----------------|--------------------|
|  Arduino mega   | can be used as it has atleast 2 ADC pins| Emon library already available to calculate the power calculation|can't manage time specific tasks| 
| ESP8266 | can't be used as it has only one adc|-|-|
|ESP32| can be used as it has atleast 2 adc pins| emon library is available for power calculations, can be programmed with RTOS to do time specific parallel tasks, and also has Wi-Fi capability for Iot integration | Littile bit hard to program comparitively| 

3. Display

| Display  | Feasibility  | Advantage  | Disadvantage |
|----------|--------------|------------|--------------|
|OLED 128x64|Can be used as we only need to display 3 lines| compact, cheap and reliable |-|


### 1.4 Deciding final pipeline

1. Sensors: **ZMPT101B** and **SCT013**
1. Microcontroller: among arduino mega and ESP32, **ESP32** has clear advantage of RTOS and Wi-Fi capability. 
1. Display: as display is not of much importance simple generic **OLED 128x64** will be sufficient.

### 1.5 Prorotyping

Builting the circuit and testing with differnt loads, and calibirating with commercial power measuring tool to get precise outputs.
And finally debugging if any undesirable outputs found.


I thing my ideation for this project is better than [this project](https://www.instructables.com/Arduino-Energy-Meter-V20/), as in the original project ESP8266 was which only has 1 adc pin, and only current is measured, so the results can be inaccurate.

#### Sources

- [Arduino Energy Meter - V2.0 : 12 Steps (with Pictures) - Instructables](https://www.instructables.com/Arduino-Energy-Meter-V20/)
- [(3) DIY ESP32 AC Power Meter (with Home Assistant/Automation Integration) - YouTube](https://www.youtube.com/watch?v=PSzkaSy5lHY&t=126s)
- [AC power - Wikipedia](https://en.wikipedia.org/wiki/AC_power)
- [RLC Series AC Circuits | Physics](https://courses.lumenlearning.com/physics/chapter/23-12-rlc-series-ac-circuits/)

---

## 2 [ESP8266 01 IoT Smart Timer for Home Automation](https://www.instructables.com/ESP8266-01-IoT-Smart-Timer-for-Home-Automation/)

### 2.1 Problem statement
Make a timer AC outlet which turns on and off at times specified by user, and also a webserver to change the turn on/off times from anywhere in the house.

### 2.2 Ideation


 *M i c r o c o n t r o l l e r*   --------------------------------------> *Relay*

<img src="https://render.githubusercontent.com/render/math?math=\ \ \ \ \ \ \ \ \ \ \ \ \downarrow\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ .">  <img src="https://render.githubusercontent.com/render/math?math=\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \uparrow"> 

*Webserver* <img src="https://render.githubusercontent.com/render/math?math=\rightarrow"> *User input*


The microcontroller checks time regularly, and if it same turn on/off time, it turns on/off AC outlet.
A webserver can be made and user can change turn on/off times in it.

### 2.3 Planning

**Parts of pipeline**
1. Microcontroller
	
| Microcontroller | Feasibility | Advantage | Disadvantage |
|---|---|---|---|
|ESP8266|It can be used as it has Web hosting capability and enough GPIO for interfacing Relay module|On the cheaper side comparitively|-|
|ESP32|It can be used as it has Web hosting capability and enough GPIO for interfacing Relay module|-|On the expensive side comparitively|

2. Relay 

|Relay module | Feasibility | Advantage | Disadvantage |
|--|--|--|--|
|Relay without octocoupler|Commercially available|Cheaper|Not enough isolation of High Volatage circuit and microcontroller|
Relay with octocoupler|Commercially available | Enough isolation of High Volatage circuit and microcontroller| Little Expensive |
### 2.4 Deciding final pipeline

Both ESP32 and ESP8266 can do the job, but ESP8266 is cheaper and compact.

Relay with octocoupler is preffered as it has higher protection at not much extra cost.

Webserver can be made using few lines of code using wifi librares for esp8266 in Arduino IDE.

### 2.5 Prorotyping

Connecting the component and testing the feature and debugging if any feature not working any undesirable outputs found.

#### Sources

- [ESP8266WiFi library — ESP8266 Arduino Core 3.0.0-22-gb4774edb documentation](https://arduino-esp8266.readthedocs.io/en/latest/esp8266wifi/readme.html)
- [ESP8266-01 IoT Smart Timer for Home Automation : 9 Steps (with Pictures) - Instructables](https://www.instructables.com/ESP8266-01-IoT-Smart-Timer-for-Home-Automation/)
- [Arduino/libraries/ESP8266WebServer at master · esp8266/Arduino](https://github.com/esp8266/Arduino/tree/master/libraries/ESP8266WebServer)

---

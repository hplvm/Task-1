# MiniTask_2 of [Task 1](https://github.com/hplvm/Task-1)
*-  Electronics Club*

### Objective
To understand how to debug a project.

### Quick links

---

# 1 [Energy Meter](https://www.instructables.com/Arduino-Energy-Meter-V20/)

# Troubleshooting
If the project doesn't work:

Connect the project to power supply and check whether power LED in ESP32 is ON/OFF:
- if [OFF](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#ESP32_powerLED_OFF)   (click on it to navigate)
- if [ON](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#ESP32_powerLED_ON)   (click on it to navigate)

## ESP32_powerLED_OFF
Change the power-supply(say mobile charger or powerbank) and observe the power LED. If the LED is
- [ON](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#ESP32_New_powersupply_ON)     (click on it to navigate)
- [OFF](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#ESP32_New_powersupply_OFF)   (click on it to navigate)

#### ESP32_New_powersupply_ON

>There was some problem with your old power-supply, it may be because the power requirements of ESP32 and attached components was not met. If it works in the new power-supply, continue using it.

#### ESP32_New_powersupply_OFF

>The ESP32 seems to be damaged, if any chip on the board becomes hot sometime after powering, then it is a strong sign of critical damage and considering buying a new board. 

## ESP32_powerLED_ON
- If reading of power etc are zero, ensure tight and secure connections between ESP32 and attached components, and connect according to schematic or information provided.
- If reading are non-zero but incorrect, try tweaking with sensitivity in code, untill you find a sweet spot.
- Display not working, check connection whether they are same as in schematic, if still doesn't work check with some display example code, if it doesn't work in that either, consider buying a new display.

---

# 2 [ESP8266 01 IoT Smart Timer for Home Automation](https://www.instructables.com/ESP8266-01-IoT-Smart-Timer-for-Home-Automation/)


# Troubleshooting

If the project doesn't work:

Check if power LED's of ESP8266 and relay is ON while powering them:
- if [both LED's are ON](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#Both_powerLED_ON)                   (click on it to navigate)
- if [atleast one of them is OFF](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#Atleast_one_PowerLED_OFF)  (click on it to navigate) 
	
## Atleast_one_PowerLED_OFF

If the component whose Power LED is OFF is:
- [ESP8266](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#ESP8266_powerLED_OFF)           (click on it to navigate)
- [Relay module](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#Relay_powerLED_OFF)    (click on it to navigate)
	
### ESP8266_powerLED_OFF

Change the power-supply(say mobile charger or powerbank) and observe the power LED. If the LED is
- [ON](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#ESP8266_New_powersupply_ON)     (click on it to navigate)
- [OFF](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#ESP8266_New_powersupply_OFF)   (click on it to navigate)

#### ESP8266_New_powersupply_ON

>There was some problem with your old power-supply, it may be because the power requirements of ESP8266 and attached components was not met. If it works in the new power-supply, continue using it.

#### ESP8266_New_powersupply_OFF

>The ESP8266 seems to be damaged, if any chip on the board becomes hot sometime after powering, then it is a strong sign of critical damage and considering buying a new board. 

### Relay_powerLED_OFF
Do all comibinations the below steps and observe power LED:
- Try pushing the jumper wires in place with gentle force, to check for loose connections.
- Change the wires connecting the module to microcontroller, to make sure there are no discontinuity within the wire.
- If the module uses seperate power-supply, try using any other compatible power-supply.(dont forgot to change the position of jumper in the relay module if powered externally)
- If <img src="https://render.githubusercontent.com/render/math?math=V_{cc}"> of module is connected to <img src="https://render.githubusercontent.com/render/math?math=V_{cc}"> of microcontroller, check datasheet of relay to find operating voltage, as ESP8266's <img src="https://render.githubusercontent.com/render/math?math=V_{cc}"> is 3.3 V, some relay module only work at 5 V. If that is the case use separate recommended power supply for relay module.

>If still no combination of the above steps made the Power LED glow, consider buying a new relay module.

## Both_powerLED_ON

- If [webserver is not working](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#Webserver_not_working)   (click on it to navigate)
- If webserver works but [relay doesn't turn on/off at specified time](https://github.com/hplvm/Task-1/blob/main/MiniTask_3.md#relay_doesnot_doesnot_on-off)   (click on it to navigate)


### Webserver_not_working

- Check if you have uploaded code with board as esp8266 and you have installed all libraries in the version specified by the creater.
- Check in the code if the ssid and password variable contains your local router's ssid and password, if not change it.
- Connect to the correct IP address,i.e of your ESP8266, to find IP address, add the below line after the loop which looks similar to ` while (WiFi.status() != WL_CONNECTED) { ... }`
```C++
Serial.println(WiFi.localIP());
```

### relay_doesnot_doesnot_on-off

- Check if all connections are tight and rigid, swap with new jumper wires if needed.
- Check with instructions provided or with schematic for connection between different pins, and replicate the same. 


#### Sources
- [How to get the IP address of a NodeMCU ESP8266 - Wia Community](https://community.wia.io/d/47-how-to-get-the-ip-address-of-a-nodemcu-esp8266)
- [ESP8266 01 IoT Smart Timer for Home Automation](https://www.instructables.com/ESP8266-01-IoT-Smart-Timer-for-Home-Automation/)

---


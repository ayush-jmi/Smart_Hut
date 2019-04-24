# Smart_Hut
This project displays company logo (inserted by us in the code), temperature, humidity, time, day and location (inserted by us in the code) on OLED 128*64 screen using I2c protocol. You can insert up to 40 screen patterns in the code. The author’s prototype is shown in Fig. 1.
COMPONENTS
The components used to make it are:-
1)	NodeMCU (ESP8266): NodeMCU is an open source Internet of Things platform with embedded controller that is programmed through Arduino IDE, to handle analog and digital received from sensors and to print data on OLED display. I use ESP8266 in place of Arduino UNO because dynamic memory of Arduino UNO is 2048 bytes and only one image can be uploaded in the code while ESP8266 has 81920 of dynamic memory and we can upload around 50 images in it.
2)	 Temperature Sensor (DHT11):  DHT11 is a Humidity and Temperature Sensor, which generates calibrated digital output. DHT11 can be interface with any microcontroller like Arduino, NodeMCU, etc. and get instantaneous results. DHT11 is a low cost humidity and temperature sensor which provides high reliability and long term stability.
3)	OLED Display: OLED (Organic Light-Emitting Diode) is a self light-emitting technology composed of a thin, multi-layered organic film placed between an anode and cathode. In contrast to LCD technology, OLED does not require a backlight. OLED possesses high application potential for virtually all types of displays and is regarded as the ultimate technology for the next generation of flat-panel displays.
4)	Push buttons:  A push button is a momentary or non-latching switch which causes a temporary change in the state of an electrical circuit only while the switch is physically actuated. An automatic mechanism (i.e. a spring) returns the switch to its default position immediately afterwards, restoring the initial circuit condition.
5)	Resisters (1000 Ohm):  A resistor is a passive two-terminal electrical component that implements electrical resistance as a circuit element. In electronic circuits, resistors are used to reduce current flow, adjust signal levels, to divide voltages, bias active elements, and terminate transmission lines, among other uses.
CIRCUIT & WORKING
The circuit diagram is shown in the fig. It is build around NodeMCU (ESP8266), DHT11 sensor, OLED 128*64, push buttons and resistors.
 The circuit has digital input to read values of temperature and relative humidity through DHT11 and two interrupts to change minutes, hours and days displayed on the OLED.
The circuit has 128*64 OLED to display company logo, temperature, time and location. Time can be change by using switches and location can be changed by changing the name of your area in the code.
The circuit runs on 5V power supply and has an internal battery which can be charged by mobile charger. The battery consists of four 3.3V lithium batteries and a power bank integrated circuit to work properly.
 
SOFTWARE
The code is written in Arduino programming language using Arduino IDE, which allows writing the code within few lines. 
To add board for ESP8266 in Arduino IDE, go to ->File ->Preferences and paste the below link in Additional Board Manager URLs.
https://arduino.esp8266.com/stabl/package_esp8266com_index.json
Open Boards Manager from Tools ->Board menu and install esp8266 platform. (Do not forget to select your NodeMCU board from Tools ->Board menu after installation).
You can download the code from the link below.
https://github.com/ayush-jmi/Smart_Hut/blob/master/logo.ino.ino
For printing an image on OLED screen :-
	Step 1:- Convert the image to complete black and white format.
	Step 2:- Convert the image to resolution of 128*64. 
	Step 3:- Convert the image into BMP (.bmp) format.
	Step 4:- Download LCD Assistant from :-
		https://github.com/ayush-jmi/Smart_Hut/blob/master/LCDAssistant.exe
		Load the image on LCD Assistant and save its output code as Text file (.txt).
Step 5:- Open the code, copy the function and paste it in the Arduino code. After that call that function from main loop by:-
 LED_PrintBMP(0,0,128,7,(unsigned char *)FUNCTION_NAME);
Upload the code. You can observe your image on the screen.

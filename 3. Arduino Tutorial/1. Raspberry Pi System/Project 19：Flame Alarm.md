**Project 19：Flame Alarm**

1.  **Introduction**

Fire is a terrible disaster and fire alarm systems are very useful in
houses、commercial buildings and factories. In this project, we will use
ESP32 to control a flame sensor, a buzzer and a LED to simulate fire
alarm devices. This is a meaningful maker activity.

2.  **Component：**

<table>
<tbody>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/df7fdb857f6490486514896b60cabe10.jpeg" style="width:1.39722in;height:0.68264in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/e380dd26e4825be9a768973802a55fe6.png" style="width:0.55208in;height:1.35417in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/ef77f5a64c382157fc2dea21ec373fef.png" style="width:0.29514in;height:1.25903in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/4b4f653a76a82a3b413855493cc58fba.png" style="width:0.86111in;height:0.70069in" /></td>
</tr>
<tr class="even">
<td>ESP32*1</td>
<td>Breadboard*1</td>
<td>Red LED*1</td>
<td>Active Buzzer*1</td>
</tr>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/a50ec3e38adf10643eafac8cb62bec8a.png" style="width:0.20278in;height:1.25764in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/845d05a6108b1662b828610ba9dcb788.png" style="width:0.25833in;height:1.13681in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/b395b1cd2678f87b3a34dec15659efbc.png" style="width:0.22431in;height:1.00556in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/e9a8d050105397bb183512fb4ffdd2f6.png" style="width:0.77222in;height:0.77986in" /></td>
</tr>
<tr class="even">
<td>Flame Sensor*1</td>
<td>220Ω Resistor*1</td>
<td><p>10KΩ</p>
<p>Resistor*1</p></td>
<td>Jumper Wires</td>
</tr>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/9197d4aff9356c585b7ef68e33a6881d.png" style="width:0.27986in;height:1.08819in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/098a2730d0b0a2a4b2079e0fc87fd38b.png" style="width:0.90833in;height:0.23681in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/7dcbd02995be3c142b2f97df7f7c03ce.png" style="width:1.05903in;height:0.56667in" /></td>
<td></td>
</tr>
<tr class="even">
<td>NPN Transistor(S8050)*1</td>
<td>1kΩ Resistor*1</td>
<td>USB Cable*1</td>
<td></td>
</tr>
</tbody>
</table>

3.  **Component Knowledge**

![](/media/a50ec3e38adf10643eafac8cb62bec8a.png)

The flame emits a certain amount IR light that is invisible to the human
eye, but our flame sensor can detect it and alert a microcontroller
(such as ESP32) that a fire has been detected. It has a specially
designed infrared receiver tube to detect the flame and then convert the
flame brightness into a fluctuating level signal. 

The short pin of the receiving triode is negative pole and the other
long pin is positive pole. We should connect the short pin (negative) to
5V and the long pin (positive) to the analog pin, a resistor and GND. As
shown in the figure below：

![](/media/87bd204db523c602c80745266c1ee452.png)

**Note:** Since vulnerable to radio frequency radiation and temperature
changes, the flame sensor should be kept away from heat sources like
radiators, heaters and air conditioners, as well as direct irradiation
of sunlight, headlights and incandescent light.

4.  **Read the values of the flame sensor**

We first use a simple code to read the ADC value, DAC value and voltage
value of the flame sensor and print them out. Please refer to the wiring
diagram below：

![](/media/76ce57355da1df27e049bdc6e19f0650.png)

<table>
<tbody>
<tr class="odd">
<td><p>//**********************************************************************************</p>
<p>/*</p>
<p>* Filename : Read Analog Value Of Flame Sensor</p>
<p>* Description : Basic usage of ADC，DAC and Voltage</p>
<p>* Auther : http//www.keyestudio.com</p>
<p>*/</p>
<p>#define PIN_ANALOG_IN 36 //the pin of the Flame sensor</p>
<p>void setup() </p>
<p>//In loop()，the analogRead() function is used to obtain the ADC value,</p>
<p>//and then the map() function is used to convert the value into an 8-bit precision DAC value.</p>
<p>//The input and output voltage are calculated according to the previous formula,</p>
<p>//and the information is finally printed out.</p>
<p>void loop() </p>
<p>//**********************************************************************************</p></td>
</tr>
</tbody>
</table>

Compile and upload the code to ESP32, after the code is uploaded
successfully, power up with a USB cable, open the serial monitor and set
the baud rate to 115200 and press the reset button first.

You will see that the serial monitor window will print out the ADC
value, DAC value and voltage value of the flame sensor. When the sensor
is closed to fire, the ADC value,DAC value and voltage value will get
greater. Conversely, the ADC value,DAC value and voltage value decrease.

![](/media/64afecf1bfe9f634e352955c906a9632.png)

5.  **Wiring diagram of the flame alarm**

Next, we will use a flame sensor, a buzzer, and a LED to make an
interesting project, that is flame alarm. When flame is detected, the
LED flashes and the buzzer alarms.

![](/media/e9fa0e50df23c1f2e58fdd319ad21b4c.png)

6.  **Test Code**（Note: ![](/media/1600623570befb10056c39ab4cc16806.png)the threshold of 500 in
    the code can be reset as required）

<table>
<tbody>
<tr class="odd">
<td><p>//**********************************************************************************</p>
<p>/*</p>
<p>* Filename : Flame Alarm</p>
<p>* Description : Controlling the buzzer and LED by flame sensor.</p>
<p>* Auther : http//www.keyestudio.com</p>
<p>*/</p>
<p>#define PIN_ADC0 36 //the pin of the flame sensor</p>
<p>#define PIN_LED 15 // the pin of the LED</p>
<p>#define PIN_BUZZER 4 // the pin of the buzzer</p>
<p>void setup() </p>
<p>void loop() </p>
<p>else</p>
<p></p>
<p>}</p>
<p>//**********************************************************************************</p></td>
</tr>
</tbody>
</table>

7.  **Test Result**

Compile and upload the code to ESP32, after the code is uploaded
successfully, power up with a USB cable and you will see that when the
flame sensor detects the flame, the LED will flash and the buzzer will
alarm, otherwise, the LED does not light up and the buzzer does not
sound.

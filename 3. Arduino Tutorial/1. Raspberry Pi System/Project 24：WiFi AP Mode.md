**Project 24：WiFi AP Mode**

1.  **Introduction**

In this project, we are going to learn the WiFi AP mode of the ESP32.

2.  **Components**

<table>
<tbody>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/729232b0c2d2c01984808289b222890c.png" style="width:1.8125in;height:0.86458in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/53f17b0de2d98d4714e8fe9043a346ca.jpeg" style="width:2.43681in;height:1.13472in" /></td>
</tr>
<tr class="even">
<td>USB Cable*1</td>
<td>ESP32*1</td>
</tr>
</tbody>
</table>

**3. Wiring Diagram**

Plug the ESP32 mainboard to the USB port of the Raspberry Pi

![](/media/53f17b0de2d98d4714e8fe9043a346ca.jpeg)

**4. Component Knowledge**

**AP Mode:**

When setting AP mode, a hotspot network will be created, waiting for
other WiFi devices to connect. As shown below;

![](/media/35d90f1ce10814ea1897ba63f8bd7ad9.png)

5.  **Test Code**

![](/media/02a41b24675ad837330d959a03ab9f9e.png)

Before running the code , you can make any changes to the ESP32 AP name
and password in the box as shown below, but in a default circumstance,
it doesn’t need to modify.

![](/media/9ad8a0e92c650dce6548b21aea71b803.png)

<table>
<tbody>
<tr class="odd">
<td><p>//**********************************************************************************</p>
<p>/*</p>
<p>* Filename : WiFi AP</p>
<p>* Description : Set ESP32 to open an access point</p>
<p>* Auther : http//www.keyestudio.com</p>
<p>*/</p>
<p>#include &lt;WiFi.h&gt; //Include the WiFi Library header file of ESP32.</p>
<p>const char *ssid_AP = "ESP32_WiFi"; //Enter the router name</p>
<p>const char *password_AP = "12345678"; //Enter the router password</p>
<p>IPAddress local_IP(192,168,1,108);//Set the IP address of ESP32 itself</p>
<p>IPAddress gateway(192,168,1,1); //Set the gateway of ESP32 itself</p>
<p>IPAddress subnet(255,255,255,0); //Set the subnet mask for ESP32 itself</p>
<p>void setup()else</p>
<p>Serial.println("Setup End");</p>
<p>}</p>
<p>void loop() </p>
<p>//**********************************************************************************</p></td>
</tr>
</tbody>
</table>

**6. Test Result**

Enter the ESP32 AP name and password correctly, compile and upload the
code to ESP32, open the serial monitor and set the baud rate to **115200
and press the reset button first**, then monitor will display as
follows:

(If open the serial monitor and set the baud rate to 115200, the
information is not displayed, please press the RESET button of the
ESP32)

![](/media/1fd21fafd84d2b529931a89d21a03d6a.png)

![](/media/38d88043831a89fb66bdf71ae167e977.png)

When observing the printed information of the serial monitor, turn on
the WiFi scanning function of the mobile phone, you can see the ssid\_AP
on ESP32, which is dubbed "ESP32\_Wifi" in this code. You can connect to
it either by typing the password "12345678" or by modifying the code to
change its AP name and password.  

![](/media/3e0ad895bea7f5100cc02a415adcace7.png)

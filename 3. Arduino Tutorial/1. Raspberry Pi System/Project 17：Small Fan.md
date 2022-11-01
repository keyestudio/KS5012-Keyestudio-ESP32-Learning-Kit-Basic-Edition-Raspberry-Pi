**Project 17：Small Fan**

1.  **Introduction**

In hot summer, we need electric fans to cool us down, so in this
project, we will use a ESP32 to control a DC motor and small fan blades
to make a **small electric fan.**

**2. Components**

<table>
<tbody>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/2baa8832e763a08fb4623b405d6481ba.jpeg" style="width:1.39514in;height:0.68056in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/5eba8bae9e1d18b959ca425a9cc83fd2.jpeg" style="width:1.07569in;height:0.43472in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/4e0b78edf6e4aeefa4c5191c606b2031.png" style="width:0.42847in;height:1.04931in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/655e6c465cb423279e0908513a983711.png" style="width:0.85694in;height:0.75347in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/9197d4aff9356c585b7ef68e33a6881d.png" style="width:0.27986in;height:1.08819in" /></td>
</tr>
<tr class="even">
<td>ESP32*1</td>
<td>DC Motor*1</td>
<td>Breadboard*1</td>
<td>Fan*1</td>
<td>NPN Transistor (S8050)*1</td>
</tr>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/9197d4aff9356c585b7ef68e33a6881d.png" style="width:0.27986in;height:1.08819in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/098a2730d0b0a2a4b2079e0fc87fd38b.png" style="width:0.90833in;height:0.23681in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/df3db6765ee8c86beafa8410e87dd50d.png" style="width:0.77361in;height:0.76944in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/6138a67aa472890c8e0e74bf96fabd01.png" style="width:1.03611in;height:0.24236in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/7dcbd02995be3c142b2f97df7f7c03ce.png" style="width:1.05903in;height:0.56667in" /></td>
</tr>
<tr class="even">
<td>PNP Transistor (S8550)*1</td>
<td>1KΩ Resistor*1</td>
<td>Jumper Wire</td>
<td>Diode*1</td>
<td>USB Cable*1</td>
</tr>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/6d0d02f79c5511a1225e0940220482e8.jpeg" style="width:1.36667in;height:0.98681in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/412d874475de346d56b39cfb041ffc4c.png" style="width:1.19028in;height:0.51389in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS5012-Keyestudio-ESP32-Learning-Kit-Basic-Edition-Raspberry-Pi/master/media/a815c48437199c6ab79d74cd2d583de0.png" style="width:0.24583in;height:1.13264in" /></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>6 AA Battery Holder*1</td>
<td>Keyestudio Breadboard Power Module*1</td>
<td>AA Battery(Self-prepared)*6</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

2.  **Component Knowledge:**

**Keyestudio Breadboard Power Supply Module：**

![](/media/7ff03f4506988f1ce99c5757892fc6de.jpeg)

**Introduction:**

This breadboard power supply module is compatible with 5V and 3.3V,
which can be applied to MB102 breadboard. The module contains two
channels of independent control, powered by the USB all the way.

The output voltage is constant for the DC5V, and another way is powered
by DC6.5-12V, output controlled by the slide switch, respectively for
DC5V and DC3.3V.

If the other power supply is DC 6.5-12v, when the slide switch is
switched to +5V, the output voltages of the left and right lines of the
module are DC 5V. When the slide switch is switched to +3V, the output
voltage of the USB power supply terminal of the module is DC5V , and the
output voltage of the DC 6.5-12V power supply terminal of the other
power supply is DC3.3V.

**Specification:**

  - Applied to MB102 breadboard;

  - Input voltage：DC 6.5-12V or powered by USB;

  - Output voltage：3.3V or 5V

  - Max output current:\<700ma

  - Up and down two channels of independent control, one of which can be
    switched to 3.3V or 5V;

Comes with two sets of DC output pins, easy for external use.

3.  **Wiring Diagram 1：**

We use the S8050（NPN transistor) to control the motor

![](/media/715ae32c3fac7c6537f380fb91e5e83c.png)

Wire up first, then connect a fan at the DC motor

5.  **Test Code 1：**

<table>
<tbody>
<tr class="odd">
<td><p>//**********************************************************************</p>
<p>/*</p>
<p>* Filename : Small_Fan</p>
<p>* Description : S8050 triode drives the motor working</p>
<p>* Auther : http//www.keyestudio.com</p>
<p>*/</p>
<p>void setup() </p>
<p>void loop() </p>
<p>//**********************************************************************************</p></td>
</tr>
</tbody>
</table>

**6. Test Result 1：**

Upload the code to the ESP32 and power up. You will view the motor
rotate for 4s, stop for 2s, in a loop way

**7.Wiring Diagram 2：**

We use the S8050（PNP transistor) to control the motor

![](/media/04293fbe70eeec27c2d8127f42afbaf2.png)

Wire up first, then connect a fan at the DC motor

8.  **Test Code 2：**

<table>
<tbody>
<tr class="odd">
<td><p>//**********************************************************************</p>
<p>/*</p>
<p>* Filename : Small_Fan</p>
<p>* Description : S8550 triode drives the motor working</p>
<p>* Auther : http//www.keyestudio.com</p>
<p>*/</p>
<p>void setup() </p>
<p>void loop() </p>
<p>//**********************************************************************************</p></td>
</tr>
</tbody>
</table>

9.  Test Result 2：

Upload the code to the ESP32 and power up. You will view the motor
rotate for 4s, stop for 2s, in a loop way

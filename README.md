​																												TS360 V99-Slim Vector Module

## Touchsens  

* 1.0 Features  

  * 1.1. Multi direction and force detection.  

  * 1.2. PS2, I2C,SPI Digital Delta-X and Delta-Y Data output..  


  * 1.3. High Anti-Noise capability.  


  * 1.4. Thin and light weight. 


  * 1.5. Low power consumption.  


  * 1.6. High durability.  


  * 1.7. High stability.

  * 1.8. Built-In center dome button. 

  * 1.9 Suitable for Mouse, Joystick and Hand-held devices.

    

* 2.0 Introduction 

  * TS360 V99-Slim is a thin and small shaped multi-functional vector module that can measure the  force and direction applied on the surface of Key Top, Easy use center dome switch, Drag and Drop  of Mouse cursor could be easily fulfilled by single finger, Besides of the Mouse and Joystick function,  TS360 V99-Slim also support the Wheel、Key In and Tapping function, Excellent for the Notebook、 Presentation Pointer、Remote Controller、GPS、 Multimedia player、Keyboard、Mouse etc. 

    

* 3.0 Product Specifications 

  * Operation Voltage : 2.8V - 5.5V.

    

  * Power Consumption: 

    * Operation: 1.8 mA (Typical) @1MIPS VDD=3.3 V.  

    * Sleep : 10μA (Max) @ VDD=3.3V.

      

  * Resolution Angle : 

    * 11.25 Degree 

      

  * Force Input : 

    * Max 5N ( 510gf )  The force are to be applied at 0.0 mm to 0.5 mm from the top of the sensor surface. The base  of the assembly must be firmly mounted in the test fixture. The load shall be applied  perpendicular to the post. The force shall start at 0 grams, ramp to the force maximum, and  return to 0 grams over a time of 4 seconds. There shall be no physical damage to the device as  a result of this test. 

      

  * Life cycle : 

    * 10M cycles for sensor under 4N (408gf) 
    * 1M cycles for Dome switch under 1N (102gf)

    The force are to be applied at 0.3 mm to 0.5 mm from the sensor surface of the Vector  Module. The base of the assembly must be firmly mounted in the test fixture. The load shall  be between 250 grams and 408 grams. The load shall be applied perpendicular to the Keytop  surface. The radial angle of the load shall be continuously by the up and down arm used to  apply the force. Each up and down cycle shall be completed in 1 second for a frequency of approximately 60 times per minute. 

    

  * Output vs. Force : 20 ~ 500 gf 

    * The output will be active of the applied force over a range of 20 to 600gram force. 

  * VIL Input Low Voltage : 0 V ~ 0.3VDD

  * VIH Input High Voltage : 0.7VDD – VDD

    

* 4.0 Outlook

  ![image](https://github.com/ouser555/ergodashv99/blob/main/004.jpeg)
  ![image](https://github.com/ouser555/ergodashv99/blob/main/003.jpeg)
  
  ![image](https://github.com/ouser555/TS360-V99-Trackpoint-module/blob/main/pic/001.png)
  
* 5.0 Block Diagram

  ![image](https://github.com/ouser555/TS360-V99-Trackpoint-module/blob/main/pic/002.png)
  ![image](https://github.com/ouser555/TS360-V99-Trackpoint-module/blob/main/pic/003.png)
  ![image](https://github.com/ouser555/TS360-V99-Trackpoint-module/blob/main/pic/004.png)
  

* 6.0 Pin Assignments of I2C & SPI

  * Pin 1 : CLK/MOSI

  * Pin 2 : VCC 

  * Pin 3 : SDA/MISO

  * Pin 4 : GND  

  * Pin 5 : Mouse Right Button/NCS 

  * Pin 6 : Mouse Left Button/SCLK

  * Pin 7 : Scan/Motion

  * R1 Jumper short!

    

* 7.0 DATA Transmission Specification - PS/2, I2C, SPI :

  **7.1 SPI DATA Transmitter Specifications:**

  * Register

    * 0x00  (R) = Product ID = 0x11

    * 0x02  (R) = Motion 

      * B7 = MOT =1, if motion is detected after last read 
      * B6 = MIDDLE SW = 1 if the middle switch is pressed

    * 0x03  (R) = Delta X

    * 0x04  (R) = Delta Y

    * 0x0D (R/W) = CTRL

      * B0 = RES =1 set the device to double resolution
      * B1 = PD =1 set the device to power down  (auto)
      * B3 = JOYSTICK = 1 set the device to Joystick mode 
      * B4 = SCROLL = 1 set the device to Scroll mode 
      * B6 = MIDDLE SW = 1 if the middle switch is pressed

    * 0x3A (W) = Reset

      * accept 0x5a to reset the device

    * 0x3F (R) = Inverse rev. ID 0xff

      

  * SPI BitMap

    (MSB R/W B7) B6 B5 B4 B3 B2 B1 (B0 LSB) ACK

    ​	Read = 0 Write =1 

    

  * SPI trans Ex.

    * SCLK <= 50kHz (Max speed)

    * Write: out(0x80 | reg addr) => out(data)

      write ctrl reg  : out(0x80) | 0x0D) => out(0x02)  // set auto power down mode

      

    * Read: out(0x7F & reg addr) => in(data)

       read delta x : out(0x7F) & 0x03) => in(delta x data)  // read delta x

  

  * 7.1.2 Transmitter pin definitions & Name Description:
    * 1: MOSI - Serial Data Input (Master Out/Slave In) 
    * 2: VDD - Supply Voltage
    * 3: MISO - Serial Data Output (Master In/Slave Out)  
    * 4: GND - Ground
    * 5: NCS - Chip Select (active low input)  
    * 6: SCLK - Serial Clock Input 
    * 7: Motion – Active low while Data output

  

* 8 DC Characteristics

  | Symbol | Description                     | Min    | Typical | Max    | Unit | Conditions(Ta=25°C) |
  | ------ | ------------------------------- | ------ | ------- | ------ | ---- | ------------------- |
  | VDD    | Operating Voltage               | 2.8    | 5.0     | 5.5    | V    |                     |
  | IOP    | Operating Current               |        | 1.82    |        | mA   | fsys=1MIPS@3.3V     |
  | IPD    | Power Down Current              |        | 10      |        | uA   | VDD=3.3V            |
  | VIL    | Input low voltage for IO lines  | 0      |         | 0.3VDD | V    |                     |
  | VIH    | Input high voltage for IO lines | 0.7VDD |         | VDD    | V    |                     |
  | LOL    | IO lines sink current           |        | 15      |        | mA   | VDD=5.0V，VOL=0.5V  |
  | LOH    | IO line drive current           |        | -15     |        |      | VDD=5.0V,VOH=4.5V   |
  | RPH    | Pull-high Resistance            |        | 80      |        | kΩ   | VDD=5.0V            |

  

* 9 Mechanical Dimension

  

* 10 Environmental Specification

  * 10.1 Environmental Compliance 

    * This Touchsens product is built in compliance with the RoHS Directive.

    * RoHS is the default compliance level. 

      

  * 10.2 Environmental Conditions 

    * Operation Temp: -20 ~ 85 ℃

    * Storage Temp : -40 ～ 105 ℃

    * Operating Humidity : 5% ~ 95% (Non-condensing)

    * Thermal Ramp Rate 5° C / min

    * Storage Temperature and Humidity 60° C @ 95 %

    * Flame Resistance : UL94V-2(UL Standard)

    * Heat Shock : 20 cycles  One temperature cycle shall be defined as –40°C held for 1 hour, followed by a ramp to 80°C at 3~5°C/min. 
      
      This is held for 1 hour followed by a ramp back down to –40°C at 3~5°C/min.

    * Power Supply Ripple Resistance : 100 mV p-p  Ripple Resistance by injecting a sine wave at the test voltages into the power input pin of the Vector www.touchsens.com Touchsens Corp. 11 Sales@touchsens.com Module. The injected frequencies increments from 1/10/100/1K/1M Hz. The Vector Module is tested at  each frequency with and without the noise injection.

    * Performance migration : 500 hours The performance of the Vector Module shall adhere to all other specifications after continual use for the above  specified period of time under the following conditions: VDD 5.0V; 25°C; 50% RH. 

      

  * 10.3 ESD Protection

    * ESD Resistance: ±8kV (Air Discharge in accordance with IEC standard 1000-4-2)

      Note: ESD is applied to the front surface of the Vector module when properly mounted.

      

* 11 Packing I. 50 pcs per Tube II. 1K / 5K/ 10K pcs 3 kinds of Carton

  * I. 50 pcs per Tube 

  * II. 1K / 5K/ 10K pcs 3 kinds of Carton

    

* 12 Ordering Information 

  * Part Number    :   V99-Slim-X-2
  * X                         :   P - PS/2 Interface, Slave 
  * X                         :   I - I2C Interface, Slave 
  * X                         :   S - SPI Interface, Slave

  

  

  

  

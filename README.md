# ECE 528/L - Robotics and Embedded Systems with Lab
**CSU Northridge**

**Department of Electrical and Computer Engineering**

## Reflectance Sensor Lab
The Reflectance Sensor lab interfaces with the following:

* User LEDs of the TI MSP432 LaunchPad
* 8-Channel QTRX Sensor Array - [Product Link](https://www.pololu.com/product/3672)

# Pre-Lab Assignment

1. What does a reflectance sensor consist of? How many reflectance sensors are on the QTRX Reflectance Sensor Array? What is its operating voltage? Refer to Pololu's documentation page of the QRTX Reflectance Sensor Array.

A reflectance sensor consists of IR LED/phototransistor pairs that identify changes in reflectance underneath the robot. There are eight sensors on the QTRX Reflectance Sensor Array. It has an operating voltage of 2.9 V to 5.5 V

2. Which control pins on the QTRX Reflectance Sensor Array are responsible for enabling the reflectance sensors? What is their default value after powering on the sensor array? List the pin names and the pin numbers used to connect the two control pins. Refer to Pololu's documentation page of the QTRX Reflectance Sensor Array.

CTRL ODD and CTRL EVEN are responsible for enabling the reflectance sensors. The default value on the sensr array is HIGH because they are turned on by default.
- CTRL EVEN - by default it is tied to CTRL ODD through an internal 1k resistor, but can be driven by external connections independently
- CTRL ODD - by default it is tied to CTRL EVEN through an internal 1k resistor, but can be driven by external connections independently

3. Write a void function named P5_0_and_P9_7_Init that takes no arguments and configures the P5.0 and P9.7 pins as output GPIO pins. Initialize the value of the P5.0 and P9.7 pins to zero.

void P5_0_and_P9_7_Init(void)

{

  P5->SEL0 &= ~0x01;
  
  P5->SEL1 &= ~0x01;

  P5->DIR |= 0x01;

  P5->OUT &= ~0x01;

  P9->SEL0 &= ~0x80;
  
  P9->SEL1 &= ~0x80;

  P9->DIR |= 0x80;
  
  P9->OUT &= ~0x80;
  
}
  

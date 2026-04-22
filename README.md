**Smart Light Control System (STM32 Nucleo-64 + OLED)**

**Project Description**
This project demonstrates a smart lighting control system built using the STM32 Nucleo-64 Experimental Kit (STEM Smart Labs).
The system uses an LDR sensor to detect ambient light and automatically controls an LED. A manual override switch allows the user to disable automatic behavior.
An SSD1306 OLED display provides real-time visualization of sensor data, system mode, and output status.
**Objectives**
•  Interface ADC to read analog sensor (LDR) 
•  Implement automatic decision-making based on light intensity 
•  Provide manual override using GPIO input 
•  Display real-time system data on OLED using I2C

**Hardware Used**
•  STM32 Nucleo-64 Development Board 
•  STEM Smart Labs Experimental Kit 
•  LDR (Light Dependent Resistor) 
•  SSD1306 OLED Display (I2C) 
•  Switch 
•  LED

**Pin Configuration**
Peripheral	STM32 Pin	Description
LDR	PA0 (ADC1_IN0)	Analog input
Switch	PB0	Digital input (Pull-up)
LED	PB3	Digital output
OLED SDA	I2C1 SDA	I2C Data
OLED SCL	I2C1 SCL	I2C Clock

**System Functionality**
1. ADC-Based Light 
  •	The LDR outputs an analog voltage proportional to light intensity. 
  •	STM32 ADC (12-bit) converts it into a value between 0–4095.
2. Operating Modes
    Manual Mode
      •	Triggered when switch is pressed (LOW) 
      •	LED is forced OFF, regardless of light intensity
    Automatic Mode
      •	Triggered when switch is released (HIGH) 
      •	System decides based on light level:
        Condition	Mode	LED
        LDR < Threshold	Night	ON
        LDR ≥ Threshold	Day	OFF

3. OLED Display Output
  The OLED shows:
    •	LDR value 
    •	Graphical bar indicator 
    •	Current mode (Manual / Day / Night) 
    •	LED status
**Software Details**
  •	Language: C 
  •	IDE: STM32CubeIDE 
  •	Libraries Used: 
  o	HAL Drivers 
  o	SSD1306 OLED Library 
  o	Font Library
    How to Run
      o	Open the project in STM32CubeIDE 
      o	Connect hardware as per pin configuration 
      o	Build and flash the code to the STM32 board 
      o	Power the system 
      o	Observe OLED output and LED behavior

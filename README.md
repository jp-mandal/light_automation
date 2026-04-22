Smart Light Control System (STM32 Nucleo-64 + OLED)

📌 Project Description

This project demonstrates a smart lighting control system built using the STM32 Nucleo-64 Experimental Kit (STEM Smart Labs). The system uses a Light Dependent Resistor (LDR) to sense ambient light intensity and automatically control an LED based on environmental conditions. In addition to automatic operation, a manual override switch is provided to disable the automatic behavior and force the light off when required. An SSD1306 OLED display is interfaced via I2C to provide real-time visualization of the LDR readings, system operating mode, and LED status.

🎯 Objectives

The main objectives of this project are to interface the ADC of the STM32 microcontroller to read analog sensor data from the LDR, implement automatic decision-making logic based on light intensity, provide a manual override mechanism using a GPIO input switch, and display real-time system information on an OLED display using I2C communication.

🧰 Hardware Used

The hardware components used in this project include the STM32 Nucleo-64 Development Board, the STEM Smart Labs Experimental Kit, an LDR (Light Dependent Resistor), an SSD1306 OLED Display (I2C), a switch, and an LED.

🔌 Pin Configuration

The LDR is connected to PA0 configured as ADC1_IN0 for analog input. The switch is connected to PB0 and configured as a digital input with an internal pull-up resistor. The LED is connected to PB3 and configured as a digital output. The OLED display uses the I2C interface, with SDA connected to the I2C1 SDA pin and SCL connected to the I2C1 SCL pin.

⚙️ System Functionality

The system operates by continuously reading the analog output from the LDR, which produces a voltage proportional to the ambient light intensity. This analog signal is converted by the STM32’s 12-bit ADC into a digital value ranging from 0 to 4095. Based on the switch input, the system operates in either manual or automatic mode. In manual mode, which is triggered when the switch is pressed (logic LOW), the LED remains turned off regardless of the light intensity. In automatic mode, triggered when the switch is released (logic HIGH), the system compares the LDR value with a predefined threshold. If the LDR value is below the threshold, the environment is considered dark (night mode), and the LED is turned on. If the LDR value is equal to or above the threshold, the environment is considered bright (day mode), and the LED is turned off.

🖥️ OLED Display Output

The OLED display provides continuous feedback by showing the current LDR value, a graphical bar representation of light intensity, the active system mode (Manual, Day, or Night), and the LED status (ON or OFF). This makes the system interactive and easy to monitor in real time.

💻 Software Details

The project is implemented in the C programming language using STM32CubeIDE. It utilizes STM32 HAL drivers for peripheral control, along with an SSD1306 OLED library and a font library for display functionality.

🚀 How to Run

To run the project, open the project files in STM32CubeIDE, connect the hardware components according to the specified pin configuration, build and flash the code to the STM32 Nucleo-64 board, and power the system. Once running, the OLED display will show real-time data, and the LED will respond automatically based on ambient light conditions or manual switch input.

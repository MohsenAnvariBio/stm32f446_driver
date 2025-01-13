# Real-Time Clock (RTC) with DS1307 and LCD Display on STM32F446RE

This project demonstrates the use of the **STM32F446RE** microcontroller to interface with the **DS1307 Tiny RTC module** over **I2C**, and display real-time data on a **16x2 LCD**. It showcases your expertise in developing custom drivers for **I2C**, **SPI**, **GPIO**, and **USART** on the STM32F446RE. The project highlights how to handle real-time clock functionality using the DS1307 RTC and manage periodic updates via the **SysTick timer**.

### Key Areas of Expertise:
- **I2C Driver**: Custom driver for communicating with the DS1307 RTC module.
- **SPI Driver**: Demonstrated in other projects for communication with SPI peripherals (e.g., sensors or displays).
- **GPIO Driver**: Manages GPIO pins for controlling the 16x2 LCD and other peripherals.
- **USART Driver**: Used for serial communication in related projects, not directly applied in this example but included in the broader STM32F446RE development.

This project serves as a practical example of how to use these drivers in a real-world embedded system application.

## Project Overview

### Key Features:
- **I2C Driver**: Enables communication with the DS1307 RTC module to read and write time and date.
- **LCD Driver**: Handles output to a 16x2 LCD, displaying real-time time and date.
- **SysTick Timer**: Used to generate periodic updates for the LCD display.
- **Custom RTC Driver**: Full control over setting and reading RTC values from the DS1307.
- **GPIO Control**: Manages communication with the LCD and other peripherals via GPIO pins.

## Hardware Setup

- **STM32F446RE NUCLEO Board**
- **DS1307 RTC Module** connected via **I2C**
- **16x2 LCD Display** connected via **GPIO**
- **Breadboard** for assembling components

## Software Overview

### Libraries Used:

- **I2C Driver**: A custom I2C driver facilitates communication with the DS1307 RTC module.
- **LCD Driver**: A custom driver for controlling the 16x2 LCD and displaying data.
- **SysTick Timer**: Utilized for periodic updates to the time and date display.

### Key Functions:
- **RTC Initialization**: The DS1307 RTC is initialized using a custom I2C driver. Time and date values are both set and retrieved from the RTC module.
- **Displaying Time and Date**: The LCD driver displays the current time and date on a 16x2 LCD. Time is shown in both 12-hour (AM/PM) and 24-hour formats.
- **SysTick Interrupt**: Periodically updates the LCD with the current time and date from the DS1307.

---

## Code Structure

The main application is divided into several key parts:

### Main Program

The main function initializes the **RTC** and **LCD**, sets the date and time for the DS1307, and updates the display periodically. The following sequence occurs:

1. **Initialize DS1307 RTC**: The DS1307 RTC is initialized, and the current time and date are set.
2. **Display Information on LCD**: The time and date are displayed on the 16x2 LCD using the custom LCD driver.
3. **Periodic Updates**: Using the **SysTick Timer**, the display is updated every second.

### Helper Functions

- **GetDayOfWeek()**: Converts the day of the week integer (1-7) into a string.
- **TimeToString()**: Converts the RTC time structure into a readable time format (hh:mm:ss).
- **DateToString()**: Converts the RTC date structure into a readable date format (dd/mm/yy).
- **InitSystickTimer()**: Configures the SysTick timer to generate periodic interrupts.
- **SysTick_Handler()**: Updates the LCD with the current time and date on each SysTick interrupt.

---

## Setup Instructions

### Connections:
1. **DS1307 RTC Module**: 
   - **SDA** → **PB7** (STM32 I2C Data)
   - **SCL** → **PB6** (STM32 I2C Clock)
   - **VCC** → **3.3V**
   - **GND** → **Ground**

2. **16x2 LCD**: 
   - **RS** → **PA1**
   - **RW** → **Ground**
   - **EN** → **PA2**
   - **D4-D7** → **PA3-PA6**
   - **VCC** → **5V**
   - **GND** → **Ground**

### Software Requirements:
- STM32CubeIDE for compiling and flashing the firmware to the STM32F446RE.
- A custom driver for I2C, DS1307, and LCD communication.

### Build and Run:
1. Open STM32CubeIDE and import the project.
2. Compile the project and flash it to the STM32F446RE board.
3. Connect the hardware as described above.
4. Observe the time and date being displayed on the 16x2 LCD.

---

## Conclusion

This project is a practical example of implementing **I2C**, **SPI**, **GPIO**, and **USART** drivers on the **STM32F446RE** microcontroller. It demonstrates your ability to write custom embedded drivers for peripherals and handle communication protocols like **I2C** for the **DS1307 RTC**, **GPIO** for the LCD, and periodic updates using the **SysTick timer**. This showcases your embedded system development skills and understanding of STM32 hardware.

## Notes
- Ensure that the clock source for the **SysTick timer** is correctly configured.
- Adjust the I2C communication speed and addresses if necessary for compatibility with your specific hardware.

![photo_2025-01-13_18-40-36](https://github.com/user-attachments/assets/a8b2877f-afcc-437f-9e38-cc0af4bb718e)

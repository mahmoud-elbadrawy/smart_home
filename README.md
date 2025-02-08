# Smart Home Control System

## Overview
The Smart Home Control System is an embedded system designed to automate and monitor various home appliances and environmental conditions. It integrates multiple sensors and actuators to control lighting, temperature, and security, providing a seamless user experience. The system includes a password-based access control mechanism to ensure security.

## Features
- **Password-Based Access Control**: Users must enter a correct password to access the system.
- **Temperature Monitoring**: Uses an LM35 sensor to measure ambient temperature and control a DC motor (simulating an air conditioner).
- **Light Intensity Monitoring**: Uses an LDR sensor to measure light levels and control LEDs.
- **Servo Motor Control**: Simulates a door mechanism that opens and closes upon successful password entry.
- **Buzzer Alert**: Activates a buzzer in case of system halt due to multiple incorrect password attempts.

## Hardware Components
- **Microcontroller**: (Not specified, typically an AVR or ARM-based microcontroller)
- **Keypad**: For password entry.
- **LCD Display**: For displaying system status, temperature, and light intensity.
- **DC Motor**: Simulates an air conditioner.
- **LM35 Temperature Sensor**: Measures ambient temperature.
- **LDR (Light Dependent Resistor)**: Measures light intensity.
- **Buzzer**: For alerting the user in case of system halt.
- **Servo Motor**: Simulates a door mechanism.
- **LEDs**: For indicating light intensity status.

## System Architecture

### Initialization
- The system initializes all peripherals (LCD, keypad, motors, sensors, etc.) on startup.

### Password Entry
- The user is prompted to enter a password using the keypad. The default password is `1234`.
  - If the password is correct, the system grants access and proceeds to monitor temperature and light intensity.
  - If the password is incorrect, the user is prompted to try again. After 3 incorrect attempts, the system halts and activates the buzzer.

### Temperature Monitoring
- The system continuously reads the temperature and displays it on the LCD.
  - If the temperature exceeds 28°C, the DC motor (air conditioner) is turned on.
  - If the temperature drops below 21°C, the motor is turned off.

### Light Intensity Monitoring
- The system continuously reads the light intensity and displays it on the LCD.
  - If the light intensity falls below 50%, the LED is turned on.
  - If the light intensity rises above 50%, the LED is turned off.

### Servo Motor Control
- Upon successful password entry, the servo motor simulates opening and closing a door.

### System Halt
- If the system halts due to multiple incorrect password attempts, the buzzer is activated, and the system enters an infinite loop.

## Software Implementation
- **Programming Language**: C

### Microcontroller Peripherals Used
- **DIO (Digital Input/Output)**: For controlling pins.
- **ADC (Analog-to-Digital Converter)**: For reading analog sensor values.
- **Timer1**: For PWM control of the servo motor.
- **CLCD (Character LCD)**: For displaying information.
- **KPD (Keypad)**: For reading user input.
- **DC Motor**: For controlling the DC motor.
- **LM35**: For reading temperature values.
- **LDR**: For reading light intensity values.
- **Servo Motor**: For controlling the servo motor.
- **LED**: For controlling the LED.

## Installation & Usage
1. Flash the firmware to the microcontroller.
2. Connect the hardware as per the system diagram.
3. Power on the system:
   - The LCD prompts for a password.
   - Upon successful password entry, the system monitors temperature and light intensity, controlling the DC motor and LEDs accordingly.
   - The servo motor simulates a door mechanism upon access.

## Future Enhancements
- **Password Change Feature**: Allow the user to change the system password.
- **Remote Monitoring**: Integrate Wi-Fi or Bluetooth for remote monitoring and control.
- **Data Logging**: Log temperature and light intensity data for later analysis.
- **IoT Integration**: Add IoT connectivity for real-time updates and control via a mobile app.

## Author

**Mahmoud Elbadrawy**
- Linkedin: www.linkedin.com/in/mahmoud-elbadrawy
- GitHub: mahmoud-elbadrawy

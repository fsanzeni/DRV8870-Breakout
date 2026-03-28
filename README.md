# DRV8870 Breakout Board

A simple breakout board for the Texas Instruments DRV8870 brushed DC motor driver (up to 3.6A peak current).

## Features

- **Motor Driver:** TI DRV8870DDA H-Bridge Motor Driver
- **Wide Operating Voltage:** VDC input ranges from 6.5V to 45V
- **Adjustable VREF:** Includes a trim potentiometer to easily set the VREF between ~1V and ~5V
- **Flexible Control:** The IN1 and IN2 pins can be driven externally via an MCU (via PWM) or set manually using jumpers.

## Hardware Overview

### Connectors
- **J1 (Voltage Input):** VDC and GND. Connect your main motor power supply here (6.5V - 45V) [file:1].
- **J3 (Motor Output):** OUT1 and OUT2. Connect directly to your brushed DC motor [file:1].
- **J2 & J4 (IO Connectors):** IN1 and IN2 logic inputs for controlling motor direction and state [file:1].

### Test Points
The board includes numerous test points (TP1 - TP12) strategically placed across VDC, +5V, GND, IN1, IN2, VREF, OUT1, and OUT2 for easy probing and debugging during development.

### Control Logic

| IN1 | IN2 | OUT1 | OUT2 | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | 0 | High-Z | High-Z | Coast; H-Bridge disabled to High-Z [file:1] |
| 0 | 1 | L | H | Reverse [file:1] |
| 1 | 0 | H | L | Forward [file:1] |
| 1 | 1 | L | L | Brake; low-side decay [file:1] |

*Note: For more information on VREF and current regulation, refer to page 8 of the DRV8870 datasheet.*

## License

This project is licensed under the MIT License.
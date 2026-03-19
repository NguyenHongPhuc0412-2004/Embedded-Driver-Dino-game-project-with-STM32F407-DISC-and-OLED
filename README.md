# Embedded-Driver-Dino-game-project-with-STM32F407-DISC
Description:
Bare-metal STM32F4 firmware development focusing on low-level driver implementation and serial communication. Programming ARM microcontrollers (STM32) from srcatch without using any IDE or third-party library or third-part HAL or CMSIS.
Responsibilities:
Architected low-level drivers using Bare-metal C (Direct Register Access) for GPIO, USART, and Timers on the STM32F407 platform, eliminating dependency on HAL libraries to optimize performance.
Implemented Hardware Interrupt Service Routines (ISR) for input handling, integrating a robust software debounce algorithm to ensure precise signal capture from mechanical buttons.
Established a bidirectional UART communication protocol to interface with a PC-based Python engine, achieving real-time data synchronization for control inputs.
Configured Advanced Timers and PWM channels to generate dynamic visual feedback (LED fading effects) responsive to serial data payloads received from the host.
Technologies:STM32F407DISC, Embedded C, EXTI Interrupts, Timer/PWM, USART, Python (Pygame), VSCode.

![language](https://img.shields.io/badge/language-C/C%2B%2B-orange)
![board](https://img.shields.io/badge/board-STM32F407DISC1-blue)
![ide](https://img.shields.io/badge/IDE-Keil%20MDK%2FVSCode-lightgrey)

> Mini game (Chrome Dino) on STM32F407 

![cover](docs/images/DINO.jpg)

## Repository Layout

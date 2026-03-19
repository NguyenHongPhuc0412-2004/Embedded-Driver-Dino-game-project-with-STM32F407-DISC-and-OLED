<div align="center">

# 🦕 Embedded Driver — Dino Game Project

### STM32F407 Discovery Board

**Bare-metal firmware from scratch — No HAL · No CMSIS · No IDE**

<br/>

![language](https://img.shields.io/badge/Language-Embedded_C-orange?style=for-the-badge&logo=c&logoColor=white)
![board](https://img.shields.io/badge/Board-STM32F407DISC1-blue?style=for-the-badge&logo=stmicroelectronics&logoColor=white)
![ide](https://img.shields.io/badge/Tools-VSCode_|_Keil_MDK-lightgrey?style=for-the-badge&logo=visualstudiocode&logoColor=white)
![python](https://img.shields.io/badge/Engine-Python_Pygame-3776AB?style=for-the-badge&logo=python&logoColor=white)

<br/>

![cover](docs/images/DINO.jpg)

<br/>

*The classic Chrome Dino game — controlled entirely by custom bare-metal drivers on STM32F407,*
*communicating in real-time with a Python game engine over UART.*

</div>

---

## 📖 Overview

This project is a complete bare-metal embedded system built from the ground up on the **STM32F407 Discovery Board**. Every peripheral driver — GPIO, USART, Timers, Interrupts — is hand-written through **direct register manipulation**, with absolutely no reliance on HAL libraries, CMSIS, or code-generation tools.

The STM32 board acts as a hardware game controller: physical button presses are captured via hardware interrupts, debounced in software, and transmitted to a **Python Pygame engine** on PC through a custom **bidirectional UART protocol**. The game responds by sending data back to the board to drive **PWM-controlled LED effects** that react to gameplay in real time.

```
┌─────────────────────────┐          UART           ┌─────────────────────────┐
│      STM32F407          │    ◄────────────────►    │      PC (Python)        │
│                         │                          │                         │
│  ▸ Button input (EXTI)  │  ── Jump Command ──►     │  ▸ Pygame Dino Engine   │
│  ▸ Software debounce    │                          │  ▸ Game logic & render  │
│  ▸ PWM LED feedback     │  ◄── Game State ────     │  ▸ Score tracking       │
└─────────────────────────┘                          └─────────────────────────┘
```

---

## ⚡ What I Built

🔩 **Bare-Metal Peripheral Drivers** — Architected low-level drivers for GPIO, USART, and Timers using direct register access on the STM32F407 platform, eliminating all dependency on HAL libraries to optimize performance and minimize overhead.

⚙️ **Hardware Interrupt & Debounce** — Implemented EXTI-based Interrupt Service Routines (ISR) for button input handling, integrated with a robust software debounce algorithm to ensure precise and reliable signal capture from mechanical switches.

📡 **Bidirectional UART Protocol** — Established a custom serial communication protocol to interface the STM32 with a PC-based Python engine, achieving real-time data synchronization for control inputs and game state feedback.

💡 **Dynamic PWM LED Effects** — Configured Advanced Timers and PWM output channels to generate smooth LED fading effects that respond dynamically to serial data payloads received from the host application.

---

## 🛠️ Technologies

| Category | Stack |
|:---------|:------|
| **Microcontroller** | STM32F407VGT6 — ARM Cortex-M4 @ 168 MHz |
| **Language** | Embedded C (bare-metal, direct register manipulation) |
| **Peripherals** | GPIO · EXTI Interrupts · USART · Timer / PWM |
| **PC Engine** | Python 3 · Pygame · PySerial |
| **Dev Tools** | VSCode · Keil MDK · ST-Link V2 |

---

## 🎮 How It Works

1. **Press the hardware button** on the STM32F407 board
2. The EXTI interrupt fires → debounce algorithm validates the press
3. A jump command is sent to the PC over UART
4. The Python Pygame engine makes the Dino jump on screen
5. Game state data is sent back → LEDs on the board react via PWM

---

<div align="center">

**Built from scratch with bare-metal registers ⚡**

*No HAL was harmed in the making of this project.*

</div>

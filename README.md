# 🔡 Morse Code Trainer (FPGA Project)

An **interactive Morse Code training game** built on the **Intel DE1-SoC FPGA board**.  
This project uses the FPGA’s **VGA display, PS/2 keyboard, HEX displays, audio output, and timer interrupts** to help users learn Morse code through two different modes of gameplay.

---

## 🎯 Features
- 🏠 **Home Screen** with navigation between modes  
- 📖 **Instruction Page** showing reference Morse code  
- 🎮 **Two Game Modes**:  
  1. **Mode 1 (Typing Trainer)** – Convert random letters into Morse code by typing dots/dashes on the keyboard.  
  2. **Mode 2 (Audio Trainer)** – Listen to Morse code audio and identify the correct letter.  
- ⏱️ **Timer-based gameplay** with countdown clock  
- ⭐ **Scoring system** displayed on VGA and HEX displays  
- 🔊 **Audio support** – Morse code signals played via the audio output  
- 🎨 **Custom VGA graphics** for backgrounds, letters, numbers, and symbols  

---

## 🛠️ Tech Stack
- **Hardware:** Intel DE1-SoC FPGA Board  
- **Language:** C (compiled with GCC for Nios II soft processor)  
- **Peripherals Used:**  
  - VGA Controller (pixel buffer)  
  - PS/2 Keyboard interface  
  - HEX Display output  
  - Interval Timer  
  - Audio Core (FIFO)  
  - Pushbuttons (KEYs) and LEDs  

---

## ⚡ How It Works
- The program runs on the **RISC V processor** inside the FPGA.  
- **Interrupts** handle:
  - `itimer_ISR` → countdown timer  
  - `KEY_ISR` → pushbutton input  
  - `PS2_ISR` → keyboard input  
  - `audio_ISR` → Morse code audio playback  
- VGA is used to draw:
  - Background screens (home, mode, instructions, game over)  
  - Letters, numbers, and Morse symbols (dots & dashes)  
- HEX displays show the countdown timer and user input.  
- Users interact with the game using the **PS/2 keyboard** and **pushbuttons**.  

---

## 🎮 Game Flow
1. **Home Page** – Select Mode 1 or Mode 2 with keyboard input.  
2. **Instruction Page** – View Morse reference before starting.  
3. **Gameplay**:  
   - Mode 1 → Type dots/dashes for the given random letter.  
   - Mode 2 → Hear Morse audio, guess the letter.  
4. **Scoring & Timer** – Correct answers increase score, game ends when timer reaches 0.  
5. **Game Over Page** – Final score displayed, return to home.



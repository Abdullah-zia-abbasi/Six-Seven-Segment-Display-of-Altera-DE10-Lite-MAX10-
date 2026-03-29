# Six-Seven-Segment-Display-of-Altera-DE10-Lite-MAX10-
Altera DE10-Lite (MAX10 – 10M50DAF484C7G)
Language: Verilog HDL
here is a complete **README.md** you can directly upload on github. it is simple, clean, and looks professional.

# Student ID Scrolling Display on FPGA

This project shows how to display a scrolling student ID on a 6 digit seven segment display using Verilog on an FPGA board. The design uses a smooth shifting window so that the digits move continuously across the displays.

The student ID used in this project is:

**34042633**


## Overview

The system displays 6 digits at a time on HEX0 to HEX5. The digits scroll automatically with control options using switches. A clock divider is used to slow down the movement so it is visible to the human eye.


## Features

* 6 seven segment displays (HEX0 to HEX5)
* smooth scrolling of digits
* adjustable speed
* pause and resume control
* forward and reverse direction
* clear display option
* reset system


## Hardware Requirements

* FPGA board (tested on Terasic DE10 Lite)
* on board 7 segment displays
* switches for control input
* 50 MHz clock


## Pin Assignment (example for DE10 Lite)

you need to assign pins manually in Quartus Pin Planner.

### clock

* CLOCK_50 → PIN P11

### switches

* SW[0] to SW[9] → assign according to board manual

### seven segment displays

each display has 7 segments (a to g):

* HEX0[0] to HEX0[6]
* HEX1[0] to HEX1[6]
* HEX2[0] to HEX2[6]
* HEX3[0] to HEX3[6]
* HEX4[0] to HEX4[6]
* HEX5[0] to HEX5[6]

refer to the board manual for exact pin numbers.

## Control Inputs

| Switch | Function                     |
| ------ | ---------------------------- |
| SW[5]  | speed control (fast or slow) |
| SW[4]  | pause scrolling              |
| SW[3]  | reverse direction            |
| SW[2]  | clear display                |
| SW[1]  | reset system                 |


## Working Principle

* the student ID is stored in an array
* a moving pointer selects 6 digits at a time
* digits shift left or right based on control input
* a clock divider controls scrolling speed
* a decoder converts digits into seven segment signals


## Project Structure

student_id.v   → main verilog module
README.md      → project description

## How to Run

1. open Quartus
2. create a new project
3. select correct FPGA device:

   * MAX 10
   * 10M50DAF484C7G
4. add the Verilog file
5. compile the design
6. open Pin Planner and assign pins
7. program the FPGA board

## Output

the student ID scrolls continuously across 6 displays with user control over speed and direction.


## Future Improvements

* add button control instead of switches
* display custom messages
* add multiple display modes
* integrate with sensors or external inputs

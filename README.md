# ARM-CortexM

## ARM CPU Architectures
ARM makes architectures and sells them. Not Hardware. Other Semicon companies nxp,ti,stm implement the architecture and get the controllers manufactured.

ARM - A - class: Application grade (can run OS - Mac(M1,M2),Linux)
      R - class: Realtime systems (Engine control/management controller | cpu has to respond in realtime)
      M - class: Microcontroller based application (toaster, remote control, power window,etc. any single targeted small application)

M series is simple to understand and straight forward. 

## Micro Architecture vs Architecture

Architecture: Specification of what a CPU should do or how it should behave. eg. Car should be able to turn right,left, forward. (only description)
Mv6, Mv7,etc..

Mv7 will be backwards compatible with Mv6..so on and so forth

Micro-Architecture: Actual Implementation of Architecture eg. Car with its components - steering, wheels (actual implemetation of description)
Cortex - M0, M4, M0+,.....

## How to Master CPU - Different Models to learn
ARM CPUs are based on Load/Store Architecture (RISC Architecture)

As an Embedded Software Engineer what all do you need to know about a CPU to Master it?

1. Programmers Model - Details Mode of operation of CPU and the registers that CPU have (GPRs and SFRs). How can a programmer imagine the computation being done by the CPU
2. Exception Model - Talks about how cpu can handle Exception/Interrupt* handling (Interrupt is external to CPU, Exception is internal)
3. Memory Model - Specifices how CPU Interacts with Memory.
4. Debug Model - External Debug hardware [Hardware Debugger] that can be connected to CPU that can let you read the CPU registers and control CPU

## Programmers Model - Register Set
Reference:

https://community.arm.com/cfs-file/__key/telligent-evolution-components-attachments/01-2142-00-00-00-00-52-96/White-Paper-_2D00_-Cortex_2D00_M-for-Beginners-_2D00_-2016-_2800_final-v3_2900_.pdf

M Class CPU has - 
16 GPRs : R0-R12, R13/MSP, R13/PSP, R14 (LR), R15 (PC)             
5 SFRs : xPSR, PRIMASK, FAULTMASK, BASEPRI, CONTROL
          ^      ^                       ^      ^
          |      |_______________________|      |
Program Status Reg          |              Control Register
                     Interrupt Mask Register

MSP - Main Stack Pointer, PSP - Process Stack Pointer, LR - Link Register, PC - Program Counter

Stack Pointer is required for C function calls to work
Link Register - Pointing to Address of instruction that CPU has to come back to after completing the execution of a function.
Program Counter - From where the instruction needs to be fetched.

xPSR (Program Status Registers) - Gives sum of EPSR, APSR, IPSR

Interrupt Mask Register

CPU can have many interrups and to each interrupt you can asign a priority level.
using PRIMASK and BASEPRI, you can control which interrupt to allow/attend to and which to be ignored. 
PRIMASK - Prioirty Mask
FAULTMASK - Fault Mask
BASEPRI - Base Priority

Control Register - Control the privilege(nPRIV bit) and which stack pointer (SPSEL bit) to use.

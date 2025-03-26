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

## Mental Model of CPU Memory interactions

ARM CPUs are based on Load/Store Architecture (RISC Architecture)

As an Embedded Software Engineer what all do you need to know about a CPU to Master it?

1. Programmers Model
2. Exception Model
3. Memory Model
4. Debug Model




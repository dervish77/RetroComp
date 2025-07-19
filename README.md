# RetroComp
RetroComp Homebrew Computer Design 

The RetroComp project specifies a design and implementation for a retro-style homebrew computer.  The design utilizes a backplane/motherboard approach similar in spirit to the old S-100 bus systems.  The backplane design supports some flexibility in the design of plugin modules for support of various kinds of peripherals.

The backplane design under consideration has two flavors - one is a traditional address/data/control signal based design, the other is a more modern approach using serial interfaces such as SPI and I2C for communication between modules.  A final decision on which approach to take has not yet been finalized.

Repo contents:

* docs/          - system design docs, block diagrams, etc
* hw/            - hardware design files
* ref/           - reference documents for integrated packages
* sw/            - software source code


## Requirements

* RetroComp system **shall** support a backplane with at least four slots.
  * RetroComp backplane **shall** support a dedicated slot for the CPU module (i.e. slot 0).
  * RetroComp backplane **shall** support a slot for keyboard input.
  * RetroComp backplane **shall** support a slot for video output.
  * RetroComp backplane **shall** support a slot for audio output.
  * RetroComp backplane *should* support slots for additional modules such as storage, serial I/O, parallel I/O.

* RetroAV shield **shall** support composite video output in Black&White using single RCA output jack.  
  * RetroAV **shall** support at least 20 characters by 16 lines of video output. 
  * RetroAV *should* support at least 40 characters by 24 lines of video output.
  * RetroAV *should* support color output if possible.

* RetroAV shield **shall** support analog audio output using RCA output jack.
  * RetroAV **shall** support a 1 volt peak to peak output signal.
  * RetroAV **shall** support at least one "voice" of audio output.
  * RetroAV *should* support more than one "voice" of audio output if possible.

* RetroAV shield **shall** support a serial interface connector as a 4 pin header.
  * RetroAV **shall** support a UART style serial interface.
  * RetroAV *should* support an I2C style serial interface.

* RetroAV code library **shall** minimally support a simple text terminal style of interface.
  * RetroAV **shall** support the standard ascii character set.
  * RetroAV **shall** support playing an audio tone for the bell character (i.e. control-G).
  * RetroAV **shall** support interfacing via the Arduino serial monitor (i.e. echo characters to serial monitor).
  * RetroAV *should* support interfacing via Arduino serial data pins (i.e. uart pins).

* RetroComp code library **shall** support enough software elements to boot up and execute manually entered code.
  * RetroComp *should* be supportable on variant boards via simple code modifications.


## High Level Design

### System Block Diagram

![System](https://github.com/dervish77/RetroComp/blob/main/docs/RetroComp-System-Block-Diagram.jpg?raw=true)

### Backplane Pin Assignments Diagram

![Backplane](https://github.com/dervish77/RetroComp/blob/main/docs/RetroComp-backplane.png?raw=true)

### HW Block Diagram

TBD

### SW Block Diagram

TBD


## Detailed Design

### Hardware

#### Backplane

The Backplane provides all of the interconnect between the modules of the system.

#### Power Supply

The Power Supply provides all of the necessary power to the backplane and the connected modules.

#### CPU Module

The CPU module is the heart of the system.  The CPU module executes the core software of the system.

#### KV Module

The KV module provides for the input of a PS2 keyboard and output of composite (or perhaps VGA) video.

#### Audio Module

The Audio module provides for the output of one channel or two channels of analog audio.

#### Storage Module

The Storage module provides support for program and data storage.

#### Serial I/O Module

The Serial I/O module provides support for at least one TTL or RS232 serial interface.

#### Parallel I/O Module

The Parallel I/O module provides support for at least one 8-bit input/output port.

### Software

#### Boot Monitor

tbd

#### Basic Interpreter

tbd

#### Assembler

tbd

#### C Compiler

tbd

#### Disk Operating System

tbd

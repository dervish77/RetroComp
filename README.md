# RetroComp
RetroComp Homebrew Computer Design 

The RetroComp project specifies a design and implementation for a retro-style homebrew computer.  The design utilizes a backplane/motherboard approach similar in spirit to the old S-100 bus systems.  The backplane design supports some flexibility in the design of plugin modules for support of various kinds of peripherals.

Repo contents:

* docs/          - system design docs, block diagrams, etc
* hw/            - hardware design files
* ref/           - reference documents for integrated packages


## Requirements

* RetroComp system **shall** support a backplane with at least four slots.
  * RetroComp backplane **shall** support a dedicated slot for the CPU module (i.e. slot 0).
  * RetroComp backplane **shall** support a slot for keyboard input.
  * RetroComp backplane **shall** support a slot for video output.
  * RetroComp backplane **shall** support a slot for audio output.

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

* RetroAV code library **shall** minimally support a standard Arduino UNO board.
  * RetroAV *should* be supportable on variant boards via simple code modifications.


## High Level Design

### System Block Diagram

![system](https://github.com/dervish77/RetroAV/blob/master/docs/RetroAV-System-Block-Diagram.png?raw=true)

### Backplane Pin Assignments Diagram

TBD

### HW Block Diagram

![HW](https://github.com/dervish77/RetroAV/blob/master/docs/RetroAV-HW-Block-Diagram.png?raw=true)

### SW Block Diagram

![SW](https://github.com/dervish77/RetroAV/blob/master/docs/RetroAV-SW-Block-Diagram.png?raw=true)


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

#### Keyboard Task

tbd

#### Video Task

tbd

#### Audio Task

tbd

#### Serial Task

tbd

#### UI Manager

tbd

#### Arduino Interface

tbd


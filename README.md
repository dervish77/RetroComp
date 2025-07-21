# RetroComp
RetroComp Homebrew Computer Design 

The RetroComp project specifies a design and implementation for a retro-style homebrew computer.  The design utilizes a backplane/motherboard approach similar in spirit to the old S-100 bus systems.  The backplane design supports some flexibility in the design of plugin modules for support of various kinds of peripherals.

The backplane design under consideration has two flavors - one is a traditional address/data/control signal based design, the other is a more modern approach using serial interfaces such as SPI and I2C for communication between modules.  A final decision on which approach to take has not yet been finalized.  Under the traditional base design, address and data lines would connect to all backplane slots.  Under the modern design, slots 1, 2, 3 would have SPI and I2C connections, where slots 4, 5, 6, would have only I2C connections.

Repo contents:

* docs/          - system design docs, block diagrams, etc
* hw/            - hardware design files
* ref/           - reference documents for integrated packages
* sw/            - software source code


## Requirements

* RetroComp system **shall** support a backplane with at least four slots but no more than seven slots.
  * RetroComp backplane **shall** support a dedicated slot for the CPU module (i.e. slot 0).
  * RetroComp backplane **shall** support a slot for keyboard input.
  * RetroComp backplane **shall** support a slot for video output.
  * RetroComp backplane **shall** support a slot for audio output.
  * RetroComp backplane *should* support slots for additional modules such as storage, serial I/O, parallel I/O.
  * RetroComp backplane **shall** utilize 50 or fewer pins.
  * RetroComp backplane *should* utilize 40 or fewer pins.

* RetroComp system **shall** support a CPU module that provides the main processing functions of the system.
  * CPU module **shall** support a microprocessor based central processing unit.
  * CPU module **shall** support random access memory for temporary storage of programs and/or data.
  * CPU module **shall** support read only memory for storing the boot monitor software.
  * CPU module **shall** support methods for addressing and accessing every slot on the backplane.

* RetroComp system **shall** support a KV module that provides keyboard input and video output.
  * KV module **shall** support keyboard input via a standard PS2 keyboard input connector.
  * KV module **shall** support a composite video output interface using a single RCA output jack.
  * KV module **shall** support at least 20 characters by 16 lines of video output.
  * KV module *should* support at least 40 characters by 24 lines of video output.
  * KV module *should* support color video output if possible.

* RetroComp system **shall** support an Audio module that provides audio output.
  * Audio module **shall** support analog audio output using RCA output jack.
  * Audio module **shall** support a 1 volt peak to peak output signal.
  * Audio module **shall** support at least one "voice" of audio output.
  * Audio module *should* support more than one "voice" of audio output if possible.
  * Audio module *should* support a direct speaker connection (i.e. powered audio output) for an 8 ohm speaker.

* RetroComp Storage module *should* support a Storage module that provides program and data storage and retrieval.
  * Storage module **shall** support an EEPROM method of data storage.
  * Storage module *should* support an SD Card method of data storage.
  * Storage module *should* support a method for connecting an external storage device such as USB, IDE, or similar media.

* RetroComp Serial I/O module *should* support a Serial I/O module that provides serial input and output.
  * Serial I/O module **shall** support one serial interface connector as a 4 pin header.
  * Serial I/O module **shall** support a TTL style serial interface.
  * Serial I/O module *should* support an RS232 style serial interface.
  * Serial I/O module *should* support at least one additional serial interface. 

* RetroComp Parallel I/O module **shall** support a Parallel I/O module that provides parallel input and output.
  * Parallel I/O module **shall** support one parallel interface connector as an 8 pin header.
  * Parallel I/O module *should* support at least one additional connector as an 8 pin header.

* RetroComp code library **shall** support enough software elements to boot up and execute manually entered code.
  * RetroComp **shall** include a boot monitor software to initialize the system and provide basic monitor functions.
  * RetroComp **shall** include a basic interpreter software to allow for minimal programmability of the system.
  * RetroComp *should* include assembler software to allow for low level programming of the system.
  * RetroComp *should* include compiler software to allow for more advanced programming of the system.
  * RetroComp *should* include disk operating software for managing storage of programs and data.


## High Level Design

### System Block Diagram

![System](https://github.com/dervish77/RetroComp/blob/main/docs/RetroComp-System-Block-Diagram.png?raw=true)

### Traditional Backplane Pin Assignments Diagram

![Backplane Traditional](https://github.com/dervish77/RetroComp/blob/main/docs/RetroComp-alt-backplane.png?raw=true)

### Modern Backplane Pin Assignments Diagram

![Backplane Modern](https://github.com/dervish77/RetroComp/blob/main/docs/RetroComp-backplane.png?raw=true)

### HW Block Diagram

![CPU modern](https://github.com/dervish77/RetroComp/blob/main/docs/RetroComp-CPU-Block-Diagram.png?raw=true)

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

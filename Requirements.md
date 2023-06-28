## Problems to solve:
* Every FS team needs at least a subset of these CAN devices
   * includes analog to CAN converters (sensor boards), CAN IO expander/multiplexer (control boards), CAN datalogger, CAN gateways, etc
*   Commercial CAN devices are expensive
*   Commercial CAN devices often have severe limitations
   * First party software
   * Single function, limited function (only gateway with no IO, four or less analog inputs, etc), but CAN devices can serve many purposes and ideally can have more functionality
* The knowledge to design a custom CAN device is available to undergrads but not accessible, especially for new or EE-light teams
   * this goes doubly for a robust, versatile, debuggable CAN device

## Potential features:

###  Need to have:
* open source hardware, able to be modified by students (can be viewed and edited by programs accessible to students)
* 2 CAN buses
* 6 analog/digital IO
   * hardware configurable analog in, digital in/out, PWM
   * hardware configurable pull-up/pull-down
* USB programming
* CAN to USB bridge
* system-level modularity
   * easy, reliable connection with other boards must be maintained, including daisy chaining (daisy chaining may be moved off-board, but must be clearly explained)
   * can be swapped out for replacements (or removed for comp)
   * no specific sensor targets (unless transparently integrated, e.g. wheel speed on the same IO as analog inputs)
* accessible assembly
   * reflow and/or hand solderable components
   * no small package or dense layout
   * parts must be common and in supply, recommended alternatives must be provided in case of shortage or obsoletion
   * connectors preferred, limited splicing if it greatly impacts space/cost
* accessible programming
   * support Arduino IDE and C/C++
   * provide simple example programs and documentation for interfaces
* robust powerchain
   * basic protection for shorts, reverse polarity, overcurrent
   * 12V compatibility with power supply
   * 5V compatibility with sensors/controls/CAN
* under $100, before assembly (students can choose to build in house or have assembled)

###  Nice to have:
* 2  CAN FD buses
   * Indication of bus activity (LED/digital output corresponding to message rate)
* 8+ analog/digital IO
   * software configurable pull-up/pull-down
   * software configurable analog in, digital in/out, PWM
* potentially use a dev board rather than a stand alone MCU
   * simplified BOM, assembly, programming, etc
* potentially a PCB mountable version (i.e. castellated pins)
   * for direct integration with another custom device like a general VCU, datalogger, etc
* easy assembly
   * ideally pure SMT on a single sided, 2 layer board
      * 2 layer boards would be easier for students new to PCB design to potentially edit for their own purposes
      * this becomes much more feasible when considering utilizing pre-made dev boards and multi-purpose ICs
   * possibly options for both purely SMT or through hole?
   * absolutely no splicing
   * supplemental material on assembly techniques
* internal modularity
   * easily converted between MCUs (or dev boards)
   * easily converted between connectors (or no/fewer connectors)
   * can be customized for more specific purposes (easily remove a CAN bus, add IO, add other serial or parallel interfaces, etc)
* easy/versatile programming interfaces
   * C/C++
   * Arduino
   * Micropython/CircuitPython
   * Simulink
   * RTOS?
   * JTAG
   * basic built-in compatibility with common off the shelf CAN devices (AEM ECU, AIM datalogger, etc)
* flexible powerchain
   * range of power supply options, 5V to 24V+ (24V is the next most common LV, would be nice to support)
   * 3V3, 5V, 12V, 24V compatibility with sensors/controls/CAN
* under $50, possibly after some editing (remove 2nd CAN bus, use cheaper connectors, etc)

###  Hard no:
* no wireless interfaces (we won't build that functionality in ourselves, teams can add it if they want)
* no obscure products
* no restrictive software/toolchain

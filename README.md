# nasscom-vsd-soc-design-program
Digital VLSI SoC Design and Planning
Sky130 Day 1 - Inception of open-source EDA, OpenLANE and Sky130 PDK SKY130_D1_SK1 - How to talk to computers SKY_L3 - From Software Applications to Hardware
DAY1
Processor/SoC:
![1 1 processor](https://github.com/user-attachments/assets/6660c8ad-df09-4cae-a160-3c6b42a947c9)

Left Side Components
JTAG-UART FTDI
a) JTAG (Joint Test Action Group): Helps in testing and debugging the chip.
b) UART (Universal Asynchronous Receiver-Transmitter): Used for sending and receiving data serially between devices.
c) FTDI (Future Technology Devices International): A chip that allows the processor to connect to a USB for debugging.

QSPI1-Flash
a) QSPI (Quad Serial Peripheral Interface): A fast communication link.
b) Flash Memory: Stores important data like firmware (the program that runs the hardware) and configuration settings.

I2C0-EEPROM
a) I2C (Inter-Integrated Circuit): A protocol that allows two chips to talk to each other.
b) EEPROM (Electrically Erasable Programmable Read-Only Memory): Stores small, essential data like settings that remain even after a power reset.

Clock and Reset
a) Clock (clk): A signal that keeps all operations in sync.
b) Reset: Resets the processor and peripherals to their starting state.

Top, Bottom, and Right Side Components
SDRAM
a) SDRAM (Synchronous Dynamic RAM): Temporary memory where the processor stores data while it's working.
b) Located on the top, bottom, and right sides for quick access by the processor.

Direct I2C, QSPI, GPIO
a) I2C and QSPI: Additional communication interfaces for connecting sensors or fast devices like memory chips.
b) GPIO (General Purpose Input/Output): Pins that can do basic input/output tasks, like controlling LEDs or detecting button presses.

PWM0-5
a) PWM (Pulse Width Modulation): Outputs signals to control devices like motors or adjust brightness of LEDs.
b) There are six PWM outputs, labeled PWM0 to PWM5.

Bottom Side Components
VCC/GND
a) VCC: Supplies power to the chip and peripherals.
b) GND: Provides a ground reference for electrical connections.

ADC
a) ADC (Analog-to-Digital Converter): Converts real-world signals (like temperature or sound) into digital data.
b) Shares pins with GPIO, so they can be used as either digital inputs/outputs or analog inputs.

Additional Communication Interfaces (Top Side)
I2C1, QSPI2, UART1/2
a) I2C1: Another I2C interface for connecting more sensors or chips.
b) QSPI2: A second QSPI interface for high-speed communication.
c) UART1/2: Two more UART interfaces for serial communication.

GPIO (General Purpose Input/Output)
a) Scattered around the chip and can be used for multiple tasks.
b) Often paired with specific protocols like I2C or QSPI for flexibility.

What is package and its types
![1 2](https://github.com/user-attachments/assets/15f920d6-9a29-4242-b930-0c8aa6de331c)
1] BGA (Ball Grid Array)
a) BGA uses tiny solder balls arranged in a grid under the chip for electrical connections.
b) It allows more connections in a small area and performs well in high-speed applications.
c) Found in high-performance devices like CPUs and GPUs.
2] DIP (Dual In-line Package)
a) DIP has two rows of pins sticking out from the sides, like legs.
b) These are used in older PCB designs where you push the pins through holes.
c) Often seen in simple or old electronics.
3] QFN (Quad Flat No-lead Package)
a) QFN is small, with its metal leads exposed at the edges for easy soldering.
b) It performs well because the short leads reduce electrical resistance.
c) Common in compact devices like smartphones.
4] QFP (Quad Flat Package)
a) QFP has metal leads coming out from all four sides.
b) Ideal for chips needing many connections, like microcontrollers.
c) Meant for surface-mounted PCBs.
5] SOP (Small Outline Package)
a) SOP has metal leads on two sides and is smaller than DIP.
b) Commonly used for memory chips in electronics like TVs and phones.
c) Designed for surface mounting.
6] SOT (Small Outline Transistor)
a) SOT packages are for tiny components like transistors with few connections.
b) Comes in versions like SOT23, with three leads for simple circuits.
c) Used in small and low-power devices like remote controls.
7] SOT223
a) This is used for components like transistors and regulators in power circuits.
b) It has bigger leads than SOT23 to handle more current.
c) Helps with heat dissipation because of its larger size.

What is PADS, DIE, Core, and MACROS
![1 3](https://github.com/user-attachments/assets/15631ce2-ed4a-4b73-85df-0e9aaa527982)
1. PADS (Bonding Pads)
A) Definition:

Pads are tiny metal squares on the edges of a chip.
They connect the chip’s internal circuits to the outside world.
B) Purpose:

They help the chip communicate with external devices by connecting it to package pins or solder balls.
C) Types:

Wire Bond Pads:
Used to attach thin metal wires (like gold or aluminum) that connect the pad to external pins.
Flip-Chip Pads:
Used for direct connection to a circuit board using bumps or solder balls.
D) Importance:

They ensure signals, power, and ground connections work reliably between the chip and other devices.
A good pad design makes the chip work better and last longer.
2. DIE (Semiconductor Die)
A) Definition:

A die is a tiny square of silicon that contains the actual working parts of a chip.
B) Purpose:

The die holds all the important components like transistors (tiny switches), resistors, and capacitors that make the chip function.
C) Fabrication:

A silicon wafer is like a big sheet with thousands of small circuits made on it.
The wafer is cut into individual pieces, called dies.
These dies are then packaged to make the final product you can use.
D) Importance:

The die is the most important part of the chip; it does all the actual work.
How well it is designed affects the chip’s performance.
3. Core (in IC Design)
A) Definition:

The core is the "brain" of the chip.
It’s the central area where all the main circuitry, like logic gates and transistors, is located.
B) Purpose:

The core does the main job of the chip, whether it’s processing data, storing memory, or controlling other devices.
4. MACROS (Hard Macros & Soft Macros)
![1 4](https://github.com/user-attachments/assets/0979cfe6-3dca-4a28-ac4c-6e451661c872)
1. Macros
a) Definition
Macros are pre-designed blocks used in making integrated circuits (ICs), especially in complex systems like ASICs and SoCs. They are like reusable building blocks for chip designs.

b) Types of Macros

Hard Macros:

Pre-built and fixed design blocks.
Cannot be changed during placement or routing.
Technology-specific and optimized for performance.
Examples: Memory blocks (e.g., SRAM, ROM), logic gates, and analog components like PLLs or ADCs.
Soft Macros:

Flexible and described at the RTL (Register Transfer Level).
Can be modified during the design process.
Examples: Processor IP cores, bus interfaces, and configurable logic blocks.
c) Purpose
Macros simplify the design process by reusing verified blocks, saving time and effort in complex IC design.

d) Importance
Using macros ensures reliability and saves time, allowing designers to focus on adding new features rather than reinventing standard functionalities.

2. Foundry
a) Definition
A foundry is a factory where semiconductor chips are made using silicon wafers and advanced equipment.

b) Function
Foundries manufacture chips by following steps like deposition, etching, doping, and photolithography. They do not design chips themselves but make them for fabless companies.

c) Examples of Foundries

TSMC (Taiwan Semiconductor Manufacturing Company)
Samsung Foundry
GlobalFoundries
d) Importance
Foundries allow chip design companies to focus on innovation while leaving the complex manufacturing process to specialized facilities.

3. Lithography System
a) Definition
A lithography system is a machine used to create patterns on silicon wafers by shining light or energy through a mask onto the wafer.

b) Types of Lithography

Optical Lithography: Uses ultraviolet (UV) light to transfer patterns.
Extreme Ultraviolet (EUV) Lithography: Uses very short wavelengths (13.5 nm) for making smaller, more precise patterns for advanced chips (e.g., 7nm technology).
Electron Beam Lithography: Uses an electron beam to directly write patterns, mainly for low-volume or prototype production.
c) Components

Light Source: Generates light or energy beams like UV or EUV light.
Mask/Reticle: Holds the pattern to be transferred to the wafer.
Projection Lens: Focuses the light onto the wafer.
d) Importance
Lithography defines the size and detail of features on a chip. Advanced lithography is crucial for making smaller, faster, and more power-efficient chips.

4. Photolithography
a) Definition
Photolithography is a key process in semiconductor manufacturing. It uses light to transfer patterns from a mask onto a silicon wafer, forming circuits.

b) Steps in Photolithography

Coating the Wafer: Apply a light-sensitive material (photoresist) to the wafer.
Exposure: Shine light through a mask to expose parts of the photoresist.
Development: Wash away exposed or unexposed photoresist (depending on the type used).
Etching: Use the remaining photoresist as a guide to etch patterns into the wafer.
Removal: Remove the leftover photoresist, leaving the etched pattern.
c) Types of Photoresist

Positive Photoresist: The exposed areas dissolve and are removed during development.
Negative Photoresist: The exposed areas harden and remain after development, while unexposed areas are removed.
d) Importance
Photolithography is vital for creating the detailed patterns on chips that determine how they function. It directly affects chip performance and power consumption.

Stopwatch Application Workflow :
![1 5](https://github.com/user-attachments/assets/1feb601d-daf8-4eb3-a5b7-305f4889017d)
1. Application Software (Stopwatch App)
This is the software that the user interacts with directly.
a) Example:

The Stopwatch app runs on your computer or laptop.
It has buttons like Start, Pause, and Reset that the user can click.
b) Functionality:

The app acts as a bridge between the user and the system.
When the user clicks a button, the app processes the command and updates the timer accordingly.
2. System Software
This layer ensures smooth communication between the app and the hardware.

a) Operating System (OS):

The OS is the "manager" of the computer's resources (CPU, memory, and devices).
It runs the Stopwatch app and handles other tasks in the background (like managing memory or input/output).
Examples of OS: Windows, macOS, Linux.
b) Compiler:

The compiler translates the app's code (written in languages like C, C++, or Java) into a language the computer can understand.
The output is an executable file (e.g., .exe for Windows).
c) Assembler:

The assembler takes the output of the compiler and converts it into binary machine code (e.g., 10101001).
This binary code is the set of instructions that the hardware can directly execute.
3. Hardware
The physical components of the computer execute the binary instructions.

a) Processor:

The processor (or CPU) performs the actual operations.
It executes the binary instructions to handle tasks like starting the timer or updating the display.
b) Digital Circuits:

Supporting components like:
Clock (Clk): Keeps the system in sync and manages timing.
Input (Din): Takes input data, such as user commands.
Output (Dout): Displays the stopwatch time or results.
Summary of the Workflow:
User Interaction:

The user clicks buttons like Start, Pause, or Reset on the Stopwatch app.
Operating System:

Manages system resources and ensures the app runs smoothly.
Code Translation:

The compiler converts the app's code into instructions.
The assembler further translates these instructions into binary machine code.
Hardware Execution:

The processor and circuits execute the instructions to perform tasks like starting/stopping the timer or updating the display.

ASIC Design Flow Overview
![1 6](https://github.com/user-attachments/assets/1dae0454-5ff5-4b95-a8e7-280086b5d553)
1. Register Transfer Level (RTL)
a. Starting Point: The design is described using a high-level hardware description language like Verilog or VHDL.
b. Function: The RTL describes how data flows between registers and how the logic components operate within the design.
2. Synthesis (Synth)
![1 7](https://github.com/user-attachments/assets/e30689fb-f48e-4f03-af8c-7cb9640194f5)
Input: RTL description
a) RTL stands for Register-Transfer Level.

It is a high-level description of the digital circuit using hardware description languages (HDLs) like Verilog or VHDL.
It describes the design's behavior and data flow.
b) The RTL description includes:

Logical expressions.
Components like registers, adders, and multiplexers.
Output: Gate-level netlist
a) The gate-level netlist is the detailed description of the design.

It includes interconnected gates like AND, OR, NOT, and flip-flops.
It represents how the circuit will be implemented physically.
b) The netlist is:

Technology-specific (depends on the standard cells provided by the technology library).
Optimized for power, speed, and area.
Process:
a) Synthesis:

A synthesis tool (like Design Compiler or Genus) converts the RTL description into a gate-level netlist.
It replaces high-level RTL constructs with actual logic gates.
b) Technology mapping:

The gates in the netlist are chosen from a specific technology library.
The library is provided by the Process Design Kit (PDK), which is specific to the manufacturing process.
Example: If the PDK supports 7nm technology, the gates and cells will conform to this process size.

3. Floor Planning + Power Planning (FP + PP)
![1 8](https://github.com/user-attachments/assets/20e54e17-6522-4e05-9ab4-eff3b8687481)
![1 9](https://github.com/user-attachments/assets/3983cdd9-5f55-4432-8743-1faaf73485ca)
Input

a) Gate-level netlist:
A description of the digital circuit in terms of logic gates and their interconnections. This is the starting point for creating the physical layout.
Process

a) Physical layout design:
The process of arranging the various components of the circuit (like logic gates, blocks, and connections) on the chip in a way that fits within the physical constraints of the design.
b) Positioning key blocks:
Placing the major functional parts of the circuit, such as processors, memory, and other essential blocks, in optimal locations on the chip.
c) I/O pin placement:
Deciding where to place input/output (I/O) pins on the chip for efficient communication with external components.
d) Power distribution network:
Designing pathways for power to flow throughout the chip, ensuring that all parts of the design receive the power they need to function correctly.
Power Planning

a) Ensures sufficient power:
Makes sure that every part of the circuit gets enough power for reliable operation.
b) Avoids power-related issues:
Prevents problems like voltage drops or overheating by designing an effective power delivery system.

4. Placement (Place)
![1 10](https://github.com/user-attachments/assets/34d95906-1294-420c-b321-2edc2b0859de)
Input
a) Gate-Level Netlist: A list describing the logic gates and flip-flops and their connections.
b) Floorplan: The layout of chip areas allocated for specific functionalities.

Process
a) Objective: Arrange logic gates and flip-flops in specific physical locations on the chip.
b) Goal: Ensure efficient design by minimizing chip area, reducing wire lengths, and meeting timing constraints.

Stages of Placement

Global Placement:
a) Logic gates and flip-flops are positioned approximately on the chip.
b) Cells may overlap in this stage.
Detailed Placement:
a) Refinement of the positions from global placement.
b) Ensures cells follow placement rules and are optimally placed without overlap.

5. Clock Tree Synthesis (CTS)
![1 11](https://github.com/user-attachments/assets/01f99d0e-9a9b-46d9-8357-2d99e4f66b5c)
Clock Tree Synthesis (CTS) Purpose: a) The clock tree is designed to distribute the clock signal evenly throughout the chip. b) Its goal is to ensure that all flip-flops (the memory elements) on the chip receive the clock signal at the same time.

Avoiding Clock Skew: a) Clock skew happens when the clock signal reaches different parts of the chip at different times. b) The clock tree minimizes clock skew, ensuring that all flip-flops are synchronized and receive the clock signal with no delay differences.

Ensuring Timing Synchronization: a) Proper clock synchronization ensures that all flip-flops are triggered at the same moment, which is essential for the chip's reliable operation. b) Without synchronization, the chip might perform incorrectly, leading to errors in processing or data storage.

Design of Clock Tree: a) The clock tree uses buffers, inverters, and other components to evenly distribute the clock signal. b) The design ensures the signal reaches all parts of the chip in a balanced and controlled manner.

6. Routing (Route)
![1 12](https://github.com/user-attachments/assets/9ffc56ad-f4ae-4001-9f30-b761dddf85a3)
Routing Tools Connect Placed Gates: a) Routing refers to the process of connecting the gates (logic elements) that were already placed on the chip. b) This is done using metal wires which are designed to form electrical paths between the gates according to the netlist (a list showing how components are connected).

Follow Design Rules: a) Design rules are a set of guidelines that ensure the chip is manufacturable and works correctly. These include minimum spacing between wires, wire widths, etc. b) Routing tools must ensure that the wires are placed in accordance with these design rules to avoid errors during manufacturing.

Optimize Performance: a) Routing tools also try to optimize performance by ensuring that the wires are placed efficiently. This means trying to minimize the delay (or resistance) of the electrical signals traveling through the wires. b) Shorter paths between gates are preferred as they reduce signal delay, improving the overall speed of the chip.

Signal Integrity Concerns: a) Crosstalk occurs when signals in nearby wires interfere with each other. It can cause errors in the signals. b) Electromagnetic interference (EMI) happens when signals from one wire affect another wire, leading to performance issues or even malfunctioning circuits. Routing tools must minimize these issues by maintaining proper distance and shielding between wires.

7. Sign-off
Timing Closure
a) What it means: Ensuring that all the signals in the design reach their destination at the correct time.
b) Why it’s important: If signals don't arrive on time, the design will not work properly, causing delays or errors.

Power Analysis
a) What it means: Verifying that the design can provide enough power to all components without overloading any part.
b) Why it’s important: Insufficient power can lead to the design not functioning or getting damaged. The power needs to be distributed properly throughout the design.

Signal Integrity Checks
a) What it means: Checking if there are any problems with how signals travel through the circuit. This includes ensuring that signals don't interfere with each other (crosstalk) and that they don’t lose their strength (electromigration).
b) Why it’s important: Poor signal integrity can cause the design to malfunction, as signals may become weak or corrupted.

8. GDSII (Graphic Data System II) Output: The final step produces the GDSII file, which contains the full physical layout of the chip. This file is sent to the semiconductor foundry for fabrication.

OpenLaneThe Open-Source Infrastructure Platform for Silicon Development:
![1 13](https://github.com/user-attachments/assets/8ea388f6-8214-4354-9ff4-45d2afd6c837)
What is OpenLane? a) OpenLane is a platform for creating silicon chips.
b) It is designed to help turn designs into actual working hardware (silicon chips).

Supports Open-Source Tools: a) OpenLane uses tools that are open-source, meaning anyone can use and modify them for free.
b) Some of the key tools used by OpenLane include:

Yosys: A tool for converting your designs into a form that can be used to create a chip.
OpenROAD: A tool for physical design, which helps in the placement and routing of the components on the chip.
Magic: A tool used for chip layout design.
KLayout: A tool for viewing and editing chip layouts.
Used for Every Open MPW and chipIgnite Shuttle: a) Since 2020, OpenLane has been used in every Open MPW (Multi-Project Wafer) and chipIgnite shuttle.
b) These are programs where multiple chip designs from different projects are sent together for manufacturing, making it more cost-effective for small teams or research projects.

Simplifies the Process of Creating Chips: a) OpenLane integrates many different steps involved in chip design into a single platform.
b) This means users don't have to manually manage or switch between different tools for each step.

Uses Simple Configuration Files: a) Instead of needing to understand complex coding or processes, OpenLane allows users to configure their projects using simple configuration files.
b) This makes it easier for users to harden (finalize) their designs without needing deep expertise in every tool.

OpenLANE ASIC Flow
![1 14](https://github.com/user-attachments/assets/e763f1a8-36c1-47ae-9194-c6446d9071bb)
1. Design RTL
a) What is RTL?
RTL (Register Transfer Level) is a high-level description of how a circuit works. It defines how data moves between registers (memory units) and how the logic operates on this data.
b) Purpose of RTL
It serves as the blueprint for the hardware and is written using a Hardware Description Language (HDL) like Verilog.

2. RTL Synthesis (Yosys + abc)
a) Input: RTL description
The RTL code created in step 1 is the input here.
b) Process: Synthesis
Synthesis converts the high-level RTL code into a gate-level design (netlist), which uses basic logic gates like AND, OR, etc. This step also optimizes the design for performance.
c) Output: Gate-level netlist
A netlist is generated, which includes all the gates (AND, OR) and flip-flops (memory elements) used in the circuit.

3. Static Timing Analysis (STA) - OpenSTA
a) What is STA?
STA checks if the circuit meets timing requirements, ensuring data arrives at the right time and operations happen in sequence.
b) Tool used: OpenSTA
OpenSTA is used to analyze the timing of the design and detect any timing issues.

4. Design for Testability (DFT)
a) What is DFT?
DFT is the process of adding special structures to the design that allow it to be easily tested. These structures help detect faults and verify the functionality of the circuit.
b) Purpose:
It makes sure the chip can be tested properly during manufacturing to catch any issues before use.

5. Floorplanning, Placement, CTS, and Optimization (OpenROAD App)
a) Floorplanning:
This step defines where different parts of the chip will go. It organizes blocks, input/output pins, and the power distribution network.
b) Placement:
The gates from the synthesized netlist are placed in specific locations on the chip. The goal is to minimize area and wire length, while ensuring timing constraints are met.
c) Clock Tree Synthesis (CTS):
The clock signal needs to reach all parts of the chip evenly. CTS ensures the clock signal is distributed without delays (clock skew).
d) Optimization:
Techniques are applied to improve power consumption, performance, and area (PPA), making the design more efficient.
e) Special Scripts:
Fake antenna diodes are used to prevent antenna effects (unwanted signals) during the design process.

6. Logical Equivalence Check (LEC) - Yosys
a) What is LEC?
LEC checks if the synthesized netlist still works the same way as the original RTL design. It ensures that no unintended changes occurred during the synthesis process.
b) Tool used: Yosys
Yosys is used to perform LEC.

7. Detailed Routing (TritonRoute)
a) What is Routing?
Routing connects the logic gates on the chip using metal layers for signals to travel.
b) Tool used: TritonRoute
TritonRoute is used to ensure the routes are correctly placed, adhere to design rules, and meet signal integrity requirements (avoiding errors in signal transmission).

8. RC Extraction and STA
a) RC Extraction:
This step calculates the resistance (R) and capacitance (C) of the routing (wires), as they can affect the circuit's performance.
b) STA (with parasitics):
After RC extraction, STA is repeated with the updated design to ensure timing is still accurate despite the new resistance and capacitance values.

9. Physical Verification (Magic & Netgen)
a) Physical Verification:
This step ensures the layout follows all manufacturing rules and the design works as expected.
b) Tools used: Magic & Netgen
Magic and Netgen tools are used to perform the verification, checking if everything is correctly laid out and ready for manufacturing.

10. GDSII Generation (Magic)
a) What is GDSII?
GDSII is the standard file format used for chip layouts.
b) Process:
The final chip layout is converted into a GDSII file, which is then sent to a semiconductor foundry for actual chip fabrication. This is the last step before manufacturing the physical chip.

This flow describes the typical steps involved in designing and manufacturing an integrated circuit (IC). Each step ensures that the design works properly, meets timing constraints, and can be physically fabricated.

Fault Tool in Design for Test (DFT):
![1 15](https://github.com/user-attachments/assets/6a3f6865-0f40-4315-b16b-a215117114db)
1. Scan Insertion
a) Adds scan chains to the circuit:

Scan chains are special pathways added to the circuit to allow test data to flow in and out easily.
This makes it easier to test the internal parts of the chip (IC).
b) Helps in testing internal components:

By inserting scan chains, you can access and test parts of the chip that are normally hard to reach during regular operation.
2. ATPG (Automatic Test Pattern Generation)
a) Automatically generates test patterns:

ATPG is a method that automatically creates test patterns (sequences of 0s and 1s) to check for faults in the circuit.
These patterns are designed to find common problems, like stuck-at faults, where a signal gets stuck at either 0 or 1.
b) Simulates expected circuit behavior:

ATPG simulates how the circuit should behave with the test patterns and checks if any errors occur.
3. Test Patterns Compaction
a) Reduces the number of test patterns:

Instead of using many test patterns, the FAULT tool reduces their number without losing the effectiveness of fault detection.
This makes the testing process more efficient.
b) Ensures efficient testing:

Even with fewer test patterns, the testing remains comprehensive enough to find most defects, saving resources and time.
4. Fault Coverage
a) Measures test pattern effectiveness:

Fault coverage is a measure of how well the generated test patterns detect faults in the circuit.
A higher percentage of fault coverage means that the tests are better at detecting problems.
b) Indicates effective testing:

If fault coverage is high, it means the tests are thorough and can catch more defects, leading to better quality chips.
5. Fault Simulation
a) Simulates faults in the circuit:

This step involves simulating faults (such as stuck-at faults) in the circuit to check if the test patterns can detect them.
It ensures the test patterns are capable of finding errors that might happen in real-world scenarios.
b) Checks test pattern accuracy:

Fault simulation checks whether the test patterns can correctly detect faults, improving the reliability of the testing process.
Benefits of the FAULT Tool
Enhanced Testability:

By adding scan chains, testing complex circuits becomes easier and more accessible.
Comprehensive Fault Detection:

The tool ensures that various faults, like stuck-at faults, are detected during testing, which prevents faulty chips from being produced.
Efficient Testing:

The FAULT tool reduces the number of test patterns needed without sacrificing the ability to detect defects, making the testing process faster and more resource-efficient.
Reliability:

With higher fault coverage, the FAULT tool improves the reliability of the chip by detecting potential defects early in the design phase, preventing issues after production.


OpenROAD Tool:
![1 16](https://github.com/user-attachments/assets/0190ba9c-ef48-41de-8adc-075d317c7bff)
1. Floor/Power Planning
a) Floor Planning: This step defines the layout of the chip’s physical area. It decides where each circuit component will go.
b) Power Planning: Ensures that the power network can deliver power to every part of the chip, making sure there are no areas without power.
2. Decoupling Capacitors and Tap Cells Insertion
a) Decoupling Capacitors: These are added to stabilize the power supply by filtering out unwanted noise.
b) Tap Cells: These cells are inserted to make sure the chip’s parts are properly connected to the power supply and to prevent issues like latch-up (a problem in CMOS circuits).
3. Placement (Global and Detailed)
a) Global Placement: This is the first step where the cells (components) are placed in a rough manner across the chip area.
b) Detailed Placement: After global placement, this step fine-tunes the positions of the cells to optimize the layout, improving efficiency.
4. Post-Placement Optimization
a) This step improves the layout after the cells are placed, making sure there is less crowding, better performance, and reduced power consumption.
5. Clock Tree Synthesis (CTS)
a) This step creates a network to distribute the clock signal evenly across the chip. It ensures that the clock reaches all components at the right time, avoiding timing problems.
6. Routing (Global and Detailed)
a) Global Routing: This step creates rough routes or paths to connect the different cells.
b) Detailed Routing: After global routing, this step fine-tunes the connections, ensuring that the wires are correctly placed to make precise connections between the cells.

RTL2GDS OpenLANE ASIC Flow Practical implementation:
Day 1 Labs
Basic Linux Commands
### 1. `ls`  
   - a) Lists files and directories in the current directory.
   - b) If no arguments are provided, it will show the files and directories in the current location.

### 2. `pwd`
   - a) Stands for "Print Working Directory."
   - b) Displays the current directory you are in.

### 3. `mkdir`
   - a) Stands for "Make Directory."
   - b) Creates a new directory (folder) in the current location.

### 4. `ls -ltr`
   - a) `ls` lists files and directories.
   - b) `-l` shows detailed information (like permissions, owner, size, and date).
   - c) `-t` sorts by modification time (newest first).
   - d) `-r` reverses the order of the list (oldest first).

### 5. `help`
   - a) Displays a list of all available commands and their descriptions.
   - b) You can use it for basic command help in the terminal.

### 6. `man`
   - a) Stands for "Manual."
   - b) Provides detailed documentation for any command.
   - c) For example, `man ls` will show the manual for the `ls` command.

### 7. `cp`
   - a) Stands for "Copy."
   - b) Used to copy files or directories from one location to another.
   - c) Example: `cp file1.txt file2.txt` copies `file1.txt` to `file2.txt`.

### 8. `rm`
   - a) Stands for "Remove."
   - b) Deletes files or directories.
   - c) Example: `rm file1.txt` removes `file1.txt` from the directory.

Steps for running OpenLane inside a virtual machine:

### 1. **Go to Virtual Machine**
   a) **Start your virtual machine**: 
      - If your virtual machine (VM) is not already running, turn it on. This could be done by opening the VM software (like VirtualBox or VMware) and starting the VM that you have installed OpenLane on.

### 2. **Open the Command Line Terminal**
   a) **Press Ctrl + Alt + T**:
      - To open a terminal window inside the virtual machine, press the **Ctrl** key, **Alt** key, and the **T** key simultaneously. This will launch the terminal where you can type commands.

### 3. **Navigate to the OpenLane Directory**
   a) **Use the cd command**:
      - The `cd` command stands for "change directory." It allows you to move into the specific folder (directory) where OpenLane is located.
   b) **Move to the OpenLane folder**:
      - In this case, you are using the `cd` command to go to the OpenLane directory located on the Desktop. You would type the following command in the terminal:
        ```bash
        cd Desktop/work/tool/openlane_directory/openlane
        ```
      - This command changes your current location in the terminal to the OpenLane folder so that you can start working with OpenLane tools.
![1  navigate to openLane directory](https://github.com/user-attachments/assets/5118daa9-bf61-4b0d-b635-9cf2e7449b61)
Sure! Here's a simple, pointwise explanation of the steps you mentioned:

### 1. Start Docker:
   a) **Open your terminal or command line**: This is where you can type commands to interact with your computer. 
   
   b) **Type the command `docker`**: This command is used to check if Docker is running properly on your system. If Docker is working, it will show information about the Docker version and its features.

   Example command:
   ```bash
   docker
   ```

   If Docker is installed and running, you will see a list of available Docker commands and information.

---

### 2. Run OpenLane in Interactive Mode:
   a) **Type the command `./flow.tcl -interactive`**: This command is used to run OpenLane, which is a tool for digital design flow, in interactive mode. The `-interactive` flag allows you to use the tool step-by-step in an interactive manner, giving you more control over the process.

   Example command:
   ```bash
   ./flow.tcl -interactive
   ```

   When you run this, OpenLane will start and ask for your input at each step. This is useful for experimenting or for monitoring progress closely.

--- 

In summary:
1. **Check if Docker is running**: Run the `docker` command.
2. **Start OpenLane interactively**: Run `./flow.tcl -interactive` to use OpenLane in a controlled, step-by-step mode.
![2  rune openlane in interactive mode](https://github.com/user-attachments/assets/2ff68fbb-8dcf-46ba-bdaa-f7148dbae3ff)
The "Design Setup Stage" in the context of setting up a PICORV32A (a 32-bit RISC-V core) involves preparing the environment and tools required to begin the actual design and simulation. Here’s a simple pointwise breakdown:

1. **a) Tool Setup**  
   You need to install and configure the tools you will use for designing and testing the PICORV32A core.  
   - These tools could include simulators like ModelSim or Verilator, and design environments like Vivado, Xilinx ISE, or others.
   - Set up the toolchain to compile the Verilog code and run simulations or synthesis.

   **b) Create Project Directory**  
   A specific folder (or project directory) must be created where all files related to the PICORV32A design will be stored.  
   - Organizing all your files in one location makes the process smoother and more manageable.

2. **a) Download PICORV32A Source Code**  
   Download the PICORV32A code from a repository (e.g., GitHub).  
   - PICORV32A is typically open-source, so you'll need to fetch its Verilog code to start using it in your project.

   **b) Check Dependencies**  
   Ensure you have all the necessary libraries and dependencies to compile and simulate the PICORV32A design.  
   - This includes verifying you have the right version of RISC-V toolchains, libraries, and any additional components required by PICORV32A.

3. **a) Configure the Core**  
   PICORV32A has multiple configuration options (like caches, interrupt handling, etc.), and you need to adjust these settings based on your specific design requirements.  
   - For example, you may configure the size of the memory or enable/disable certain features based on your application.

   **b) Set Up Constraints**  
   Define the constraints for your design, such as clock speed, pin assignments, or target hardware (FPGA or ASIC).  
   - These constraints are essential to guide the design towards your specific hardware requirements.

4. **a) Simulation Setup**  
   Set up simulation scripts that will test the PICORV32A design after you've configured it.  
   - You’ll write testbenches or use existing ones to check the behavior of the core.

   **b) Verify the Setup**  
   Run an initial simple simulation to verify that your environment is properly set up and the code is compiling and simulating correctly.  
   - If everything works without errors, you are ready to move on to more detailed testing.

5. **a) Documentation**  
   Review and document the setup process, configuration changes, and any assumptions or special conditions for your design.  
   - Documentation is crucial for keeping track of the design setup and for future debugging or enhancements.

   **b) Version Control**  
   Use version control (like Git) to track changes in the code and design configuration.  
   - This helps in case you need to revert changes or collaborate with others.

This stage essentially ensures that all the tools, configurations, and setups are in place before moving on to actual coding or simulation of the PICORV32A core.
![3  design setup stage](https://github.com/user-attachments/assets/82a2d207-199d-48e8-91cb-481976540d46)
The `run_synthesis` command is used in hardware design, specifically in tools like Vivado or Quartus, to convert a high-level description of a design (usually in a Hardware Description Language like Verilog or VHDL) into a gate-level representation. This process is crucial for turning your design into something that can be physically implemented in hardware (e.g., on an FPGA or ASIC). Below is a pointwise explanation of the synthesis process:

### 1. **Synthesis Overview**
   a) **Converts RTL to Gate-Level**: RTL (Register Transfer Level) code (like Verilog/VHDL) is converted into a netlist of logic gates (AND, OR, NOT, etc.).  
   b) **Optimization**: During this process, the synthesizer tries to optimize your design for factors like speed, area (how much space it will take), and power consumption.

### 2. **Input Files**
   a) **HDL Code**: The design’s source code (in Verilog/VHDL) is provided as input.  
   b) **Constraints**: These include timing, area, and input/output specifications that guide how the design should be synthesized.

### 3. **Logic Mapping**
   a) **High-Level Functions to Gates**: The synthesizer maps high-level constructs (like `if`, `case`, `assign`) into lower-level logic gates.  
   b) **Optimization of Gates**: It optimizes the logic to use fewer gates or reduce the critical path to meet timing requirements.

### 4. **Optimization**
   a) **Area Optimization**: It tries to minimize the number of logic gates, reducing the area taken by the design on the chip.  
   b) **Speed Optimization**: It attempts to arrange the logic to minimize delays in signal propagation, which speeds up the design.  
   c) **Power Optimization**: Reduces the power consumed by the logic gates.

### 5. **Clock Handling**
   a) **Clock Constraints**: The synthesizer ensures that clock constraints (timing of signals) are met in the design.  
   b) **Clock Gating**: It can add clock gating to reduce power usage by turning off parts of the design when not in use.

### 6. **Reports**
   a) **Synthesis Report**: After synthesis, the tool generates a report that shows the gate-level summary of the design, including the number of gates, timing information, and any potential errors or warnings.  
   b) **Area and Timing Analysis**: Provides insights into how well the design meets area and timing requirements.

### 7. **Post-Synthesis**
   a) **Netlist Generation**: After synthesis, a netlist (a list of gates and their connections) is created. This is then used for further steps like place and route.  
   b) **Verification**: Ensures the synthesized design behaves as expected, often by comparing the gate-level implementation with the original RTL code.

### 8. **Tools Used**
   a) **Vivado/Quartus/ISE**: These are common synthesis tools used in FPGA/ASIC design. They automate much of the process.  
   b) **Static Timing Analysis**: Some tools automatically perform timing analysis during synthesis to check if the design will work at the required clock speed.

In simple terms, `run_synthesis` translates your code (which tells the hardware what to do) into a structure of gates that can actually be implemented in real hardware. It also checks for errors and tries to make your design faster, smaller, and more power-efficient.
![4  run_synthesis](https://github.com/user-attachments/assets/bd940fa7-6bba-4793-8345-601cc7b10387)
**Flop Ratio Explanation (Pointwise)**

1. **What is Flop Ratio?**
   a) Flop Ratio refers to the ratio of the number of flip-flops (or latches) in a circuit compared to the number of logic gates used.
   b) Flip-flops are used to store data or maintain state in digital circuits, while logic gates are used to perform operations like AND, OR, etc.

2. **Importance of Flop Ratio**
   a) It helps in assessing the efficiency of a digital circuit design.
   b) A higher flop ratio might indicate that the circuit is more state-driven (involving more memory elements), whereas a lower flop ratio suggests a more combinational (logic-based) circuit.

3. **How is Flop Ratio Calculated?**
   a) Flop Ratio is calculated by dividing the total number of flip-flops in a design by the total number of logic gates used.
   b) The formula is:  
      **Flop Ratio = (Number of Flip-Flops) / (Number of Logic Gates)**

4. **Significance in Design**
   a) A high flop ratio means more memory elements are being used, which could lead to more complex design and slower performance due to increased delays in storing and accessing data.
   b) A lower flop ratio generally indicates that the circuit is optimized for faster computation but might not be suitable for applications needing lots of state storage.

5. **Practical Use**
   a) In VLSI (Very Large Scale Integration) design, the flop ratio helps in deciding the balance between logic operations and memory storage, influencing factors like speed, power consumption, and area.
   b) Designers aim for a balance in the flop ratio based on the intended application, whether it is for high-speed computing, storage, or signal processing.

In summary, the flop ratio provides insights into the structure of a digital circuit, helping to optimize performance and efficiency based on the needs of the application.

DAY2_Good floorplan vs bad floorplan and introduction to library cells:
### 1. **Aspect Ratio (Ar)**:
   a) **Definition**: The aspect ratio of a layout is the ratio of its height to its width.  
   b) **Formula**:  
     Aspect Ratio (Ar)= Width/Height
   c) **Interpretation**:  
      - If the aspect ratio is **1**, the height and width are the same, making the core **square**.
      - If the aspect ratio is greater than 1, the core is wider than it is tall, and if it's less than 1, the core is taller than it is wide.

### 2. **Utilization Factor**:
   a) **Definition**: The utilization factor measures how much of the total available area is used by logic elements or standard cells in a design.
   b) **Formula**:  
     Utilization Factor= Area occupied by standard cells/Total available area in the block or chip

​   c) **Interpretation**:  
      - If the utilization factor is **0.5** (50%), it means that half of the chip or design block area is used for placing cells, while the other 50% is available for routing (connecting the cells).

### 3. **Tap Cell**:
   a) **Definition**: A tap cell (or well tap cell) is a special cell used in integrated circuit (IC) designs to maintain proper connection between the power/ground network and the silicon substrate, ensuring correct biasing.
   b) **Purpose**:  
      - Tap cells prevent **latch-up**, a condition where unwanted connections form between the power and ground rails due to parasitic structures, causing the circuit to malfunction.
   c) **How it works**:  
      - Tap cells connect the **n-wells** and **p-wells** to the appropriate power/ground (VDD or GND), ensuring that the wells are correctly biased, preventing latch-up.

### 4. **Priority Order for Floorplan in OpenLane**:
   a) **PDK File (Process Design Kit)**:  
      - This file contains the process-specific design rules and information needed for the design process. It is the **first priority** for defining how designs should be laid out according to the manufacturing process.
   b) **Design File (config.tcl)**:  
      - The design configuration file (typically a `.tcl` file) specifies the design parameters and constraints, such as chip dimensions and the desired configuration of cells and blocks. This file is the **second priority** for the floorplan.
   c) **System Default (floorplan.tcl)**:  
      - This is a **default file** used by the system to set up the basic floorplan configuration if no specific configurations are provided by the user. It is used as a fallback and is the **third priority**.

Each of these steps ensures that the design follows the right process and is optimized for functionality and manufacturability.


LAB2 :
Screenshot of run_floorplan : 
Step performed : 
    1. cd Desktop/work/tools/openlane_working_dir/openlane

    2.    docker
    3.    ./flow.tcl -interactive 
    4.    prep -design picorv32a
    5.    run_synthesis
    6.    run_floorplan
    
    ![1  run_floorplan](https://github.com/user-attachments/assets/68f1e0d5-3c90-4826-ab54-cc2a9b7635a3)
   ![2  run floorplan](https://github.com/user-attachments/assets/da859c5c-e784-4039-b83a-8fb5b8241866)



### **1. Command Overview**
- **Magic**: A layout editor and VLSI design tool used for creating and verifying chip layouts.
- The command is used to load the necessary files (technology, LEF, DEF) into Magic for visualization or editing.

---

### **2. Command Breakdown**
#### **2.1. `magic -T ...`**
- **a)** `magic`: Starts the Magic tool.
- **b)** `-T /home/vsduser/.../sky130A.tech`: Specifies the path to the **technology file** (`sky130A.tech`) for the Sky130A process.  
  - **Technology file**: Contains information about layers, design rules, and other process-specific details.

#### **2.2. `lef read ../../tmp/merged.lef`**
- **a)** `lef read`: Reads a **LEF file** into Magic.
- **b)** `../../tmp/merged.lef`: Path to the LEF file that describes the standard cell library, including the physical and logical layout of cells.

#### **2.3. `def read picorv32a.floorplan.def`**
- **a)** `def read`: Reads a **DEF file** into Magic.
- **b)** `picorv32a.floorplan.def`: The DEF file describes the **floorplan** or placement of cells in the design (`picorv32a` in this case).

#### **2.4. `&`**
- Runs the command in the background, allowing the terminal to remain available for other tasks.

---

### **3. Purpose of the Command**
- **a)** Load the Sky130A technology rules (`sky130A.tech`) into Magic.
- **b)** Import standard cell definitions from the LEF file (`merged.lef`).
- **c)** Load the floorplan details from the DEF file (`picorv32a.floorplan.def`) for viewing or editing in Magic.

---

### **4. Why Use This Command?**
- To **visualize and verify** the floorplan of a design (`picorv32a`) using Magic.
- To ensure the design adheres to the process technology rules (Sky130A).

![3  magic -t](https://github.com/user-attachments/assets/f20f3376-1c82-49d9-8834-65a5b2fdeb4f)

### 1. Align the design to the middle of the screen  
**a)** Press **S** on your keyboard to select the entire design.  
**b)** Then press **V** to align the design to the center of the screen.

### 2. Zoom to a particular area  
**a)** Use your **left mouse button** to click and select the area you want to zoom into.  
**b)** Right-click and press **Z** on your keyboard to zoom in on the selected area.

### 3. View details of a cell  
**a)** Move your mouse cursor over the cell you want to check and press **S** to select it.  
**b)** Open the **tkcon window** and type the command `what`.  
**c)** The details of the selected cell will appear in the **tkcon window**.
![4  what](https://github.com/user-attachments/assets/88a93eff-f1e4-45ee-a683-3cc7ad29f15e)

Here's the explanation of **Placement in Physical Design** pointwise and in simple terms:

---

### **1. Placement Overview:**
   a) **What is Placement?**  
   Placement is a step in VLSI design where the synthesized netlist (logic gates and connections) is converted into a physical layout.  
   b) **Why is Placement important?**  
   The goal is to arrange standard cells (logic gates) on the chip to optimize **timing, power, and area**.  
   c) **Key objectives of Placement:**  
      - Minimize wirelength (short connections between cells).  
      - Ensure proper signal timing.  
      - Follow design rules for manufacturability.

---

### **2. Types of Placement:**

#### **a) Global Placement:**
   i) **What happens in Global Placement?**  
   Cells are roughly positioned inside the chip’s core area for the first time.  
   ii) **Key Characteristics:**  
      - **Cell Overlap Allowed:** Cells can overlap; this is not a final placement.  
      - **Design Rules Ignored:** Detailed rules like spacing or overlap are not enforced yet.  
      - **Goal:** Create a rough placement considering timing and congestion, giving a global view of the design.  
   iii) **Purpose:** Helps identify congestion and gives an overall idea of the layout.  

---

#### **b) Detailed Placement:**
   i) **What happens in Detailed Placement?**  
   Fine-tuning of cell positions to remove overlaps and align cells to a grid.  
   ii) **Key Characteristics:**  
      - **Cell Overlap Eliminated:** Ensures no cells overlap.  
      - **Design Rules Enforced:** Spacing and DRCs (Design Rule Checks) are strictly followed.  
      - **Precise Alignment:** Cells are placed exactly on a placement grid.  
   iii) **Purpose:** Prepares the design for the next step (Routing).  

---

### **3. Placement Commands:**

#### a) **Command for Running Placement:**  
   - `run_placement`  
   This command executes both **Global Placement** and **Detailed Placement**.  

#### b) **Output of the Command:**  
   i) Cells are positioned inside the chip’s floorplan.  
   ii) No overlaps between cells.  
   iii) Design rule violations (like spacing issues) are resolved.
![5  placement](https://github.com/user-attachments/assets/095b9146-bafc-43c0-be8e-d9c28c5c5d1a)
![6  placement](https://github.com/user-attachments/assets/f712c9b3-a720-4b16-80c9-11ce383c72e6)
![7  placement 2](https://github.com/user-attachments/assets/cfce374a-0e98-493c-876e-023a5d5424c5)

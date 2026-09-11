# Logic Design – Classroom Capacity Counter

A digital logic design project implementing a **5-bit synchronous up/down counter** for classroom capacity management.

## Project Overview

The circuit tracks the number of students in a classroom from **0 to 29**. It supports:

- Synchronous counting up when students enter
- Synchronous counting down when students exit
- Saturation at 0 and 29
- Reset functionality
- Lock functionality
- Two 7-segment displays showing the classroom capacity
- A 10-second countdown timer
- A third 7-segment display indicating whether the classroom is **Open (O)** or **Locked (L)**

The design was developed using logic gates, flip-flops, adders, counters, and 7-segment display decoders, then simulated and implemented as a digital circuit.

## Main Components

### 1. 5-bit Synchronous Up/Down Counter

The counter represents the number of students using five state bits:

`Q4 Q3 Q2 Q1 Q0`

The valid range is:

`0 ≤ students ≤ 29`

The counter remains at 0 when an exit is requested at an empty classroom and remains at 29 when an entry is requested at full capacity.

The counter uses JK flip-flops with J and K connected, making them equivalent to T flip-flops.

### 2. Student Capacity Display

Two 7-segment displays show the current number of students.

The circuit divides the counter values into three ranges:

- 0–9
- 10–19
- 20–29

A 74LS83 4-bit adder is used to convert the binary counter value into the appropriate BCD value for the unit display.

### 3. Timer

A 74LS193 4-bit up/down synchronous counter is used as a countdown timer.

The timer:

- Starts at 10
- Counts down to 0
- Stops at 0
- Resets to 10 when the system is reset

### 4. Lock / Open Display

A third 7-segment display indicates the classroom state:

- `O` — Open
- `L` — Locked

The lock condition is associated with:

- Classroom capacity reaching 29
- Timer reaching 0
- The instructor activating the lock switch

## Control Priority

The circuit implements the following priority:

1. Reset
2. Lock
3. Enter / Exit

Enter and Exit are prevented from being active simultaneously.

## Technologies / Components

- Digital logic gates
- JK flip-flops
- T flip-flop logic
- 74LS83 4-bit adder
- 74LS193 4-bit counter
- 7-segment displays
- BCD / 7-segment decoding
- Quartus simulation
- Breadboard implementation

## Repository Structure

```text
logic-design-class-capacity-counter/
├── README.md
├── documentation/
│   └── Logic_Project.docx
├── quartus/
│   └── [Quartus project files]
├── schematics/
│   └── [Circuit schematics]
└── simulations/
    └── [Simulation files / waveforms]
```

## Authors

- Jean Paul Zammar
- Hadi Jouni

## Course

**COE 322 – Logic Design Lab**

Lebanese American University (LAU)

## Future Updates

The Quartus project files, schematics, and simulation files can be added to the corresponding folders when available.

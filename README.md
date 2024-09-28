# Traffic Light Control System Project

## Project Title:
**Study, Design, and Programming of a Traffic Light Control System**

## Objective:
The objective of this project is to design and implement an electronic system that controls traffic lights at an intersection. The goal is to acquire, visualize, and control the lights using the LABVIEW environment.

## Project Specifications:
- **Two Identical Lanes (A and B):** The system controls traffic lights for two identical lanes. The duration of each light state (Red, Yellow, Green) is the same for both lanes.
- **Time Cycle:** The system operates on a 16-unit time cycle:
    - **Green Light (VA, VB):** 5 units of time
    - **Red Light (RA, RB):** 5 units of time
    - **Yellow Light (JA, JB):** 2 units of time
- **Safety Mechanism:** For safety reasons, when a light turns green, there must be a preceding period where both lanes' lights are simultaneously red for 1 unit of time.
- **Time Breakdown (5 2 1 5 2 1 cycle):** The light cycles for each lane are as follows:
    - **Lane A:** Green for 5 units, then Red for 5 units.
    - **Lane B:** Red for 5 units, then Green for 5 units.

## System Requirements:
- **Control System:** The system must include the following controls:
    1. **"INi" Command:** Initializes the system with Lane A (VA) green and Lane B (RB) red.
    2. **"URG" Command:** Forces the system into a state where both lanes are red (RA, RB) in case of an emergency.
    3. **"JC" Command:** Switches both traffic lights to blinking yellow mode (controlled by an HC: Blinking Clock).

## Hardware Setup:
- **Components:**
    1. **6 Traffic Lights:** Three lights for each lane (A and B), consisting of:
        - Red LED
        - Yellow LED
        - Green LED
    2. **Interface Circuit:** Velleman K8055 board compatible with LABVIEW.
    3. **LED Resistors:** 268 Ohms resistors for each LED.

- **Wiring Setup:**
    - One end of each LED is connected to the digital outputs (2-7) of the K8055 board.
    - Outputs 2-7 correspond to Red, Yellow, and Green LEDs for both lanes.
    - When a digital output is activated, the circuit closes, allowing current to pass through the LED, turning it on.
    - The other end of each LED is connected to the Clamp.
    - The **+Vs** of the generator is connected to the Clamp (pin 9).
    - The **-GND** of the generator is connected to the ground of the K8055 board.

## K8055 Board Configuration:
- The board has different address configurations based on the settings of SK5 and SK6.
- In our case, both SK5 and SK6 are left free, corresponding to **address 3**.

| SK5  | SK6  | Address |
|------|------|---------|
| ON   | ON   | 0       |
| OFF  | ON   | 1       |
| ON   | OFF  | 2       |
| OFF  | OFF  | 3       |

## Software Requirements:
- **LABVIEW:** To control the traffic light system using the Velleman K8055 interface.

## Circuit Overview:
- The LEDs are connected in such a way that the K8055 board's digital outputs control their activation.
- When a digital output (e.g., output 2) is turned on, the corresponding LED (e.g., red LED) lights up.
- The system continuously cycles between red, yellow, and green lights for each lane according to the specified timing rules.

## Commands:
- **INi:** Initializes the system to start with Lane A green and Lane B red.
- **URG:** Forces both lanes to red in case of emergency.
- **JC:** Activates blinking yellow mode for both lanes.

## Required Equipment:
1. **Velleman K8055 Interface Board**
2. **6 LEDs (2 Red, 2 Yellow, 2 Green)**
3. **Resistors (268 Ohms)**
4. **Power Supply**
5. **LABVIEW Software**

## Conclusion:
This system simulates the control of traffic lights at a standard intersection using the LABVIEW environment. The configuration ensures safe transitions between lights, with features for initialization, emergency stop, and blinking yellow mode for caution. The K8055 board serves as the interface between the software and hardware, providing real-time control of the traffic lights.

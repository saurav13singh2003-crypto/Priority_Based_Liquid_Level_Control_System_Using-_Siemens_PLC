# Priority-Based Liquid Level Control System Using Siemens PLC

## Project Overview

This project implements an automated liquid level control system for three storage tanks (Tank A, Tank B, and Tank C) using a Siemens PLC and Ladder Logic programming in TIA Portal. The system controls the filling process based on predefined tank priorities and liquid level thresholds. Tank A has the highest priority, followed by Tank B and Tank C.

The main objective is to automate liquid distribution, coordinate pump and valve operations, and provide visual indicators for tank filling and full-level conditions.

## Objectives

- Automate the filling of three storage tanks using PLC programming.
- Implement priority-based control to manage tank filling operations.
- Control pump and solenoid valve operations using Ladder Logic.
- Monitor liquid levels using predefined thresholds.
- Provide indicators for filling and full-tank conditions.
- Use start/stop controls to operate the system.

## Technologies Used

- **PLC:** Siemens S7-1200 (CPU 1211C)
- **Programming Software:** Siemens TIA Portal
- **Programming Language:** Ladder Logic (LAD)
- **Control Concepts:** Priority Logic, Timers, Memory Bits, Comparison Instructions
- **Application:** Industrial Automation and Process Control

## System Components

| Component | Function |
|---|---|
| Siemens PLC | Executes the control logic |
| Start/Stop Push Buttons | Start and stop the system |
| Tank A, Tank B, Tank C | Store the liquid |
| Valves A, B, C | Control liquid flow into each tank |
| Pump | Supplies liquid to the tanks |
| Level Values | Represent the measured liquid levels |
| Fill Indicators | Indicate when a tank requires filling |
| Full Indicators | Indicate when a tank reaches its full-level threshold |
| TON Timer | Delays pump activation by 3 seconds |

## Working Principle

### 1. System Start and Stop
The Start push button activates the system using a latching memory bit. The system remains active after the button is released. Pressing the Stop push button deactivates the system.

### 2. Priority-Based Tank Filling
The system uses predefined liquid level thresholds to control the tank valves:

| Tank | Priority | Filling Threshold | Full-Level Threshold |
|---|---:|---:|---:|
| Tank A | 1 (Highest) | 15 | 50 |
| Tank B | 2 | 25 | 75 |
| Tank C | 3 | 35 | 85 |

The PLC evaluates the tank level values and operates the valves according to the programmed priority conditions. The control logic uses valve status and level comparisons to coordinate the filling sequence.

### 3. Pump Control
A TON (on-delay) timer introduces a 3-second delay before activating the pump when a tank valve is open and the system is running. This helps coordinate pump operation with the valve control sequence.

### 4. Tank Status Indicators
Each tank has two indicators:
- **Fill Indicator:** Activates when the measured level is at or below the configured filling threshold.
- **Full Indicator:** Activates when the measured level equals the configured full-level threshold.

### 5. PLC Programming Structure
The main program is organized into Ladder Logic networks for:
1. System Start/Stop
2. Tank A Priority Control
3. Tank B Priority Control
4. Tank C Priority Control
5. Pump Timer and Control
6. Tank A Status Indicators
7. Tank B Status Indicators
8. Tank C Status Indicators

## Key Features

- Automated control of three liquid storage tanks.
- Priority-based valve control logic.
- Configurable liquid level thresholds.
- Three-second pump activation delay.
- Start/stop control with a latching memory bit.
- Individual fill and full status indicators for each tank.
- Structured Ladder Logic programming.

## Learning Outcomes

- Gained practical experience with Siemens S7-1200 PLC programming.
- Learned to develop Ladder Logic using TIA Portal.
- Understood PLC memory bits, memory words, and output addressing.
- Applied comparison instructions and on-delay timers.
- Developed an understanding of priority-based process automation.

## Conclusion

This project demonstrates how a Siemens PLC can automate a multi-tank liquid filling process using priority-based control logic. It combines level comparisons, valve sequencing, delayed pump activation, and status indicators to demonstrate the fundamentals of industrial automation and process control.


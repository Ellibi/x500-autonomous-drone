# dexi5-autonomous-drone
# DEXI 5 Autonomous Drone Project

Autonomous quadcopter development project utilizing PX4 Autopilot, Gazebo simulation, QGroundControl, and an onboard companion computer architecture.

---

## Project Overview
This repository serves as the central workspace for the development, simulation, hardware procurement, and deployment of the autonomous DEXI 5 quadcopter.

The development workflow validates system dynamics, communications, and autonomous behavior in simulation before transitioning to laboratory assembly and flight testing.

---

## System Architecture

### 1. Two-Tier Brain System
* **Low-Level Control (Flight Controller - Pixhawk 6C):**
  * Runs PX4 Autopilot firmware.
  * Manages real-time sensor fusion (IMU, barometer, magnetometer, GPS) and high-rate PID stabilization loops.
* **High-Level Processing (Companion Computer - Raspberry Pi):**
  * Runs Linux for high-level mission logic, vision processing, and AI tasks.
  * Communicates with the Pixhawk via MAVLink over serial UART/USB.
  * Directs vehicle navigation using PX4 Offboard Mode.

---

## Roadmap & Phases
* **Phase 1: Simulation & Digital Setup:** Set up toolchain (WSL2, Gazebo, QGroundControl), test flight modes, and configure mission parameters.
* **Phase 2: Hardware Assembly:** Procure components from the Bill of Materials and assemble the DEXI 5 frame, motors, ESC, and flight controller.
* **Phase 3: Companion Computer & Autonomy:** Mount Raspberry Pi, configure serial telemetry communication, and integrate camera/AI workloads.
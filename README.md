# Autonomous X500 Quadcopter Project

Autonomous quadcopter development project utilizing PX4 Autopilot, Gazebo simulation, QGroundControl, and an onboard companion computer architecture.

---

## Project Overview
This repository serves as the central workspace for the development, simulation, hardware procurement, and physical deployment of an autonomous quadcopter based on the Holybro X500 V2 platform.

The development workflow validates flight dynamics, communications, and autonomous behavior using PX4 SITL and Gazebo simulation before deploying software to physical hardware for laboratory flight testing.

---

## System Architecture

### Two-Tier Brain Architecture
* **Low-Level Control (Flight Controller - Pixhawk 6C / 6X):**
  * Runs PX4 Autopilot firmware.
  * Manages real-time sensor fusion (IMU, barometer, magnetometer, GPS) and high-rate PID attitude/position control loops.
* **High-Level Processing (Companion Computer - Raspberry Pi 4 / 5):**
  * Runs Linux for mission logic, path planning, and vision processing.
  * Communicates with the Pixhawk via MAVLink over serial UART (TELEM2).
  * Commands vehicle trajectories using PX4 Offboard Mode (via MAVSDK / pymavlink).

---

## Hardware Baseline (Holybro X500 V2)
* **Frame:** Holybro X500 V2 carbon fiber quadcopter (500 mm wheelbase)
* **Propulsion:** Holybro 2216 920KV brushless motors with 1045 propellers
* **Power:** 4S LiPo battery (4000–5000 mAh) with PM02/PM03 Power Module
* **Navigation & Sensors:** Holybro M9N/M10 GNSS + Compass module, internal multi-redundant IMUs
* **Perception Payloads (Targeted):** Intel RealSense depth sensor and downward LiDAR rangefinder

---

## Roadmap & Phases
* **Phase 1: Simulation & Software Testbench:** Configure the simulation toolchain (WSL2, Gazebo, QGroundControl), test standard and sensor-equipped `x500` models, and develop offboard flight scripts.
* **Phase 2: Hardware Assembly & Bench Testing:** Procure components, assemble the X500 V2 frame and propulsion kit, configure Pixhawk power management, and perform motor calibration.
* **Phase 3: Companion Computer Integration:** Mount the Raspberry Pi, establish serial telemetry routing, and validate autonomous offboard routines in real-world test flights.

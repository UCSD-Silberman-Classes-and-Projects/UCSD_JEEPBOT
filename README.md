# <div align="center">Jeep Bot</div>
### <div align="center">Triton AI and Dr. Jack Silberman's Lab Group</div>
#### <div align="center">UC San Diego Jacobs School of Engineering and Halıcıoğlu Data Science Institute</div>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-control%20scripts-3776AB?style=flat-square&logo=python&logoColor=white">
  <img alt="Raspberry Pi" src="https://img.shields.io/badge/Raspberry%20Pi-onboard%20compute-A22846?style=flat-square&logo=raspberrypi&logoColor=white">
  <img alt="Arduino" src="https://img.shields.io/badge/Arduino-Leonardo%20HID-00878F?style=flat-square&logo=arduino&logoColor=white">
  <img alt="PlatformIO" src="https://img.shields.io/badge/PlatformIO-firmware%20build-F5822A?style=flat-square&logo=platformio&logoColor=white">
  <img alt="ExpressLRS" src="https://img.shields.io/badge/ExpressLRS-radio%20control-111111?style=flat-square">
  <img alt="VESC" src="https://img.shields.io/badge/VESC-motor%20control-2E7D32?style=flat-square">
  <img alt="DonkeyCar" src="https://img.shields.io/badge/DonkeyCar-joystick%20integration-7B3FE4?style=flat-square">
  <img alt="DepthAI OAK-D" src="https://img.shields.io/badge/DepthAI%20OAK--D-perception-00A3E0?style=flat-square">
</p>

Master repository for the UC San Diego JeepBot project: a Power Wheels Jeep converted into a modular robotics platform for autonomous vehicle development, hardware integration, embedded control, and repeatable student research.

This repository is intentionally organized as a submodule-based workspace. The top-level repository provides the project overview, integration map, and contributor workflow, while the implementation, documentation, firmware, and setup assets remain in their dedicated component repositories.

## Abstract

JeepBot is a full-scale robotics platform developed for experimentation in vehicle actuation, embedded systems, perception, and autonomous navigation. The platform combines onboard compute, VESC-based motor control, steering and drive interfaces, camera and sensor integration, and manual-control workflows that support safe development before autonomous operation.

The project is designed to be modular and reproducible. Each subsystem is maintained in a focused repository and brought together here as a master workspace so future contributors can understand the full system, update individual components, and reproduce the current JeepBot stack.

- **Organization**: Triton AI
- **Team Members**: Evan Chou, Erik, Sophia Davila, Helena, Kaung Khant, Chris Martin
- **Faculty Sponsors**: Dr. Jack Silberman

## Project Goals

- Convert a ride-on Jeep platform into a maintainable robotics testbed.
- Support manual, assisted, and autonomous vehicle-control workflows.
- Provide repeatable setup documentation for future teams.
- Separate hardware documentation, firmware, setup scripts, and integration code into maintainable modules.
- Preserve iteration history across electrical, mechanical, embedded, and software design decisions.

## Repository Structure

```text
UCSD_JEEPBOT/
├── .gitmodules
├── README.md
├── software/
│   ├── README.md
│   ├── JeepBot-SetUp/
│   ├── JeepBot-ELRS-Controller/
│   ├── TritonAI_Jeepbot_Current_Directory/
│   ├── ros2-docker/               # planned
│   └── donkeycar-stack/           # planned
└── hardware/
    ├── README.md
    ├── JeepBot-Docs/
    └── 148-jeepbot-team-01/
```

## Submodules

GitHub displays each committed submodule path as a folder-like link to the exact submodule commit. The folder indexes in [`software/`](./software) and [`hardware/`](./hardware) also provide direct links to each upstream repository.

| Submodule | Purpose | Upstream |
| --- | --- | --- |
| [`software/JeepBot-SetUp`](./software/JeepBot-SetUp) | Setup and control scripts for F710 / VESC steering and drive testing. | <https://github.com/KennethKhant/JeepBot-SetUp.git> |
| [`software/JeepBot-ELRS-Controller`](./software/JeepBot-ELRS-Controller) | ExpressLRS-to-USB-HID controller firmware and DonkeyCar joystick integration. | <https://github.com/KennethKhant/JeepBot-ELRS-Controller.git> |
| [`software/TritonAI_Jeepbot_Current_Directory`](./software/TritonAI_Jeepbot_Current_Directory) | Current proof-of-concept, DonkeyCar, and YOLO demo workspace. | <https://github.com/esha0281/TritonAI_Jeepbot_Current_Directory.git> |
| [`hardware/JeepBot-Docs`](./hardware/JeepBot-Docs) | Static setup guide for VESC, encoder, F710 controller, and Raspberry Pi workflows. | <https://github.com/KennethKhant/JeepBot-Docs.git> |
| [`hardware/148-jeepbot-team-01`](./hardware/148-jeepbot-team-01) | Main team repository containing JeepBot hardware documentation, system architecture, CAD/docs/source organization, and project history. | <https://github.com/Triton-AI/148-jeepbot-team-01.git> |

## Planned Submodules

| Path | Intended purpose | Status |
| --- | --- | --- |
| `software/ros2-docker/` | ROS 2 development container and runtime environment for autonomy work. | Planned |
| `software/donkeycar-stack/` | DonkeyCar project workspace and vehicle configuration. | Planned |

## System Overview

JeepBot brings together four major development areas:

1. Vehicle platform and hardware integration
   - Power Wheels Jeep base
   - VESC motor controllers
   - Steering and drive actuation
   - Electrical mounting, wiring, and safety architecture

2. Embedded and remote-control interfaces
   - ExpressLRS radio controller
   - Radio receiver integration
   - Arduino Leonardo USB-HID joystick bridge
   - Logitech F710 controller setup for test workflows

3. Onboard compute and software stack
   - Raspberry Pi-based control environment
   - Python setup and hardware test scripts
   - DonkeyCar-compatible joystick interface
   - Future autonomous-control integration points

4. Perception and autonomy
   - OAK-D camera integration
   - LiDAR / sensor expansion
   - Computer-vision and navigation experiments
   - Future closed-loop autonomous driving workflows

## Quick Start

Clone the master repository with all submodules:

```bash
git clone --recurse-submodules <master-repo-url>
cd UCSD_JEEPBOT
```

If the repository was cloned without submodules:

```bash
git submodule update --init --recursive
```

To pull updates from the master repository and refresh submodules:

```bash
git pull
git submodule update --init --recursive
```

To update each submodule to its latest upstream branch:

```bash
git submodule update --remote --merge
```

## Recommended Reading Order

1. Start with [`hardware/148-jeepbot-team-01/README.md`](./hardware/148-jeepbot-team-01/README.md) for the high-level project background, hardware revisions, and system architecture.
2. Review [`hardware/JeepBot-Docs/index.html`](./hardware/JeepBot-Docs/index.html) for the setup guide covering VESC, encoder, controller, and Raspberry Pi steps.
3. Use [`software/JeepBot-SetUp/README.md`](./software/JeepBot-SetUp/README.md) when running steering and drive scripts against the physical platform.
4. Use [`software/JeepBot-ELRS-Controller/README.md`](./software/JeepBot-ELRS-Controller/README.md) when working on ExpressLRS controller firmware or joystick integration.

## Development Workflow

Because this is a submodule workspace, most code and documentation changes should be made inside the relevant submodule repository.

Typical workflow:

```bash
cd software/<component-repo>
# or
cd hardware/<component-repo>
git checkout <branch-name>
# make changes
git add .
git commit -m "Describe component change"
git push

cd ../..
git add software/<component-repo>
# or
git add hardware/<component-repo>
git commit -m "Update <component-repo> submodule pointer"
git push
```

Use the top-level repository for:

- Project overview and abstract
- Submodule coordination
- Integration notes
- Release snapshots
- Cross-subsystem documentation

Use individual submodules for:

- Firmware changes
- Setup scripts
- Hardware documentation
- CAD and media assets
- Detailed subsystem documentation

## Safety Notes

JeepBot includes moving mechanical systems, high-current motor controllers, batteries, and software-controlled actuation. Before running any control script or firmware against the physical vehicle:

- Verify the vehicle is lifted, restrained, or in a safe test area.
- Confirm VESC current limits and position-control settings.
- Confirm controller deadman behavior before applying drive power.
- Keep a physical power disconnect available.
- Test steering and drive separately before combined operation.
- Use conservative speed, duty-cycle, and steering limits during early tests.

## Acknowledgments

JeepBot was developed through UC San Diego robotics coursework (ECE/MAE 148 and ECE 191) and student project work, with contributions across mechanical design, electrical integration, embedded systems, controls, and documentation.

Special thank you to Dr. Silberman for advising the project and mentoring the group!

## Contacts

* Dr. Jack Silberman - jasilberman@ucsd.edu
* Evan Chou - e3chou@ucsd.edu

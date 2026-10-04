# JeepBot Software

Software-facing submodules for JeepBot control, firmware, autonomy, and runtime environments.

| Component | Local path | Upstream repository | Purpose |
| --- | --- | --- | --- |
| JeepBot setup scripts | [`JeepBot-SetUp`](./JeepBot-SetUp) | <https://github.com/KennethKhant/JeepBot-SetUp> | Python setup and control scripts for Logitech F710, VESC steering, and drive testing. |
| ELRS controller firmware | [`JeepBot-ELRS-Controller`](./JeepBot-ELRS-Controller) | <https://github.com/KennethKhant/JeepBot-ELRS-Controller> | ExpressLRS receiver to Arduino Leonardo USB-HID joystick firmware and DonkeyCar joystick integration. |
| ROS 2 Docker stack | `ros2-docker/` | `[add repository link]` | Planned ROS 2 development container and autonomy runtime workspace. |
| DonkeyCar stack | `donkeycar-stack/` | `[add repository link]` | Planned DonkeyCar project workspace and vehicle configuration. |

Most implementation changes should be made inside the relevant submodule repository, then the master repo should be updated to point at the new submodule commit.


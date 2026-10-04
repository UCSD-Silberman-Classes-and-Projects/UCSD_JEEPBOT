# JeepBot Hardware

Hardware-facing submodules for JeepBot platform documentation, setup guides, electrical architecture, mechanical references, and system integration history.

| Component | Local path | Upstream repository | Purpose |
| --- | --- | --- | --- |
| JeepBot documentation site | [`JeepBot-Docs`](./JeepBot-Docs) | <https://github.com/KennethKhant/JeepBot-Docs> | Static setup guide for VESC, encoder, F710 controller, and Raspberry Pi workflows. |
| Team hardware repository | [`148-jeepbot-team-01`](./148-jeepbot-team-01) | <https://github.com/Triton-AI/148-jeepbot-team-01> | Main hardware and project-history repository with CAD, documentation, architecture notes, and system references. |

Most hardware documentation, CAD, media, and setup changes should be made inside the relevant submodule repository, then the master repo should be updated to point at the new submodule commit.


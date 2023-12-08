# Amiga2000DualConfig
Amiga 2000 Coprocessor Board to support 2 selectable CPUs, 2 selectable kickstart ROMs (+ 2x A/B configuration options) at boot or reset.

The **DualConfig** project was born out of an observation: some programs, games or demos don't work with all 680x0 processor models or all kickstart versions.

This project allows you to run the Amiga 2000 in legacy mode (68000 & Kickstart1.3) or with the legacy CPU and a more recent kickstart (68000 & Kickstart 3.x) or with a TerribleFire-type card (68030 & Kickstart3.x) for instance. It also provides two additional controls, one can be used to control a DF0 selector for instance. 

There is no need to power-off the Amiga to change the configuration. It can be changed anytime while the Amiga is powered-on. It will be taken in account on the next reset. Each of the 4 configuration parameters (CPU, Kickstart, param3, param4) can be selected using a latched SPST Off-On switch, with optional illumination.

The solution consists of two PCBs:

1. A "DualCpuAdapter" card that fits into the coprocessor slot. It is inspired by the [Open Amiga 2000 Copro Adapter](https://github.com/SukkoPera/OpenAmiga2000CoproAdapter) project. It allows:

   a) permanent installation of two CPUs in the Amiga with selection of one of the two installed CPUs via a SPST latched Off-On switch;

   b) selection of one of two Kickstarts via a SPST latch Off-On switch;

   c) optionally two other configuration parameters, each controlled via a latchsed SPST Off-On switch, one can be used to drive a ["DF0 Selector" board with a SPST control interface such as the one developped by Jussi Kilpelainen](https://jussikilpelainen.kapsi.fi/wordpress/?p=256)

   d) a led illumination driver for each parameter, enabling the use of illuminated switches 

2. A "DualKickAdapter" card that fits in the Kickstart DIP40 slot, allowing a permanent installation of two kickstart ROMs in the Amiga. Kickstart selection can be controlled either by the "DualCpuAdapter" card or by a DPDT On-On switch. 

The "DualKickAdapter" can be controlled by the "DualCpuAdapter" board by connecting 2 wires from the KICK1_CSn & KICK2_CSn header pins of the "DualCpuAdapter" board to the middle pins of the 2x3 header "SW DPDT", CSn_A & CSn_B.

The [CIT Relay GH Series](http://citrelay.com/view_switch.php?series=GH) are illuminated SPST latching off-on pushbutton switches with a small enough diameter of 10mm to be installed on the lower area of the bottom chassis of the Amiga 2000.

I made this project initially for personal use. It is operational and free of license. 


|:warning:**IMPORTANT: The KiCad files provided in the github repository have been translated from another commercial PCB design tool. The latest beta version (7.99) is required to open the files. I strongly advise to double check the KiCad PCB design files before sending to production. Please feel free to propose document updates.** |
|-----------------------------------------|

DualCpuAdapter, CPU1 side  | DualCpuAdapter, CPU2 side | DualKickAdapter
:-------------------------:|:-------------------------:|:-------------------------:
| ![](https://github.com/mutedsounds/Amiga2000DualConfig/blob/main/Photos/DualCpuAdapter_SideCPU1.png) | ![](https://github.com/mutedsounds/Amiga2000DualConfig/blob/main/Photos/DualCpuAdapter_SideCPU2.png) | ![](https://github.com/mutedsounds/Amiga2000DualConfig/blob/main/Photos/DualKickAdapter.png) |

:camera:![CIT Relay GH Series Pushbutton Switches to select CPU model (red on the left) and Kickstart version (green on the right)](https://github.com/users/mutedsounds/projects/1/assets/135176179/4c770e0a-ff8a-44ca-834e-0b1e27449c4a)
|-----------------------------------------|

:camera:![Selection of legacy configuration 68000 with Kickstart 1.3, CPU switch off, Kickstart switch off](https://github.com/users/mutedsounds/projects/1/assets/135176179/7f285a54-d631-4581-9c03-284ca2d2d242)
|-----------------------------------------|

:camera:![Selection of legacy CPU 68000 with Kickstart 3.2.2, CPU switch off, Kickstart switch on](https://github.com/users/mutedsounds/projects/1/assets/135176179/2aaed360-2e29-441e-9bbe-69dbc4d2bf91)
|-----------------------------------------|

:camera:![Selection of TF536 accelerator board with Kickstart 3.2.2, CPU switch on, Kickstart switch on](https://github.com/users/mutedsounds/projects/1/assets/135176179/309dac52-2971-43a3-9c62-463e57b7b171)
|-----------------------------------------|

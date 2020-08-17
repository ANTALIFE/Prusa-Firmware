# Prusa i3 MK3S + MMU2S Better Handling of Filament Diameter Irregularities

My solution to issue [#2797](https://github.com/prusa3d/Prusa-Firmware/issues/2797)
![Diameter Irregularity](https://user-images.githubusercontent.com/21979291/90369594-68c71e80-e0af-11ea-9e5c-01d53f9bff88.png)

Only change is to ["can_load()" function of "mmu.cpp"](https://github.com/prusa3d/Prusa-Firmware/compare/MK3...ANTALIFE:MK3_3.9.0-ANT), as here I adjusted the "filament_detected_count" threshold from 26 (-4) to 5 (-25). Doing so means the IR sensor has to see 5 instances of valid load (vs the old 26) for the filament load to be considered successful. For one of my 5 colour prints above change has reduced failed loads from 10 to 0 :D

You can compile the FW yourself using [Prusa's instructions](https://github.com/prusa3d/Prusa-Firmware#linux), just make sure to use "./PF-build.sh" and [not "./build.sh"](https://github.com/prusa3d/Prusa-Firmware/issues/2799) if you are compiling on Linux OS

Otherwise you can download the compiled .hex here:

**[FW390-ANT-Build3421-1_75mm_MK3S-EINSy10a-E3Dv6full.hex](https://drive.google.com/file/d/1hc7U24rbg7fO95JxU7Q-QvqoINkHbIh-/view?usp=sharing)**

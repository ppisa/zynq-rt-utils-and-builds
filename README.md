zynq-rt-utils-and-builds
========================

Xilinx Zynq utilities, patches, projects builds and experiments

MicroZed U-Boot Patch to setup UART0 as SPL and U-boot console
--------------------------------------------------------------

The UART1 is selected as console on MicroZed board and MIO
is configured to route signals to serial to USB converter
present on the MicroZed board.

But this solution has drawbacks when galvanically isolated
connection is required for serial board use in the control
applications. The micro USB connector is fragile when
MicroZed is intended to be used for university courses
as well. Yet another problem is that power management on MicroZed
board does not correctly/fully disable some power supply
rails when carrier board supply is switched off. The current
from USB rail leaks to SDRAM and other chip power supply pins.
The correct solution on the carrier board requires strong pull
down on some signals which is not so easy by semiconductors
(FETs) to switch on when there is no power supply.
Switching console fills all these requirements.

[0001-ARM-zynq-MicroZed-configure-clocks-and-pins-for-UAR0.patch](projects/u-boot/patches/0001-ARM-zynq-MicroZed-configure-clocks-and-pins-for-UAR0.patch)

[0002-ARM-zynq-MicroZed-select-UAR0-to-be-used-for-console.patch](projects/u-boot/patches/0002-ARM-zynq-MicroZed-select-UAR0-to-be-used-for-console.patch)

[0003-ARM-zynq-Silence-unnecessary-warnings-when-CONFIG_FP.patch](projects/u-boot/patches/0003-ARM-zynq-Silence-unnecessary-warnings-when-CONFIG_FP.patch)

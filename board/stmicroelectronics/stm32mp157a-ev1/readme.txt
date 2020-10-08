STM32MP157A Evaluation v1

Intro
=====

This configuration supports the STM32MP157 Evaluation 1 (EV1)
platform:

  https://www.st.com/en/evaluation-tools/stm32mp157a-ev1.html

How to build
============

 $ make stm32mp157a_ev1_defconfig
 $ make

How to write the microSD card
=============================

Once the build process is finished you will have an image called
"sdcard.img" in the output/images/ directory.

Copy the bootable "sdcard.img" onto an microSD card with "dd":

  $ sudo dd if=output/images/sdcard.img of=/dev/sdX

Boot the board
==============

 (1) Insert the microSD card in connector CN9
 
 (2) Disconnect JP9 and redirect UART signals with JP4 and JP5 as shown at user manual UM2535 page 16: https://www.st.com/en/evaluation-tools/stm32mp157a-ev1.html#documentation

 (3) Plug a micro-USB cable in connector CN4 and run your serial
     communication program on /dev/ttyACM0.

 (4) Plug the power supply cable in CN1 to power-up the board.

 (5) The system will start, with the console on UART, but also visible
     on the screen.

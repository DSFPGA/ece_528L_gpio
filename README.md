# ECE 528/L - Robotics and Embedded Systems Lab
**CSU Northridge**

**Department of Electrical and Computer Engineering**

## Overview

Title: Lab 0 - GPIO
Author: Dominic Sanqui
Date: 9/24/26

Description: The purpose of this lab is to introduce how to use the General Purpose Input/Output (GPIO) of the MSP432 Launchpad. For this lab, we configure the MSP432 Launchpad to have 2 types of inputs which are 2 buttons and 4 PMOD switches. Additionally, the MSP432 Launchpad was configured to have 2 types of outputs: LEDs built into the Launchpad and LEDs connected through a PMOD 8LD. Based on the values of the buttons and/or switches, the LEDs on the Launchpad and the PMOD will display a variety of patterns.

## Components Used
- 1 TI-RSLK MAX
- 1 PMOD SWT
- 1 PMOD 8LD
- 1 USB-A to Micro-USB Cable
- 1 Breadboard
- Female to Male Connectors

## Analysis and Results
This section will be divided into several subsections for each task. For each task, the process of developing the code and the results for each task will be explained.

1. Initial Behavior for LED_Pattern_1 and LED_Pattern_2
This subsection analyzes the behavior of the Launchpad, PMOD 8LD, and PMOD SWT modules with the initial of LED_Pattern_1 and LED_Pattern_2 provided for this lab. Figures 1-4 display the values of the buttons and LEDs for test cases 1-4 respectively of LED_Pattern_1. Figure 5 display the values of the buttons, switches, and LEDs on the Launchpad for LED_Pattern_2. Figure 6 displays three test cases for LED_Pattern_2 which are the values of the LEDs at different points as it is not feasible to showcase all results. 

Figure 1: LED_Pattern_1 Test Case 0: Press Button 1
![Figure 1](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure1.png)

Figure 2: LED_Pattern_1 Test Case 1: Press Button 2
![Figure 2](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure2.png)

Figure 3: LED_Pattern_1 Test Case 2: Press Button 1 and 2
![Figure 3](/ece_528L_gpio/Screenshots/ece528L_lab0_gpio_figure3.png)

Figure 4: LED_Pattern_1 Test Case 3: Press No Buttons
![Figure 4](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure4.png)

Figure 5: LED_Pattern_2: Buttons and Switch Values
![Figure 5](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure5.png)

Figure 6: LED_Pattern_2: LED Values when
![Figure 6](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure6.png)

2. Task 1: Modified LED_Pattern_1
This subsection analyzes the behavior of the equipment after modifying LED_Pattern_1. Figures 7-10 display the values of the buttons and LEDs for test cases 0-3 respectively. 

For modifying the code, the values to trigger the case statements are still the same, so those were not modified. The changes were mainly within the case statements. To configure the LEDs, the output registers of the ports need to be set to a specific value. Most of the values were written down as constant definitions such as turning on or off LED0, so those definitions could be reused for this task. For the new patterns of the LEDs, new constant definitions such as PMOD_8LD_EVEN_ON and PMOD_8LD_ODD_ON were generated and used for this task.

Figure 7: Modified LED_Pattern_1 Test Case 0: Press Button 1
![Figure 7](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure7.png)

Figure 8: Modified LED_Pattern_1 Test Case 1: Press Button 2
![Figure 8](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure8.png)

Figure 9: Modified LED_Pattern_1 Test Case 2: Press Button 1 and 2
![Figure 9](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure8.png)

Figure 10: Modified LED_Pattern_1 Test Case 3: Press No Buttons
![Figure 10](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure10.png)

3. Task 2: LED_Pattern_3
This subsection analyzes the behavior of the equipment after generating the function LED_Pattern_3. Figure 11 displays the values of the buttons and switches. Figure 12 displays the results for three test cases.

For this task, the goal was to generate a new function to implement a binary down counter when only switch 2 is enabled. It would start at a decimal value of 255 (0xFF) and decrement down to 0. This implementation would require a for loop that starts at 255 and decrements by 1 at the end of every iteration. The value of the for loop counter would then be passed on to the output register of the LEDs to represent the down counter. Additionally, a new case statement in the LED_Controller function was needed for the MCU to process the switch 2.

Figure 11: LED_Pattern_3 Buttons and Switch Values
![Figure 11](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure11.png)

Figure 12: LED_Pattern_3 LED values
![Figure 12](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure12.png)

4. Task 3: LED_Pattern_4
This subsection analyzes the behavior of the equipment after generating the function LED_Pattern_4. Figure 13 displays the values of the buttons and switches. Figure 14 displays the results for three test cases.

For this task, the goal was to generate a new function to generate a ring counter that starts at the right and shifts one bit at a time to the left. To generate the code, bit 0 was initially set to 1. At the end of every iteration, this set bit is shifted one bit to the left until eventually bit 7 has been set. Additionally, a new case statement in the LED_Controller function was needed for the MCU to process the switch 3.

Figure 13: LED_Pattern_4 Buttons and Switch Values
![Figure 13](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure13.png)

Figure 14: LED_Pattern_4 LED values
![Figure 14](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure14.png)

5. Task 4: LED_Pattern_5
This subsection analyzes the behavior of the equipment after generating the function LED_Pattern_5. Figure 15 displays the values of the buttons and switches. Figure 15 displays the results for three test cases.

For this task, the goal was to generate a new function to generate a ring counter that starts at the left and shifts one bit at time to the right. To generate the code, bit 7 was initially set to 1. At the end of every iteration, this set bit is shifted one bit to the right until eventually bit 0 has been set. Additionally, a new case statement in the LED_Controller function was needed for the MCU to process the switch 4.

Figure 15: LED_Pattern_5 Buttons and Switch Values
![Figure 15](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure15.png)

Figure 16: LED_Pattern_5 LED values
![Figure 16](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure16.png)

6. Task 5: Johnson_Counter
This subsection analyzes the behavior of the equipment after generating the function Johnson_Counter. Figure 17 displays the values of the buttons and switches. 

For this task, the goal was to generate a new function to generate a Johnson counter. This counter will initially set the value of all LEDs to 0. In the following iterations, the value of the LEDs will be shifted to the left by one bit and the least significant bit will be inverted until eventually the value of the LEDs returns to 0. Additionally, a new case statement in the LED_Controller function was needed for the MCU to process when both switch 1 and 2 are enabled.

Figure 17: Johnson_Counter Buttons and Switch Values
![Figure 17](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure17.png)

Figure 18: Johnson_Counter LED values
![Figure 18](/ece528L_gpio/Screenshots/ece528L_lab0_gpio_figure18.png)

## Known issues or limitations
LED7 of the PMOD 8LD never turned on regardless of the value of the P9OUT register. This could be the result of damage to either the MCU or the PMOD 8LD itself. Since LED0-6 still work, I was able to still generate most of the expected outputs.

## References
* Technical Reference Manual for TI MSP432 Launchpad
[Product Link](https://web.archive.org/web/20200402132841/http:/www.ti.com/lit/ug/slau356i/slau356i.pdf)

* User buttons and LEDs of the TI MSP432 LaunchPad
* PMOD SWT (4 Slide Switches) - [Product Link](https://digilent.com/reference/pmod/pmodswt/start)
* PMOD 8LD (8 LEDs) - [Product Link](https://digilent.com/shop/pmod-8ld-eight-high-brightness-leds/)
## Getting Started with STM32F407
*Contains all of my process in understanding microprocessor.*

### To Do List
- [x] Create some report  
- [ ] with the picture come explanation  
- [ ] upload source code (which you created or edited) to this repository  
- [ ] a cooler project will come then

I currently study in Mechatronics Engineering.
Which is the combination of Electrical Engineering, Mechanical Engineering and Informatics Engineering. 
In Informatics side, understanding the microprocessor (5W+1H) is pretty necessary. 

>At the first time, I know nothing. And this is what I asked google to help me out.:thumbsup:

* [Datasheet of STM32F407](https://www.st.com)
* [Datasheet of the board](https://www.st.com)

![STM32F407](https://ae01.alicdn.com/kf/HTB1WEpBRXXXXXXDXVXXq6xXFXXXs/STM32F407G-DISC1-new-STM32F4DISCOVERY-Board-for-STM32F4-series-with-STM32F407-STM32F4-Discovery-supports-mbed.jpg)

## Progress Blink Code 
*November 11th, 2017*

So, the first thing I try in programming microprocessor is blinking STM32F407

Before making the project, we have to download and install some apps which is :
1. Cross ARM GNU
2. Plugins release
3. STM32 Toolchain
4. Pack STM32 Electronics
5. Eclipse (For your programming platform)

When all of the 'apps' already installed, I found blink program. When I try to run the program, I found :
![bin not found](https://user-images.githubusercontent.com/32242310/32642143-bf2210fa-c604-11e7-959b-e4d1bd758e84.png)

*November 14th, 2017*

Problem "Binary Not Found" solved!
That error appeared when I build and run the program in Eclipse. Program in eclipse shouldn't be run. 
* We only have to click build all
* Then change debug mode into release mode. 
* Open the STM32 ST-Link Utility. You can got it [here](https://www.st.com/stm32f4-discovery)
* Open the file we've made in Eclipse Workspace (In .hex)
* And you can see the STM32F407 blinks!

By the way, Im gonna describe what it really looks like when the board is connected to the PC.
1. When STM32 is connected with PC using USB Type A to Mini B, LED - LD1&2 will light up. LD2 indicates power accepted, and LD1 indicates board status whether it is filled with program or not.
![Iddle](https://user-images.githubusercontent.com/32242310/32766657-83d1ac4a-c942-11e7-9578-427fd4bab0e2.jpg)

2. And when B1 is pressed, MEMs sensor actives and 4 LEDs between B1 and B2 will light up.
![B1 pressed](https://user-images.githubusercontent.com/32242310/32766749-daed27f2-c942-11e7-9a74-4c6453d1ddcb.jpg)

3. It's like a mouse! When we tilt it to the left/right/up/down, different LEDs will blink.
![tilt 1](https://user-images.githubusercontent.com/32242310/32766869-61f258f8-c943-11e7-99a1-e0bae5cde37c.jpg)

![tilt 2](https://user-images.githubusercontent.com/32242310/32766911-99fd7f66-c943-11e7-9a1c-e4fe0bf086df.jpg)


![tilt 3](https://user-images.githubusercontent.com/32242310/32766933-b29ba872-c943-11e7-9272-33582c650bb7.jpg)

![tilt 4](https://user-images.githubusercontent.com/32242310/32766946-c677ef22-c943-11e7-93c1-2594fe896ca1.jpg)



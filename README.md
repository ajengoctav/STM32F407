## Getting Started with STM32F407
*Contains all of my process in understanding microprocessor.*

### To Do List (Made by my lecturer - github:oektomo)
- [x] Create some report  
- [x] with the picture come explanation  
- [x] upload source code (which you created or edited) to this repository  
- [x] a cooler project will come then

### What's inside this repository?
- [x] Basic knowledge about STM32F4
- [x] 'Tools' to be downloaded and installed before activating STM32F4
- [x] Activating STM32F4 as a mouse
- [x] Uploading the program from eclipse (blink) to STM32F4
- [x] Debugging (make gdb works on windows)
- [x] TUBES/TUGAS BESAR/FINAL TASK 
      *about parsing method and debug the program in C&assembly language

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
Photo above shows us when the board is tilt to the left, 2LEDs indicator in the right and up side will light up. This is caused by MEMs.
![tilt 2](https://user-images.githubusercontent.com/32242310/32766911-99fd7f66-c943-11e7-9a1c-e4fe0bf086df.jpg)
This is what we see when the board is tilt to the right. The indicator in the left side will light up. 
![tilt 3](https://user-images.githubusercontent.com/32242310/32766933-b29ba872-c943-11e7-9272-33582c650bb7.jpg)
And if we turn the board a lil bit lower, the blue LED will be off and the LED in the down side will light up.
![tilt 4](https://user-images.githubusercontent.com/32242310/32766946-c677ef22-c943-11e7-93c1-2594fe896ca1.jpg)
And if we make the board vertical (up side), the LED in the upper side will light up.

## Blink
When the 'getting started program' in eclipse is uploaded to the board, there will be no more mouse function. It all turns into blink function. So the 4 LEDs will be blink simultaneously with time delay.

## Move to Debugging
Debugging is identify and remove errors from the program.
I will do debugging (with gdb) in windows so there are some steps to do first before the debugging starts.
1. Install mingw. Mingw is one of the tools to manage the apps for linux to be operated in windows.
2. Install gdb (gnu debugger) for windows
3. Start to write the code!

To make the gdb appears, we need to make the directory goes to the mingw folder where gdb.exe exists.
The command prompt will be like :
![hai](https://user-images.githubusercontent.com/32242310/34298036-3a4834b6-e74e-11e7-852b-f9f81880a5fb.png)
Based on the red sign in the photo, gdb.exe exists in bin for mingw32 software. I put mingw32 in my data C (Program Files). 
When command prompt found the directory, gnu debugger will be activated and we can write gdb's instruction.

I got basic instruction for gdb [here](https://www.tutorialspoint.com/gnu_debugger/gdb_commands.htm)
And I got the instruction for disassembly the code [here](https://yohan.es/security/gdb/#index1h2)

## Parsing
Parsing is analyze strings (text) in order to test conformability to a logical grammar.
I got insights from this [web](https://www.daniweb.com/programming/software-development/code/216952/to-implement-predictive-parsing-in-c) to make the parser program. Actually I didn't make it by my self, I just combine the programs i got from some webs. But. I tried to understand every lines of my parser program.
The program tells user to give the input consists of arithmetic symbol (+ - * / etc) and the input will be pushed to the stack. If the input is right, action table (shifting info of the input) will be performed whenever we run the program. If the input is wrong, error appears when we run the program. 

And I debug this program using gdb for windows. I found something interesting. Gdb can't work if we put mingw folders in Program Files. I read in mingw site that it's strongly prohibited to be placed in local disk C's main folder. So we have to place mingw in another directory. When gdb works, I used 'disas main' to show assembly language of the program.






# Project 1: Bare Minimum Human-Robot Interface
> [!IMPORTANT]
> # Due: Thursday, Oct. 1st @ 5 PM

## Overview
Human-Robot Interface (HRI) is widely used allowing humans to easily interact with robots. 
The fundamentals of an HRI include **displaying** a robot's status, and **responding** to human operations. 
In this project, we will build a bare minimum HRI using LED and tactile switch button as illustrated below.

![hri_example](/assets/images/hri_example.gif)

## Requirements:

### 1 (15%) Circuit Design
- (10%) Wire up the Raspberry Pi Pico, LEDs and the button to deliver a functional circuit for the HRI.
- (3%) Make a debouncing circuit for the button.
- (2%) Use a **common cathode** RGB LED.
> [!TIP]
> - Search online if any concepts are confused.
> - Scavenge in robotics lab or ask Dr. Zhang's help if any parts are needed.

> [!IMPORTANT]
> Redeem the credits by uploading images and display them in [Documentation](#circuit-design) below.

### 2 (65%) Coding
- Program the Raspberry Pi Pico to: 
    - Encode robot's status into colors (`RED`, `GREEN`, `BLUE`) using LEDs .
    - Switch robot's behavior between `WORK MODE` and `PAUSE MODE` using a button.
- Upload your script to this repository.
- Complete following tasks:
1. Initialization (System Check): blink all the LEDs at the same time if the button's GPIO pin is receiving correct default signal (`0` for `PULL_DOWN`, `1` for `PULL_UP`).
   - (4%) Blink all LEDs with frequency of 5 Hz, lasting 2 seconds.
   - (1%) The robot enters `PAUSE MODE` after this step.
2. When `PAUSE MODE` is activated:
   - (10%) `GREEN` LED fades in and fades out at frequency of 1 Hz (equally allocate fade-in and fade-out time).
   - (10%) Press the button to **immediately** switch to the `WORK MODE`.
3. When `WORK MODE` is activated:
   - (4%) `GREEN` LED stays constantly on.
   - (6%) Press the button to **immediately** switch to the **PAUSE MODE**.
4. Time `WORK MODE`.
   - (15%) If the accumulated `WORK MODE` time exceeds 45 seconds, substitute `GREEN` LED with **`BLUE`** LED in both modes (low-battery simulation).
   - (5%) If accumulated `WORK MODE` time over 55 seconds, blink `RED` LED (`BLUE` LED keep working) at frequency of 10 Hz.
5. (10%) Termination. **Despite the mode**, trigger a [hard reset](https://docs.micropython.org/en/latest/wipy/tutorial/reset.html#reset-and-boot-modes) if:
   - `RED` LED blinked 5 seconds
   - button is **pressed and held** for 3 seconds. 

> [!IMPORTANT]
> - Mode switching is NOT a one-time function.
> - After 55 seconds of `WORK`, the `BLUE` LED and the `RED` LED are suppose to be functional together in both modes.

> [!TIP]
> - Break tasks down into small pieces (the smaller the better). You may need write a handful of unit test scripts.
> - `print()` function and Python Shell are handy tools.
> - [global variables](https://realpython.com/python-use-global-variable-in-function/) are useful for interrup handling functions.

### 3 (20%) Documentation
**It is important to get an engineering project well documented.** 
Complete the [Documentation](#documentation-student-work-) section below. 
1. Illustrate circuit design
   - (7%) Upload a [wiring diagram](https://projects-static.raspberrypi.org/projects/getting-started-with-the-pico/76943ea08b51e5f59937fcc4cec1d531fc013b6c/en/images/single_LED.png) or a circuit schematic (breadboard is optional) to this repository  and display it in the [Circuit Diagram](#circuit-diagram) section.
   - (1%) Upload a picture to this repository to illustrate your physical setup. Display it in the [Wiring Picture](#wiring-picture) section.
2. (10%) Explain how your debouncing circuit works using **math** language.
   - Explain how button "pressing" is delayed. Use equation(s) to calculate delayed time.  
   - Explain how button "releasing" is delayed. Use equation(s) to calculate delayed time.  
4. (2%) (Within 80 words) Briefly propose a nice-to-have feature for an **HRI** with consideration of **safety**.
   State why this feature will make the robot safer to the hardware/user/public/environment/etc..

> [!TIP]
> Please refer to [Github formatting guide](https://docs.github.com/en/get-started/writing-on-github).


## Documentation (Student Work) 👇

### Circuit Design
#### Circuit Diagram
> Display ciruit diagram below

![diagram name](diagram_link)

#### Wiring Picture
> Display an actual picture of your physical circuit below.

![picture name](picture_link)

#### Debouncing Circuit Explained
> Write your analysis down below in **math** language. 

### Safety Feature in Future
> Write your considerations/solutions down below.

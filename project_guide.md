# Project 1: Bare Minimum Human-Robot Interface
> [!IMPORTANT]
> # Due: Thursday, Oct. 1st @ 5 PM

## 1. Overview
Human-Robot Interface (HRI) is widely used allowing humans to easily interact with robots. 
The fundamentals of an HRI include **displaying** a robot's status, and **responding** to human operations. 
In this project, we will build a bare minimum HRI using LED and tactile switch button as illustrated below.

![hri_example](/assets/images/hri_example.gif)

The main objective of this project is to practice advanced coding skills on the Raspberry Pi Pico 2 board.

## 2. Get Started
You may want to prepare following items for this project.
> [!NOTE]
> These are just recommended setup.

### 2.1. Hardware

| Name                  | Qty. |
|   :---                | ---: |
| Raspberry Pi Pico 2   |  x1  |
| Green LED             |  x1  |
| Yellow LED            |  x1  |
| Red LED               |  x1  |
| 220 $\Omega$ Resistor |  x3  |
| Tactile Button        |  x1  |
| Jumper Wires          |  x?  |
| Solderless Breadboard |  x1  |
| Micro-USB Cable       |  x1  |
| Computer              |  x1  |

### 2.2. Software
- [Thonny](https://thonny.org)
- [MicroPython Firmware](https://micropython.org/download/RPI_PICO2/)
 
## 3. Requirements:

### 3.1. (15%) Circuit Design
Wire up the Raspberry Pi Pico, LEDs and the button to deliver a **functional** circuit for the HRI.
*You don't need to follow the circuit configured in the example [gif](/assets/images/hri_example.gif)*.
- (10%) Draw a wiring diagram illustrating how all the components are connected to Pico's GPIO pins.
Upload the wiring diagram and display it in the [README](/README.md).
- (5%) Upload a picture of your actual physical circuit and display it out in the [README](/README.md).
- (+5% bonus) Make a reasonable debouncing circuit for the button.

> [!CAUTION]
> No credit will be given if the components using different GPIO pins between the actual circuit and the wiring diagram.

### 3.2. (65%) Coding
Program the Raspberry Pi Pico to: 
  - Encode the system's status into colors (`RED`, `GREEN`, `YELLOW`) using LEDs .
  - Switch the system's behavior between `WORK MODE` and `PAUSE MODE` by pressing a button.
Please complete the following coding tasks to redeem your credits.
1. (5%) Initialization (System Check): blink all the LEDs at the same time **if the button's GPIO pin is receiving correct default signal** (`0` for `PULL_DOWN`, `1` for `PULL_UP`).
   - (4%) Blink all LEDs with frequency of 5 Hz, lasting 2 seconds.
   - (1%) The system enters `PAUSE MODE` after this step.
2. (20%) When `PAUSE MODE` is activated:
   - (10%) `GREEN` LED fades in and fades out at frequency of 1 Hz (equally allocate fade-in and fade-out time).
   - (10%) Press the button, the system **immediately** switch to the `WORK MODE` **at the moment the button is released**.
3. (10%) When `WORK MODE` is activated:
   - (4%) `GREEN` LED stays constantly on.
   - (6%) Press the button, the system **immediately** switch to the `PAUSE MODE` **at the moment the button is released**.
4. (20%) Time `WORK MODE`.
   - (15%) If the accumulated `WORK MODE` time exceeds 40 seconds, substitute `GREEN` LED with **`YELLOW`** LED in both modes (low-battery simulation).
   - (5%) If accumulated `WORK MODE` time over 50 seconds, blink `RED` LED at frequency of 10 Hz (`YELLOW` LED has to be functional under both modes).
5. (10%) Termination. **Despite the mode**, put the Pico 2 board into **Deep Sleep** if:
   - (10%) `RED` LED blinked 5 seconds (no matter)
   - (+5% bonus) button is **pressed and held** for 3 seconds. 
- (+2% bonus) Auto start the program whenever the Pico 2 board get powered up.

> [!IMPORTANT]
> No credits will be given to the mode switching part if the system can only switch mode once.

> [!TIP]
> - Break tasks down into small pieces (the smaller the better). You may need write a handful of unit test scripts.
> - `print()` function and Python Shell are handy tools.
> - [global variables](https://realpython.com/python-use-global-variable-in-function/) are useful for the callback functions.

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

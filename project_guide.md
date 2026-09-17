# Project 1: Bare Minimum Human-Robot Interface
> [!IMPORTANT]
> # Due: Thursday, Oct. 1st @ 5 PM

## 1. Overview
Human-Robot Interface (HRI) is widely used allowing humans to easily interact with robots. 
The fundamentals of an HRI include **displaying** a robot's status, and **responding** to human operations. 
In this project, we will build a bare minimum HRI using LED and tactile switch button as illustrated below.

![hri_example](/assets/images/hri_example.gif)

The main objectives of this project is to 
- Practice advanced coding skills on the Raspberry Pi Pico 2 board.
- Practice professional documentaion for engineering projects.

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
Wire up the Raspberry Pi Pico 2, LEDs and the button to deliver a **functional** circuit for the HRI.
*You don't need to follow the circuit configured in the example [gif](/assets/images/hri_example.gif)*.
- (10%) Draw a wiring diagram illustrating how all the components are connected to Pico's GPIO pins.
Upload the wiring diagram to this repository.
- (5%) Upload a picture of your actual physical circuit **without key connection gets obstructed** to this repository.
- (+5% bonus) Make a reasonable debouncing circuit for the button.

> [!CAUTION]
> No credit will be given if the components using different GPIO pins between the actual circuit and the wiring diagram.

### 3.2. (65%) Coding
Program the Raspberry Pi Pico to: 
  - Encode the system's status into colors (`RED`, `GREEN`, `YELLOW`) using LEDs .
  - Switch the system's behavior between `WORK MODE` and `PAUSE MODE` by pressing a button.

Please complete the following coding tasks to redeem your credits.
You can use the [template](/minimum_hri.py) to get started or upload your own script.
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

### 3.3. (20%) Documentation
> [!IMPORTANT]
> **Get your engineering projects well documented from now on.**

Complete the documentation using [README](README.md). 
- (12%) List components on your circuit in a Markdown table with 3 columns (`Name`, `Description`, `Quantity`).
  - Describe the functionality of each item.
  - Specify the exact number for each item.
  - Do not include items not directly related to the circuit (e.g. computer).
> [!TIP]
> You can use the table in this guide as a template.

- (6%) Illustrate the circuit.
   - (3%) Display a picture of your actual circuit in [README](README.md) with the resolution of 800 px. x 600 px for landscape layout. (600 px. x 800 px. for portrait layout).
   - (3%) Display the wiring diagram with the resolution of 800 px. x 600 px for landscape layout. (600 px. x 800 px. for portrait layout).
- (2%) Acknowledge AI's contributions.
Please list out all the AI's contributions to this project.
- (+25% bonus) Explain how the debouncing circuit works on the GPIO (if you had one) using **math** language.
   - (+5% bonus) Explain how button "pressing" and "releasing" gets delayed with math equation(s) and numbers.   
   - (+10% bonus) Plug in values from your actual circuit to calculate how long does the circuit delayed the "pressing" signal. 
   - (+10% bonus) Plug in values from your actual circuit to calculate how long does the circuit delayed the "releasing" signal. 
> [!TIP]
> You need to figure out what type of logic level does RP2350 chip use and how it treats a certain voltage as the logic level.

## 4. Resources
- [pico-micropython-examples](https://github.com/raspberrypi/pico-micropython-examples)
- [Raspberry Pi Pico Python SDK](https://datasheets.raspberrypi.com/pico/raspberry-pi-pico-python-sdk.pdf)
- [Organizing information with tables](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables)
- [Writing mathematical expressions](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
- [Designing an RC debounce circuit](https://mayaposch.wordpress.com/2018/06/26/designing-an-rc-debounce-circuit/)
- [Raspberry Pi Pico 2 Datasheet](https://pip.raspberrypi.com/documents/RP-008299-DS)
- [Logic Level](https://en.wikipedia.org/wiki/Logic_level)


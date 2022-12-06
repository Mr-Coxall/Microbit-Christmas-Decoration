# micro:bit - Introduction

## Introduction @unplugged

![micro:bit getting started image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/dice.png)

Learn how to get the micro:bit to be a virtual dice.

[Watch dice video](https://youtu.be/FzfHJH903nU).

## Now let's connect and attach the micro:bit, ONLY if we need to! @showhint

** ONLY RE-CONNECT IF YOU ARE NOT ALREADY CONNECTED!**

Let's get the micro:bit connected to the computer again:
- plug the micro:bit into the micro USB cable
- plug the other end into the computer
- click the "..." at the bottom left of the screen, next to the "Download" button
- select "Connect device"
- select your micro:bit ("BBC micro:bit CMSIS-DAP")
- then select "Connect"

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

## Now let's write another program @showhint

Let's program the micro:bit to be a dice:
- remove the ``||basic:on start||`` block & the ``||basic.forever||`` block by dragging them over to tool bar (to the left where the blocks are). When you drag them over o the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!
- select ``||input. Input||`` and drag out a ``||input.on shake ▼ ||`` block
- select ``||basic. Basic||`` and drag out a ``||basic.showNumber(0) ||`` block
- place it inside the ``||input.on shake ▼||`` block
- select ``||math: Math||`` and drag out the ``||math:randint(0, 10)||`` block
- place it where the "10" is inside the ``||math:randint(0, 10)||`` block
- change the "0" to be "1"
- change the "10" to be "6" 
- hit the "Download" button at the bottom of the screen to flash your program to the micro:bit
- your program will not run until you shake your micro:bit

```blocks
// @highlight
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(randint(1, 6))
})
```

## Extra

**Extras**

- can you make a different kind of dice?
  - for 1 to 10?
  - for 1 to 4?
  - from 2 to 12?

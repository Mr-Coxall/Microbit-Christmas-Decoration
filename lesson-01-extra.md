# micro:bit - Make a Dice!

## Introduction @unplugged

Learn how to get the micro:bit to be a virtual dice.

[Watch dice video](https://youtu.be/FzfHJH903nU)

![micro:bit getting started image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/dice.png)

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
- select ``||basic. Basic||`` and drag out a ``||basic.show number(0) ||`` block
- place it inside the ``||input.on shake ▼||`` block
- select ``||math: Math||`` and drag out the ``||math: pick random (0) to (10)||`` block
- place it where the "10" is inside the ``||math:randint(0, 10)||`` block
- change the "0" to be "1"
- change the "10" to be "6"

```blocks
// @highlight
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(randint(1, 6))
})
```

## Finally! let's flash our first program! @unplugged

** Finally! let's flash our first program! **

![micro:bit flashing program image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/transfer.jpg)

## Finally! let's flash our first program!

Let's flash our program over to the micro:bit:
- hit the "Download" button at the bottom of the screen
- watch the lights flash on the back of the micro:bit
    - this is a good thing, it means the program is being flashed over to the micro:bit
- once it is all done, you should see your program running on the micro:bit

## Extra

**Extras**

- can you make a different kind of dice?
  - for 1 to 10?
  - for 1 to 4?
  - from 2 to 12?

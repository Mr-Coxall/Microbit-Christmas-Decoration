# micro:bit Introduction

## Introduction @unplugged

![micro:bit getting started image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/micro-bit-getting-started.png)

Learn how to get the micro:bit working, program its features and create your first projects.

[Watch introduction video](https://youtu.be/u2u7UJSRuko).

## Let's Attach the micro:bit @showhint

![micro:bit attached to micro USB cable image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/connect-micro-bit.png)

Let's get the micro:bit attached to the computer:
- plug the micro:bit into the micro USB cable
- plug the other end into the computer

## Now let's connect the micro:bit @showhint

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

Let's get the micro:bit connected to the computer:
- click the "..." at the bottom left of the screen, next to the "Download" button
- select "Connect device"
- select your micro:bit ("BBC micro:bit CMSIS-DAP")
- then select "Connect"

## Now let's write your first program!

![micro:bit programming image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/program.jpg)

Let's program the micro:bit:
- from the code blocks, select "Basic"
- then click and drag out the ``||basic:show string("Hello!")||`` block.
- place it inside the ``||basic:on start||`` block
- now add you name after "Hello":
    - Example: ``||basic:show string("Hello, Jane!")||``

```blocks
// @highlight
basic.showString("Hello, Jane!")
```

## Now let's check our first program!

Let's check our program:
- on the left hand side, the micro:bit simulator should have updated
- you can test run your program, to ensure it is working correctly
- if you need to fix anything, do so now

## Finally! let's flash our first program!

![micro:bit flashing program image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/transfer.jpg)

Let's flash our program over to the micro:bit:
- hit the "Download" button at the bottom of the screen
- watch the lights flash on the back of the micro:bit
    - this is a good thing, it means the program is being flased over to the micro:bit
- once it is all done, you should see your program running on the micro:bit

## Run it again!

Let's run your program again:
- hit the "reset" button on the back of the micro:bit
- your program should start over aain
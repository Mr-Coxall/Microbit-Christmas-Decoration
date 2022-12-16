# micro:bit - Make 2 micro:bits talk to each other!

## 01 @unplugged

**Learn how to get 2 micro:bits to talk to each other.**

In this program you will get 2 micro:bit to communicate using Bluetooth.

**NOTE: Each group must have *a different number*, so the micro:bit knows who they should be talking to**

![micro:bit adding game](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/micro_bit_radio.png)

## 02 @showhint

** ONLY RE-CONNECT IF YOU ARE NOT ALREADY CONNECTED!**

Let's get the micro:bit connected to the computer again:
- plug the micro:bit into the micro USB cable
- plug the other end into the computer
- click the "..." at the bottom left of the screen, next to the "Download" button
- select "Connect device"
- select your micro:bit ("BBC micro:bit CMSIS-DAP")
- then select "Connect"

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

## 03 @unplugged

**This code is for the person sending the message**

**REMEMBER: you need to have your group number**

## 04 @showhint

This code will send a message to another micro:bit:
- remove the ``||basic.forever||`` block by dragging it over to the tool bar (to the left where the blocks are). When you drag them over to the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!
- select ``||basic: Basic||`` drag out a ``||basic. clear screen ||`` block and add it to the ``||basic:on start||`` block
- select ``||basic: Basic||`` drag out a ``||basic:show icon ♥ ▼||`` block and add it to the bottom in the ``||basic:on start||`` block
- change the icon to a ``||basic:show icon ✓ ▼||``
- select ``||radio: Radio||`` drag out a ``||radio: radio set group (1) ||`` block and add it to the bottom in the ``||basic:on start||`` block
- change the "(1)" to the number your group is using
  - **REMEMBER:it can not be the same number as any other group**

```blocks
basic.clearScreen()
basic.showIcon(IconNames.Happy)
radio.setGroup(1)
```

## 05 @showhint

Now for the message:
- select ``||input. Input||`` and drag out a ``||input.on button A ▼ pressed||`` block
- select ``||radio: Radio||`` drag out a ``||radio: radio send string ("") ||`` block and add it to the ``||input.on button A ▼ pressed||`` block
- place your **short** message inside the ("")
  - for example: ``||radio: radio send string ("Hello, World!") ||``

```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("Hello, World!")
})
```

## 06 @unplugged

**The sender code is now done.**

Let's flash your program over to the micro:bit:
- again press the "Download" button at the bottom of the screen
- watch the lights flash on the back of the micro:bit
    - this is a good thing, it means the program is being flashed over to the micro:bit
- once it is all done, you should see your program running on the micro:bit

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

## 07 @unplugged

**This code is for the person receiving the message**

**REMEMBER: you need to have your group number**

## 08 @showhint

This code will receive a message to another micro:bit:
- remove the ``||basic.forever||`` block by dragging it over to the tool bar (to the left where the blocks are). When you drag them over to the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!
- select ``||radio: Radio||`` drag out a ``||radio: radio set group (1) ||`` block and add it to the bottom in the ``||basic:on start||`` block
- change the "(1)" to the number your group is using
  - **REMEMBER:it can not be the same number as any other group**
- select ``||radio: Radio||`` drag out a ``||radio: on radio received (receivedString) ||`` block
- select ``||basic: Basic||`` drag out a ``||basic. clear screen ||`` block and add it to the ``||radio: on radio received (receivedString) ||`` block
- select ``||basic: Basic||``drag out a ``||basic: show string ("Hello!") ||`` block and add it to the bottom in the ``||radio: on radio received (receivedString) ||`` block
- on the ``||radio: on radio received (receivedString) ||`` block, select the ``||variables. (receivedString) ||`` block drag it out and place it where ("Hello!") is

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    basic.clearScreen()
    basic.showString("" + (receivedNumber))
})
```

## 09 @unplugged

**The receiver code is now done.**

Let's flash your program over to the micro:bit:
- again press the "Download" button at the bottom of the screen
- watch the lights flash on the back of the micro:bit
    - this is a good thing, it means the program is being flashed over to the micro:bit
- once it is all done, you should see your program running on the micro:bit

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

## 10 @showhint

**Play the Game**

- now the 2 people can send and receive the message
- once done, can you make additions or changes?
  - each person can be a sender **AND** a receiver
    - the receiving code will not change!
  - each person can have a different message of the "A" & "B" buttons
    - as well as for shake and the micro:bit touch icon!

## 11

**Done.**

# micro:bit - Make an addition game!

## Addition Game @unplugged

**Learn how to get the micro:bit to be a virtual math helper.**

![micro:bit getting started image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/add.png)

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

## Now let's create a variable @showhint

A variable is just a place holder that can hold some information. In our case we will create 2 variables, each one holding a number that we will add together:
- remove the ``||basic:on start||`` block & the ``||basic.forever||`` block by dragging them over to tool bar (to the left where the blocks are). When you drag them over o the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!
- select ``||input. Input||`` and drag out a ``||input.on shake ▼ ||`` block
- select ``||variable. Variable||`` and then click "Make a Variable ..."
- we will call our 1st variable, "first_number", since it will hold the 1st number
- type in "first_number" and then press "Enter"
- you will notice a new block has been created, drag out the ``||variable. set [first_number ▼] to (0)||`` block and place it inside the ``||input.on shake ▼ ||`` block

```blocks
// @highlight
let first_number = 0
input.onGesture(Gesture.Shake, function () {
    first_number = 0
})
```

## Now let's create a 2nd variable @showhint

Now that we have our first variable, let's create a 2nd one:
- select ``||variable. Variable||`` and then click "Make a Variable ..."
- we will call our 2nd variable, "second_number", since it will hold the 2nd number
- type in "second_number" and then press "Enter"
- you will notice the new block has been changed. The little ▼ will let you select any variable you create. Drag out the ``||variable. set [second_number ▼] to (0)||`` block and place it inside the ``||input.on shake ▼ ||`` block under the ``||variable. set [first_number ▼] to (0)||`` block 

```blocks
let first_number = 0
let second_number = 0
input.onGesture(Gesture.Shake, function () {
    first_number = 0
    // @highlight
    second_number = 0
})
```

## Add in randomness @showhint

At the moment out 2 variables are just holding the number 0. We need to get the micro:bit to randomly choose numbers for us :
- select ``||math: Math||`` and drag out the ``||math: pick random (0) to (10)||`` block
- place it where the "0" is inside the ``||variable. set [first_number ▼] to (0)||`` block
- now change the "10" to "9"
- once again, select ``||math: Math||`` and drag out the ``||math: pick random (0) to (10)||`` block
- place it where the "0" is inside the ``||variable. set [second_number ▼] to (0)||`` block
- once again change the "10" to "9"

```blocks
let first_number = 0
let second_number = 0
input.onGesture(Gesture.Shake, function () {
    // @highlight
    first_number = randint(0, 9)
    // @highlight
    second_number = randint(0, 9)
})
```

## Now let's let the user know everything is ready @showhint

Now that we have both variables, let's show a "✓", so the user knows they can start:
- select ``||basic: Basic||`` and drag out the ``||basic:show icon ♥ ▼||`` block and change the icon to a ``||basic:show icon ✓ ▼||``
- place it after the ``||variable. set [second_number ▼] to (0)||`` block

```blocks
input.onGesture(Gesture.Shake, function () {
    first_number = randint(0, 9)
    second_number = randint(0, 9)
    // @highlight
    basic.showIcon(IconNames.Yes)
})
```

## Now let's make the numbers show up @showhint

In this program you will first shake the micro:bit to set the question. Then you will press "A: and "B" to see what numbers you will add together. Finally you can see the answer by touching the micro:bit touch logo on the front of the micro:bit.:
- select ``||input. Input`` and drag out a ``||input.on button A ▼ pressed||`` block
- select ``||basic. Basic||`` and drag out a ``||basic.show number(0)||`` block
- select ``||variable. Variable||`` and drag out the ``||variable. first_number||`` block
- place it inside the ``||basic.show number(0)||`` block where the "0" is
- this will show whatever random number was placed inside the ``||variable. first_number||`` vairiable

```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    basic.showNumber(first_number)
})
```

## Now let's make the 2nd number show up @showhint

Now let's make the 2nd number show up:
- select ``||input. Input`` and drag out a ``||input.on button A ▼ pressed||`` block
- select the ▼ and change the "A" to "B"
- select ``||basic. Basic||`` and drag out a ``||basic.show number(0)||`` block
- select ``||variable. Variable||`` and drag out the ``||variable. second_number||`` block
- place it inside the ``||basic.show number(0)||`` block where the "0" is
- this will show whatever random number was placed inside the ``||variable. second_number||`` vairiable

```blocks
input.onButtonPressed(Button.B, function () {
    // @highlight
    basic.showNumber(second_number)
})
```

## Now let's show the answer @showhint

This will only work on the new ver: 2 micro:bit (the one we have!):
- select ``||input. Input||`` and drag out a ``||input.on logo pressed ▼ ||`` block
- select ``||basic. Basic||`` and drag out a ``||basic. clear screen||`` block
- select ``||basic. Basic||`` and drag out a ``||basic. show string ("Hello!")||`` block
- goto the bottom and select "Advanced" and then select ``||text. Text||``
- drag out the ``||text. join ("Hello") ("World") ⊖ ⨁||`` block
- place it inside the ``||basic. show string ("Hello!")||`` block where the "Hello!" is
- this is used to join several words together
- hit the "⨁" 3 times, so you have 5 sections in total

```blocks
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    // @highlight
    basic.clearScreen()
    // @highlight
    basic.showString("Hello" + "World" + "" + "" + "")
})
```

## Now let's show the answer @showhint

Let's print out the answer:
- in the 1st section that currently has "Hello" place
  - select ``||variable. Variable||`` and drag out the ``||variable. first_number||`` block
- in the 2nd section that currently has "World" replace it with a "+" symbol
- in the 3rd section that currently is empty
  - select ``||variable. Variable||`` and drag out the ``||variable. second_number||`` block
- in the 4th section that currently is empty replace it with a "=" symbol
- in the last section that currently is empty
  - select ``||math. Math||`` and drag out the ``||math. (0) +▼ (0)||`` block
  - inside the first "(0)", replace it with the ``||variable. first_number||`` block
  - inside the second "(0)", replace it with the ``||variable. second_number||`` block

```blocks
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    basic.clearScreen()
    // @highlight
    basic.showString("" + first_number + "+" + second_number + "=" + (first_number + second_number))
})
```

## Finally! let's flash our first program!

Let's flash your dice program over to the micro:bit:
- again press the "Download" button at the bottom of the screen
- watch the lights flash on the back of the micro:bit
    - this is a good thing, it means the program is being flashed over to the micro:bit
- once it is all done, you should see your program running on the micro:bit

## Extra

**Extras**

- can you make a different kind of dice?
  - for 1 to 10?
  - for 1 to 4?
  - from 2 to 12?

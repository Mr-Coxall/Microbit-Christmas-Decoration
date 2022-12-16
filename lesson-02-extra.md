# micro:bit - Make an addition game

## 01 @unplugged

**Learn how to get the micro:bit to be a virtual math helper.**

In this program you will first shake the micro:bit to set the question. Then you will press "A" and "B" to see what numbers you will add together. Finally you can see the answer by touching the micro:bit touch logo on the front of the micro:bit.

![micro:bit adding game](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/addition.png)

## 02 @showhint

**ONLY RE-CONNECT IF YOU ARE NOT ALREADY CONNECTED!**

Let's get the micro:bit connected to the computer again:
- plug the micro:bit into the micro USB cable
- plug the other end into the computer
- click the "..." at the bottom left of the screen, next to the "Download" button
- select "Connect device"
- select your micro:bit ("BBC micro:bit CMSIS-DAP")
- then select "Connect"

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

## 03 @showhint

A variable is just a place holder that can hold some information. In our case we will create 2 variables, each one holding a number that we will add together:
- remove the ``||basic:on start||`` block & the ``||basic.forever||`` block by dragging them over to the tool bar (to the left where the blocks are). When you drag them over to the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!
- select ``||input. Input||`` and drag out an ``||input.on shake ▼ ||`` block
- select ``||variables. Variables||`` and then click "Make a Variable..."
- we will call our 1st variable, ``||variables. first_number||`` since it will hold the 1st number we are adding
- type in "first_number" and then press "Enter"
- you will notice several new blocks has been created, drag out the ``||variables. set [first_number ▼] to (0)||`` block and place it inside the ``||input.on shake ▼ ||`` block

```blocks
let first_number = 0
input.onGesture(Gesture.Shake, function () {
    // @highlight
    first_number = 0
})
```

## 04 @showhint

Now that we have our first variable, let's create a 2nd one:
- select ``||variables. Variables||`` and then click "Make a Variable..." again
- we will call our 2nd variable, ``||variables. second_number||``, since it will hold the 2nd number we are adding
- type in "second_number" and then press "Enter"
- you will notice the new blocks have changed. The ▼ will let you select any variable you have create. Drag out the ``||variables. set [second_number ▼] to (0)||`` block and place it inside the ``||input.on shake ▼ ||`` block under the ``||variables. set [first_number ▼] to (0)||`` block

```blocks
let first_number = 0
let second_number = 0
input.onGesture(Gesture.Shake, function () {
    first_number = 0
    // @highlight
    second_number = 0
})
```

## 05 @showhint

At the moment our 2 variables are just holding the number 0. We need to get the micro:bit to randomly choose numbers for us :
- select ``||math: Math||`` and drag out the ``||math: pick random (0) to (10)||`` block
- place it where the "0" is inside the ``||variables. set [first_number ▼] to (0)||`` block
- now change the "10" to "9"
- once again, select ``||math: Math||`` and drag out the ``||math: pick random (0) to (10)||`` block
- place it where the "0" is inside the ``||variables. set [second_number ▼] to (0)||`` block
- once again change the "10" to "9"

```blocks
let first_number = 0
let second_number = 0
input.onGesture(Gesture.Shake, function () {
    first_number = randint(0, 9)
    second_number = randint(0, 9)
})
```

## Now let's tell the user everything is ready @showhint

Now that we have both variables, let's show a "✓" on the screen, so the user knows they can start:
- select ``||basic: Basic||`` and drag out the ``||basic:show icon ♥ ▼||`` block and place it at the end
- change the icon to a ``||basic:show icon ✓ ▼||``

```blocks
input.onGesture(Gesture.Shake, function () {
    first_number = randint(0, 9)
    second_number = randint(0, 9)
    // @highlight
    basic.showIcon(IconNames.Yes)
})
```

## Now let's make the numbers show up @showhint

Leave the ``||input.on shake ▼ ||`` block with all it's code alone. We will be adding a new set of blocks. Now let's make the first number show up when you press the "A" button:
- select ``||input. Input||`` and drag out a ``||input.on button A ▼ pressed||`` block
- select ``||basic. Basic||`` and drag out a ``||basic.show number(0)||`` block
- select ``||variables. Variables||`` and drag out the ``||variables. first_number ▼||`` block, under "Your Variables"
- place it inside the ``||basic.show number(0)||`` block where the "0" is
- this will show whatever random number was placed inside the first_number variable

```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    basic.showNumber(first_number)
})
```

## Now let's make the 2nd number show up @showhint

Now we will leave that section of code and add another section. Now let's make the 2nd number show up:
- select ``||input. Input||`` and drag out a ``||input.on button A ▼ pressed||`` block
- you will notice that our previous code just turned grey; that is because we can not have 2 sections of code with the same start block
- select the ▼ on the new ``||input.on button A ▼ pressed||`` block and change the "A" to "B", the old code will turn from grey to pink
- select ``||basic. Basic||`` and drag out a ``||basic.show number(0)||`` block
- select ``||variables. Variables||`` and drag out the ``||variables. second_number ▼||`` block
- place it inside the ``||basic.show number(0)||`` block where the "0" is
- this will show whatever random number was placed inside the second_number variable

```blocks
input.onButtonPressed(Button.B, function () {
    // @highlight
    basic.showNumber(second_number)
})
```

## Now let's show the answer @showhint

Now let's show the answer:
- select ``||input. Input||`` and drag out a ``||input.on logo pressed ▼ ||`` block
- select ``||basic. Basic||`` and drag out a ``||basic. clear screen||`` block
- select ``||basic. Basic||`` and drag out a ``||basic. show string ("Hello!")||`` block
- in the tool bar go to the bottom and select "⌄ Advanced" and then select ``||text. Text||``
- drag out the ``||text. join ("Hello") ("World") ⊖ ⨁||`` block
- place it inside the ``||basic. show string ("Hello!")||`` block where the "Hello!" is
- this block is used to join several words together
- hit the "⨁" 3 times, so you have 5 sections in total

```blocks
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    // @highlight
    basic.clearScreen()
    // @highlight
    basic.showString("Hello" + "World" + "" + "" + "")
})
```

## Now we can show the answer @showhint

Let's print out the answer:
- in the 1st section that currently has "Hello" replace it with
  - select ``||variables. Variables||`` and drag out the ``||variables. first_number||`` block
- in the 2nd section that currently has "World" replace it with a "+" symbol
- in the 3rd section that currently is empty replace it with
  - select ``||variables. Variables||`` and drag out the ``||variables. second_number||`` block
- in the 4th section that currently is empty replace it with a "=" symbol
- in the last section that currently is empty replace it with
  - select ``||math. Math||`` and drag out the ``||math. (0) +▼ (0)||`` block
  - inside the first "(0)", replace it with the ``||variables. first_number||`` block
  - inside the second "(0)", replace it with the ``||variables. second_number||`` block

```blocks
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    basic.clearScreen()
    // @highlight
    basic.showString("" + first_number + "+" + second_number + "=" + (first_number + second_number))
})
```

## Finally! let's flash our adding program

Let's flash your add program over to the micro:bit:
- again press the "Download" button at the bottom of the screen
- watch the lights flash on the back of the micro:bit
  - this is a good thing, it means the program is being flashed over to the micro:bit
- once it is all done, you should see your program running on the micro:bit

## Play the Adding Game

**Play the Adding Game**

- shake the micro:bit to start the game, you should see a "✓" when it is ready
- press the "A" button to see the first number
- press the "B" button to see the second number
- in your head, add the 2 numbers together and remember your answer
- now touch the micro:bit logo on the front of the micro:bit, you should see the question and the answer scroll on the screen

## Done

**Done.**

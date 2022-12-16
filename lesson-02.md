# lesson-02

## Last Time @showhint

Last time we went over:
- what is a micro:bit
- attaching the micro:bit to the computer
- connecting the micro:bit to the computer
- wrote a program
- flashing it to the micro:bit
- ran the program on the micro:bit

![micro:bit attached to micro USB cable image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/connect-micro-bit.png)

## Now let's connect and attach the micro:bit @showhint

Let's get the micro:bit connected to the computer again:
- plug the micro:bit into the micro USB cable
- plug the other end into the computer
- click the "..." at the bottom left of the screen, next to the "Download" button
- select "Connect device"
- select your micro:bit ("BBC micro:bit CMSIS-DAP")
- then select "Connect"

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

## Now let's write another program @showhint

Let's program the micro:bit again:
- remove the ``||basic:on start||`` block & the ``||basic.forever||`` block by dragging them over to tool bar (to the left where the blocks are). When you drag them over o the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!
- select ``||input. Input||`` and drag out a ``||input.on button A ▼ pressed||`` block
- then select ``||basic: Basic||`` and drag out the ``||basic:show icon ♥ ▼||`` block
- place it inside the ``||input.on button A ▼ pressed||`` block
- hit the "Download" button at the bottom of the screen to flash your program to the micro:bit
- your program will not run until you hit the "A" button on your micro:bit

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Heart)
})
```

## Let's make a pattern, just like in math class! @showhint

You can use the ``||basic:show icon ♥ ▼||`` block to show different pictures. Lets place 3 different icons into the ``||input.on button A ▼ pressed||`` block.
- you already have a ``||basic:show icon ♥ ▼||`` block
- now go back to ``||basic: Basic||`` to add a 2nd ``||basic:show icon ♥ ▼||`` block and place it after your first one
- change the icon to a ``||basic:show icon ☺ ▼||``
- now go back to ``||basic: Basic||`` to add a 3rd ``||basic:show icon ♥ ▼||`` block and change the icon to a ``||basic:show icon ✓ ▼||``
- hit the "Download" button at the bottom of the screen to flash your program to the micro:bit
- your program will once again run when you press the "A" button on your micro:bit

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Heart)
    basic.showIcon(IconNames.Happy)
    basic.showIcon(IconNames.Yes)
})
```

## Too fast! @showhint

You will notice the images change very fast. You can slow that down by adding in a delay.
- select ``||basic: Basic||``, then the ``||basic.pause ms(100)||`` block
- place it after your ``||basic:show icon ♥ ▼||`` block
- now change the "100" to "1000", meaning 1 second
- repeat this after each ``||basic:show icon||`` block

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Heart)
    basic.pause(1000)
    basic.showIcon(IconNames.Happy)
    basic.pause(1000)
    basic.showIcon(IconNames.Yes)
    basic.pause(1000)
})
```

## Clear the screen

You might want to clear the screen at the end of your sequence
- select ``||basic: Basic||`` and drag out the ``||basic.basic.clearScreen()||`` block and place it at the end

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Heart)
    basic.pause(1000)
    basic.showIcon(IconNames.Happy)
    basic.pause(1000)
    basic.showIcon(IconNames.Yes)
    basic.pause(1000)
    // @highlight
    basic.clearScreen()
})
```

## Run it again

Let's run your program again:
- press the "reset" button on the back of the micro:bit
- your program should start over again, once you press the "A" button

## All done

**All Done.**

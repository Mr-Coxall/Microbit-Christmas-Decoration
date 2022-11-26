# lesson-02

## Last Time

![micro:bit attached to micro USB cable image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/connect-micro-bit.png)

Last time we went over:
- what is a micro:bit
- attaching the micro:bit to the computer
- connecting the micro:bit to the computer
- wrote a program
- flashing it to the micro:bit
- ran the program on the micro:bit

## Now let's connect and attach the micro:bit @showhint

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

Let's get the micro:bit connected to the computer again:
- plug the micro:bit into the micro USB cable
- plug the other end into the computer
- click the "..." at the bottom left of the screen, next to the "Download" button
- select "Connect device"
- select your micro:bit ("BBC micro:bit CMSIS-DAP")
- then select "Connect"

## Now let's write another program

Let's program the micro:bit again:
- remove the ``||basic:on start||`` block & the ``||basic.forever||`` block by dragging them over to tool bar (to the left where the blocks are)
- now select "Input" and drag out a ``||input.on button A ▼ pressed||`` block
- then click and drag out the ``||basic:show icon ♥ ▼||`` block
- place it inside the ``||input.on button A ▼ pressed||`` block
- hit the "Download" button at the bottom of the screen to flash your program to the micro:bit
- now your program will not run until you hit the "A" button!

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Heart)
})
```

## Let's make a pattern, just like in math class!

You can use the ``||basic:showIcon()||`` block to show different pictures. Lets place 3 different icons into the ``||input.on button A ▼ pressed||`` block.
- you already have a ``||basic:show icon ♥ ▼||`` block
- now add an 2nd ``||basic:show icon ♥ ▼||`` block and place it after your first one
- change the icon to a ``||basic:show icon ☺ ▼||``
- now add an 3rd ``||basic:showIcon()||`` block and change the icon to a ``||basic:show icon ✓ ▼||``
- then flash your new program and hit the "A" button again

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Heart)
    basic.showIcon(IconNames.Happy)
    basic.showIcon(IconNames.Yes)
})
```

## Too fast!

You will notice the images change very fast. You can slow that down by adding in a delay. 
- select "Basic", then the ``||basic.pause ms(100)||`` block
- place it after your ``||basic:show icon ♥ ▼||`` block
- now change the "100" to "1000", meaning 1 second
- repeat this afer each ``||basic:show icon||`` block

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Heart)
    basic.pause(1000)
    basic.showIcon(IconNames.Happy)
    basic.pause(1000)
    basic.showIcon(IconNames.Yes)
    basic.pause(1000)
})
```

## Run it again!

Let's run your program again:
- hit the "reset" button on the back of the micro:bit
- your program should start over again

## All done

**All Done.**

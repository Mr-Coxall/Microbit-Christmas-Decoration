# Lesson #03

## Last Time @unplugged

Last time we went over:
- how to attach a sequence of blocks together to show a pattern

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

## Let's connect and attach up the micro:bit @showhint

Let's get the micro:bit connected to the computer again:
- plug the micro:bit into the micro USB cable
- plug the other end into the computer
- click the "..." at the bottom left of the screen, next to the "Download" button
- select "Connect device"
- select your micro:bit ("BBC micro:bit CMSIS-DAP")
- then select "Connect"

![micro:bit connecting image](https://raw.githubusercontent.com/Mr-Coxall/Microbit-Christmas-Decoration/master/docs/static/pair.png)

## Now let's write another program

Let's try some new blocks:
- remove the ``||basic:on start||`` block & the ``||basic.forever||`` block by dragging them over to tool bar (to the left where the blocks are). When you drag them over to the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!
- select ``||input. Input||`` and drag out a ``||input.on shake ▼||`` block
- click the "▼" and select "tilt left"
  - it should look like: ``||input.on tile left ▼||``
- select "Basic" and drag out the ``||basic:show arrow (North) ▼||`` block
- place it inside the ``||input.on tile left ▼||`` block
- select the "▼" on the ``||basic:show arrow (North) ▼||`` block and choose "West"
  - it should look like: ``||basic:show arrow (West) ▼||``
- select ``||input. Input`` and drag out another ``||input.on shake ▼||`` block
- click the "▼" and select "tilt right"
  - it should look like: ``||input.on tilt right ▼||``
- select ``||basic: Basic`` and drag out the ``||basic:show arrow (North) ▼||`` block
- place it inside the ``||input.on tilt right ▼||`` block
- select the "▼" on the ``||basic:show arrow (North) ▼||`` block and choose "East"
  - it should look like: ``||basic:show arrow (East) ▼||``
- hit the "Download" button at the bottom of the screen to flash your program to the micro:bit
- run your progrm by pressing the "A" button on your micro:bit and watch the arrow move back and forth when you tilt the micro:bit!

```blocks
// @highlight
input.onGesture(Gesture.TiltLeft, function () {
    basic.showArrow(ArrowNames.West)
})
input.onGesture(Gesture.TiltRight, function () {
    basic.showArrow(ArrowNames.East)
})
```

## Let's make another pattern, just like in math class!

The goal is to make a pattern on the micro:bit and then show the pattern to your partner. Their job is to tell you the pattern. To help them learn the pattern you will show it 4 times!

- to begin with remove all the blocks by dragging them over to tool bar (to the left where the blocks are). When you drag them over to the toolbar it will turn red and a grabage can shows up. That's okay! You are in the right spot!

## Let's make another pattern, just like in math class! @showhint

- select ``||input. Input`` and drag out a ``||input.on button A ▼ pressed||`` block
- select ``|| loops. Loops`` and drag out a ``|| loops.repeat (4)times ||`` block and place it inside the ``||input.on button A ▼ pressed||`` block 

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
    
    }
})
```
## Let's make another pattern, just like in math class!

- select ``||basic: Basic`` add in a ``||basic:show icon ♥ ▼||`` block and place it inside the ``||loops.repeat||`` block
- now change the icon to something you would like!
- select ``||basic: Basic`` add in a ``||basic.pause ms(100)||`` block and change the "100" to "1000", meaning 1 second
- now repeat this 2 more times, creating a pattern you would like
- at the bottom of your loop add in a ``||basic:show leds||`` block to clear the screen at the end

```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        basic.showIcon(IconNames.Square)
        basic.pause(1000)
        basic.showIcon(IconNames.LeftTriangle)
        basic.pause(1000)
        basic.showIcon(IconNames.Sad)
        basic.pause(1000)
    }
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        `)
})
```

## Let's make another pattern, just like in math class!

- hit the "Download" button at the bottom of the screen to flash your program to the micro:bit
- show the micro:bit to your partner and press the "A" button on your micro:bit
  - can they tell you what the pattern is?

## All done

**All Done.**

(04_deployment)=
# Connecting the Trilobit and Start Recording

```{admonition} What You Need
:class: tip
**Hardware**

- Blue Motherboard/Control Unit
- GPS antenna with cable
- 2 COM to USB cable
- The R-Puck
- The UNIS Geophone Laptop
- 6 mm Hex Allen Key
- Pliers

**Software (should be on the Laptop)**

- EDR208
- Notepad ++
```

## Establishing Connection

1.  Start by laying out all the devices and cables:

```{image} assets/word_image12.jpg
:width: 376px
```

2.  Connect cables as shown and press the “ON-Button” on the back-side of the Control Unit. Make sure, that the cable with the Zip-Tie goes in the correct spot

```{image} assets/word_image13.jpg
:width: 412px
```

```{image} assets/word_image14.jpg
:width: 412px
```

3.  Place the GPS-Receiver outside. When it catches signal there is a green light pulsing on the far left of the board.

```{image} assets/word_image16.jpg
:width: 265px
```

4.  The Control Unit should now look like this:

```{image} assets/word_image18.jpg
:width: 518px
```

5.  Connect the R-Puck to the front of the Motherboard. It can only go on one way and is secured with a lock ring.

```{image} assets/word_image20.jpg
:width: 501px
```

6.  Also connect the Laptop to the USB cable. Chose the USB-Port on the **left** side of the Laptop!!!

```{image} assets/word_image21.jpg
:width: 318px
```

7.  Open EDR208 and apply the following options:

```{image} assets/word_image22.jpg
:width: 460px
```

To calibrate the GPS the entire system should now rest active for at least 30 minutes before continuing. In the meantime:

8.  Lift up the hood of the trilobit as explained in the previous chapter and pop of the white plastic caps of the battery housings and cables. Especially for the cable you might need a good pair of pliers.

9.  Make sure that there is an O-ring on both, the battery compartment and the cable as shown in the picture

```{image} assets/word_image23.jpg
:width: 247px
```

10. Connect the cables as shown, they can only go on one way. Press them on firmly and secure them with the copper nut. There shouldn’t be any visible threats left.

```{image} assets/word_image24.jpg
:width: 354px
```

11. After that you can take the R-Puck and place it on top of the Trilobit like shown. A red light should flash and blink every couple of seconds. You may need to press the button on the side of the R-Puck to activate it.

```{image} assets/word_image25.jpg
:width: 482px
```

12. Go into the EDR-program and press “Send” and then “Inq_Revs” in the current panel.

```{image} assets/word_image26.jpg
:width: 292px
```

13. Following output should appear, showing you the Firmware and Serial Number and some other stuff.

```{image} assets/word_image27.jpg
:width: 434px
```

```{admonition} Attention
:class: danger
Sometimes that does not work and you only get the first 2 lines, in that case remove the R-Puck and restart the blue control unit and EDR. Note that EDR should be run as Administrator at any time!
```

14. You can also press “Send” and then “Inq_vTemp” to get information about temperature and voltage. If the aforementioned outputs worked it means that the connection is established successfully. At this point all lights should be green on the control unit.

```{image} assets/word_image28.jpg
:width: 391px
```

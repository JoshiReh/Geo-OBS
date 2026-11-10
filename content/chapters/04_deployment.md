(04_deployment)=
# Connecting the Trilobit

```{admonition} What You Need
:class: tip
**Hardware**

- Blue control unit (motherboard)
- GPS antenna with cable
- 2 COM-to-USB cables
- R-Puck
- UNIS geophone laptop
- 6 mm hex Allen key
- Pliers

**Software (installed on the laptop)**

- EDR208
- Notepad++
```

## Establishing the Connection

1. Lay out all devices and cables.

   ```{image} assets/word_image12.jpg
   :alt: Devices and cables laid out
   :height: 400px
   :align: center
   ```

2. Connect the cables as shown and press the ON button on the back of the control unit. Make sure that the cable with the zip tie goes into the correct port.

   ```{image} assets/word_image13.jpg
   :alt: Cables connected to the control unit
   :height: 400px
   :align: center
   ```

3. Place the GPS receiver outside. As soon as it receives a signal, a green light starts pulsing on the far left of the board.

   ```{image} assets/word_image16.jpg
   :alt: GPS receiver placed outside
   :height: 400px
   :align: center
   ```

4. The control unit should now look like this:

   ```{image} assets/word_image18.jpg
   :alt: Control unit with GPS signal
   :height: 400px
   :align: center
   ```

5. Connect the R-Puck to the front of the control unit. It only fits one way and is secured with a lock ring.

   ```{image} assets/word_image20.jpg
   :alt: R-Puck connected to the control unit
   :height: 400px
   :align: center
   ```

6. Connect the USB cable to the laptop. Use the USB port on the **left** side of the laptop!

   ```{image} assets/word_image21.jpg
   :alt: USB cable connected to the left port of the laptop
   :height: 400px
   :align: center
   ```

7. Open EDR208 and apply the following settings:

   ```{image} assets/word_image22.jpg
   :alt: EDR208 settings
   :height: 400px
   :align: center
   ```

```{admonition} GPS Calibration
:class: note
To calibrate the GPS, the whole system has to run for at least **30 minutes** before you continue. Use this time for steps 8 to 10.
```

8. Lift the hood of the Trilobit as explained in {ref}`03_preparation` and pull off the white plastic caps of the battery housings and of the cables. For the cable caps you may need a good pair of pliers.

9. Make sure that there is an O-ring on both the battery compartment and the cable, as shown in the picture.

   ```{image} assets/word_image23.jpg
   :alt: O-ring on the cable connector
   :height: 400px
   :align: center
   ```

10. Connect the cables as shown. They only fit one way. Press them on firmly and secure them with the copper nut. No thread should be visible afterwards.

   ```{image} assets/word_image24.jpg
   :alt: Cables connected and secured with the copper nut
   :height: 400px
   :align: center
   ```

11. Place the R-Puck on top of the Trilobit as shown. A red light should flash every few seconds. You may need to press the button on the side of the R-Puck to activate it.

   ```{image} assets/word_image25.jpg
   :alt: R-Puck placed on top of the Trilobit
   :height: 400px
   :align: center
   ```

12. In EDR208, press “Send” and then “Inq_Revs” in the current panel.

   ```{image} assets/word_image26.jpg
   :alt: Inq_Revs command in EDR208
   :height: 400px
   :align: center
   ```

13. The following output should appear. It shows the firmware versions, the serial number and some further information.

   ```{image} assets/word_image27.jpg
   :alt: Output of Inq_Revs
   :height: 400px
   :align: center
   ```

```{admonition} Attention
:class: danger
Sometimes this does not work and you only get the first two lines. In that case, remove the R-Puck and restart both the blue control unit and EDR208. Always run EDR208 as administrator!
```

14. You can also press “Send” and then “Inq_vTemp” to get the temperature and the battery voltage. If both outputs appear, the connection is established. All lights on the control unit should now be green.

   ```{image} assets/word_image28.jpg
   :alt: Output of Inq_vTemp
   :height: 400px
   :align: center
   ```

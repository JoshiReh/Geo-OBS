(05_recovery)=
# Stopping the Trilobite and retrieving the Data

Hardware you need:

- Blue Motherboard/Control Unit

- GPS antenna with cable

- 2 COM to USB cable

- Data to USB cable

- The R-Puck

- The UNIS Geophone Laptop

- 6 mm Hex Allen Key

Software you need (should be on the Laptop):

- EDR208

- Notepad ++

- Windows Powershell

## Stopping the Trilobite and correcting the time

This step is needed to correct the internal clock of the Trilobite which has a little bit of a drift especially after long deployments.

1.  Setup everything as in the chapter before: Connect all cables, locate the GPS, let it calibrate for 30 minutes and connect the laptop.

2.  Start the EDR as Administrator and place the R-Puck on the Geophone. You can press “Send” and “Inq_Recording” to make sure it is still recording.

3.  Go to the panel “Script/Log” and create a stopping Log-file that will store important information that you might need later.

4.  Now load the file “Svalbard_STOP_rec” and press “Open”.

```{image} assets/word_image33.png
:width: 409px
```

5.  Again, set the delay to 2 seconds and press “Send”. Wait until everything has run.

6.  The recording should now be set to inactive. You can check again by “Inq_Recording” as previously explained.

7.  You can now remove the R-Puck and turn of the blue control unit, disconnect the laptop and all other wires.

8.  Finally, take of the hood of the Trilobite and disconnect the batteries. Put the white plastic caps back on the wires and battery compartments.

(05_recovery)=
# Stopping the Trilobit and Correcting the Time

```{admonition} What You Need
:class: tip
**Hardware**

- Blue control unit (motherboard)
- GPS antenna with cable
- 2 COM-to-USB cables
- Data-to-USB cable
- R-Puck
- UNIS geophone laptop
- 6 mm hex Allen key

**Software (installed on the laptop)**

- EDR208
- Notepad++
- Windows PowerShell
```

This step is needed to correct the internal clock of the Trilobit, which drifts slightly, especially during long deployments.

1.  Set up everything as described in {ref}`04_deployment`: connect all cables, place the GPS receiver outside, let it calibrate for 30 minutes and connect the laptop.

2.  Start EDR208 as administrator and place the R-Puck on the Trilobit. You can press “Send” and “Inq_Recording” to make sure that it is still recording.

3.  Go to the “Script/Log” panel and create a log file for stopping. It stores important information that you might need later.

4.  Load the file “Svalbard_STOP_rec” and press “Open”.

```{image} assets/word_image33.png
:width: 409px
```

5.  Again, set the delay to 2 seconds and press “Send”. Wait until all commands have run.

6.  The recording should now be inactive. You can check this again with “Inq_Recording”, as explained above.

7.  Remove the R-Puck, turn off the blue control unit, and disconnect the laptop and all other cables.

8.  Finally, take off the housing of the Trilobit and disconnect the batteries. Put the white plastic caps back on the cables and battery compartments.

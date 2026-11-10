(04_start_recording)=
# Start Recording

Make sure that the connection to the Trilobit is established as described in {ref}`04_deployment`.

1. Go to the “Script/Log” panel in EDR208.

   ```{image} assets/word_image29.jpg
   :alt: Script/Log panel in EDR208
   :height: 400px
   :align: center
   ```

2. Press “Open Log File” and create a log file in a folder of your choice, ideally with a name like “Start_1069_Log”. The log file saves the commands and their output, so you keep a record of the chosen sampling rate, the temperature and voltage at the start, and the exact time the recording started. This is important when you work with the data later.

3. Press “Send” and select the file “Svalbard_START_rec” in the “Trilobit” folder.

   ```{image} assets/word_image30.png
   :alt: Selecting the start script
   :height: 400px
   :align: center
   ```

4. Set *Seconds Delay between each Script Command* to “2”. This makes sure that all script commands for starting the Trilobit are read in correctly.

   ```{image} assets/word_image31.jpg
   :alt: Setting the delay between script commands
   :height: 400px
   :align: center
   ```

5. Press “Send” and **wait** until this output has appeared about three times:

   ```{image} assets/word_image32.jpg
   :alt: Output after starting the recording
   :height: 400px
   :align: center
   ```

6. The Trilobit is now recording, and you can press “Close Log File”. To double-check, go to the “EDR Cmd” panel, press “Send” and choose “Inq_Recording”. This shows whether the recording is active and when it started (in UTC).

7. Lift off the R-Puck. You can now either program the next Trilobit or switch off the control unit and the laptop.

```{admonition} Note the Times
:class: tip
Write down the **start time** of the recording yourself, and especially the **deployment** and **recovery** times. You will need them for the data processing.
```

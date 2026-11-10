(04_start_recording)=
# Start Recording

Make sure that the connection to the Trilobit is established as described in {ref}`04_deployment`.

1. Go to the panel Script/Log in EDR

```{image} assets/word_image29.jpg
:width: 361px
```

2. Press “Open Log file” and create a Log file in a folder you desire, ideally calling it something like “Start_1069_Log”. This will just save some commands so you get information about the sampling rate you chose, the temperature and voltage in the beginning and the moment where you started the recording that can be important when working with the data.

3. Press “Send” and select the file “Svalbard_START_rec” in the “Trilobit”-folder.

```{image} assets/word_image30.png
:width: 347px
```

4. Finally Set the *Seconds Delay between each Script Command* to “2”. This will make sure that all scripts for starting and operating the Trilobit will be read in correctly.

```{image} assets/word_image31.jpg
:width: 349px
```

5. Press “Send” and **wait** until you get this output about 3 times:

```{image} assets/word_image32.jpg
:width: 395px
```

6. Your Trilobit is now running and you can press “Close Log File”. To double check you can go into the start panel “EDR Cmd” and “Send” “Inq_Recording”, which will show you again if the recording is active (in UTC).

7. You can now lift up the R-Puck and either start programming the next Trilobit or turn of the control unit and your laptop.

```{admonition} Just for Your Reference
:class: tip
I would recommend that you write down the **start time** yourself and especially the **deployment**- and the **pick-up** time. You will need that for your data processing.
```

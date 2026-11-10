(06_data)=
# Downloading the Raw Data

```{admonition} Attention
:class: danger
Follow these instructions precisely. It is very easy to mess something up if one step is not executed properly.
```

Make sure that the batteries are **disconnected** before you start the download.

1.  Remove the copper cap from the data unit.

```{image} assets/word_image34.jpg
:width: 349px
```

2.  Connect the data cable and screw on its copper nut so that it is firmly attached to the data unit.

```{image} assets/word_image35.jpg
:width: 349px
```

3.  Connect the USB end of the cable to the **right side** of the laptop. As usual when you plug a device into a PC, a window will appear. **You have to press “Cancel”, “OK”, “Cancel”.**

```{image} assets/word_image36.jpg
:width: 279px
```

```{image} assets/word_image37.jpg
:width: 369px
```

```{image} assets/word_image38.jpg
:width: 227px
```

4.  If you haven’t already, open EDR208 as administrator and go to the “Raw dev” panel. Press “Start Raw Routine” and create a new file by choosing a storage location and entering a name. In this example, the raw file is called “Demonstration”. Click “Save”.

```{image} assets/word_image39.jpg
:width: 273px
```

5.  In the Windows Explorer, check that the file contains data. Depending on the recording length, it can be several GB.

6.  In this very important step, copy all files from the folder “Files to copy into new data folder” into the folder where your raw file is located. Most of these files are used by the scripts that you run in the next steps.

```{image} assets/word_image40.jpg
:width: 519px
```

7.  Open Windows PowerShell as administrator and navigate to the folder. In this example, it looks like this:

```{image} assets/word_image41.jpg
:width: 338px
```

````{admonition} New to the Terminal?
:class: tip
If you have never used a terminal before: use “cd” to go into a folder, e.g. “cd \next folder\data”. To go back from “data” to “next folder”, use “cd ..”. To list all files in a folder, type “ls”. You should be able to copy and paste the following commands to get to the Trilobit folder once you have opened PowerShell:

```powershell
cd ..
cd ..
cd \Users\unisg\Desktop\Trilobit\Data\
```
````

8.  As shown in the last picture, type “.\fix_all_ln.ps1” and press Enter. This creates a new file with exactly the same name as your raw file and renames the original file to “old_xxx”. In this example, the file is still called “Demonstration”, and there is also a file “old_demonstration”, which can be **deleted**. If an error occurs, type `Set-ExecutionPolicy Unrestricted` in PowerShell and try again.

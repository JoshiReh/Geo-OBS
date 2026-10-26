(06_data)=
# Downloading the Raw Data

```{admonition} Attention
:class: danger
Follow these instructions precisely. It is very easy to mess something up if one step is not executed properly.
```

Make sure that the batteries are **disconnected** before starting the Downloading Process.

1.  Remove the copper cap from the data unit.

```{image} assets/word_image34.jpg
:width: 349px
```

2.  You can now connect the data cable and screw on its copper nut, so that it is firmly attached to the data unit.

```{image} assets/word_image35.jpg
:width: 349px
```

3.  Connect the USB end of the cable to the **right side** of the Laptop. As usual when plugging in a device into a PC, a window will appear. **You have to press “Cancel”, “OK”, “Cancel”.**

```{image} assets/word_image36.jpg
:width: 279px
```

```{image} assets/word_image37.jpg
:width: 369px
```

```{image} assets/word_image38.jpg
:width: 227px
```

4.  If you haven’t already, open EDR as Administrator and navigate to the Panel “Raw dev”. Press the button “Start Raw Routine” and create a new file by simply choosing a location to store and writing your desired name. In this case, I named the Raw-file “Demonstration”. Click “Save”.

```{image} assets/word_image39.jpg
:width: 273px
```

5.  In your Explorer, check that the file contains data. Depending on the recording length, it can be multiple GB.

6.  In this very important step, you have to copy all files that are in the folder “Files to copy into new data folder”, into the folder where your Raw file is located. Most of the files will be used by a couple scripts that you have to run in the next few steps.

```{image} assets/word_image40.jpg
:width: 519px
```

7.  Open Windows Powershell as Administrator and navigate to the folder. In my case it looks like this:

```{image} assets/word_image41.jpg
:width: 338px
```

````{admonition} New to the Terminal?
:class: tip
If you have never used any terminal like bash before, use “cd” to go to the next folder like “cd \next folder\data”. If you want to jump back from “data” to “next folder” use the command “cd ..”. To list all files in one folder press “ls”. You should be able to copy paste the following commands to get to the Trilobit folder once you open powershell:

```powershell
cd ..
cd ..
cd \Users\unisg\Desktop\Trilobit\
```
````

8.  As seen in the last picture write “.\fix_all_ln.ps1” and press “enter”. This will create a new file that has exactly the same name as you named it and will re-name your original file into “old_xxx”. In my case my file is still called “Demonstration” but I also have the file “old_demonstration” which I can **delete**. You may have to type `Set-ExecutionPolicy Unrestricted` in the powershell when an error occurs before trying again.

```{admonition} Attention
:class: danger
If your file is **larger** than 2 GB, you cannot continue directly with {ref}`06_decoding`. First you have to **Chunk** the file into subfiles, which is explained in {ref}`06_chunking`!
```

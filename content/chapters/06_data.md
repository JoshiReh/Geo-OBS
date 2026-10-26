(06_data)=
# Downloading and Converting the Data

Follow these instructions precisely. It is very easy to mess something up if one step is not executed properly.

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

If you have never used any terminal like bash before, use “cd” to go to the next folder like “cd \next folder\data”. If you want to jump back from “data” to “next folder” use the command “cd ..”. To list all files in one folder press “ls”. You should be able to copy paste the following commands to get to the Trilobite folder once you open powershell:

```powershell
cd ..
cd ..
cd \Users\unisg\Desktop\Trilobit\
```

8.  As seen in the last picture write “.\fix_all_ln.ps1” and press “enter”. This will create a new file that has exactly the same name as you named it and will re-name your original file into “old_xxx”. In my case my file is still called “Demonstration” but I also have the file “old_demonstration” which I can **delete**. You may have to type «*Set-**ExecutionPolicy Unrestricted*” in the powershell when an error occurs before trying again.

If your file is **larger** then 2GB the following steps are not relevant and you have to **Chunk** the file into subfiles, which is explained in {ref}`06_chunking`!

9.  Go back into EDR. Still in the panel “Raw Dev” set the “Operation” to “Scan Raw” and select your raw dataset as you named it in Step 4.

10. The panel in EDR should show you when the dataset started and when it stopped.

```{image} assets/word_image42.jpg
:width: 466px
```

11. Now select Operation “Decode Raw”. This should produce 9 new files: 4 .aux files (where aux0 is the temperature, aux1 is the voltage, and aux5 is the tilt) and 4 files .g1,.g2,.g3,.h1 that refer to our geophones and hydrophone in the trilobite. You will also get a text-file that you need later.

```{image} assets/word_image43.jpg
:width: 373px
```

```{image} assets/word_image44.jpg
:width: 411px
```

12. You now need to return to Windows Powershell and execute the following commands:

    1.  `.\get_skew.ps1` (note down the number!)

    2.  `type .\xxx_seq1.txt` (for xxx insert your file name)

```{image} assets/word_image45.jpg
:width: 477px
```

13. You have to focus on the following numbers:

```{image} assets/word_image46.png
:width: 406px
```

14. Go into the Windows explorer and open the “Trilobit_SHT”-file with Notepad ++. Here you enter the Start end End-time that you just read from the txt file in powershell. Leave the last digit as “0” in both rows. Note that the digits are separated by a **tab** and not a **space**.

```{image} assets/word_image47.jpg
:width: 459px
```

15. Press Save and close, then open “Trilobit_RCV”. Here you enter the Skew number, aswell as the Unit Serial Number and the Trilobite number. You just do that in the first row and ignore the other columns. So just adjust the first 3 numbers in row 6! Also here, the digits are separated by a **tab** and not a **space**; that’s why it looks a bit weird in the picture below.

```{image} assets/word_image48.jpg
:width: 519px
```

16. The very last step is now to go back into EDR208 and change the operation to “Seis to SEGY”.

```{image} assets/word_image49.jpg
:width: 428px
```

17. Click on “Start Conversion” and select any of the 4 files you should see now (it will automatically convert the other files as well. You will then be requested to enter the previously modified RCV and SHT file and finally you enter the “header_edr” file.

**It happens quite easily that you did not save the RCV or SHT file correctly or had a type in it. Then the conversion will cancel and you should revisit those files.**

```{image} assets/word_image50.jpg
:width: 519px
```

```{image} assets/word_image51.jpg
:width: 520px
```

(06_displaying)=
## Displaying the Data

UNIS has a license to the GeoGiga Software in Computer Lab 2, which is commonly used for showing and analyzing seismic data. However, GeoGiga is unfortunately not opening the files produced by EDR208 because the “Binary-Header” is writing false values into the file. For repairing the data, we have developed a python script that is repairing the data, see {ref}`08_binary_header`.

In the meantime, you can use the software “SeiSee” which is installed on the Laptop. The data sometimes does not appear directly in the view-panel or it looks broken. Try to experiment with these parameters:

```{image} assets/word_image52.jpg
:width: 300px
```




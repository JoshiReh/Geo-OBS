(06_segy)=
# Converting the Data into SEG-Y Files

The raw file has to be decoded first, see {ref}`06_decoding`.

1. Return to Windows PowerShell and run the following commands:

    1.  `.\get_skew_new.ps1` (write down the number!)

    2.  `type .\xxx_seq1.txt` (for xxx insert your file name)

```{image} assets/word_image45.jpg
:width: 477px
```

2. Look for the following numbers:

```{image} assets/word_image46.png
:width: 406px
```

3. In the Windows Explorer, open the file “Trilobit_SHT” with Notepad++. Enter the start and end time that you just read from the .txt file in PowerShell. Leave the last digit as “0” in both rows. Note that the numbers are separated by a **tab**, not a **space**.

```{image} assets/word_image47.jpg
:width: 459px
```

4. Save and close the file, then open “Trilobit_RCV”. Enter the unit serial number (1st number after RC), the Trilobit number (2nd number) and, instead of “Auto”, the skew number. Only change the first row and ignore the others. So you only adjust the 1st, 2nd and 4th number in row 6! Here, too, the numbers are separated by a **tab**, not a **space**, which is why it looks a bit odd in the picture below.

```{image} assets/word_image48.jpg
:width: 519px
```

5. As the very last step, go back to EDR208 and change the operation to “Seis to SEGY”.

```{image} assets/word_image49.jpg
:width: 428px
```

6. Click “Start Conversion” and select any of the 4 files you now see (the other files are converted automatically as well). You are then asked for the RCV and SHT files you just edited, and finally for the “header_edr” file.

**It happens easily that the RCV or SHT file was not saved correctly or contains a typo. In that case, the conversion is cancelled and you should check those files again.**

```{image} assets/word_image50.jpg
:width: 519px
```

```{image} assets/word_image51.jpg
:width: 520px
```

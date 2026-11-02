(06_segy)=
# Converting the Data into SEG-Y Files

The raw file has to be decoded first, see {ref}`06_decoding`.

1. You now need to return to Windows Powershell and execute the following commands:

    1.  `.\get_skew_new.ps1` (note down the number!)

    2.  `type .\xxx_seq1.txt` (for xxx insert your file name)

```{image} assets/word_image45.jpg
:width: 477px
```

2. You have to focus on the following numbers:

```{image} assets/word_image46.png
:width: 406px
```

3. Go into the Windows explorer and open the “Trilobit_SHT”-file with Notepad ++. Here you enter the Start end End-time that you just read from the txt file in powershell. Leave the last digit as “0” in both rows. Note that the digits are separated by a **tab** and not a **space**.

```{image} assets/word_image47.jpg
:width: 459px
```

4. Press Save and close, then open “Trilobit_RCV”. Here you enter the Unit Serial Number (1st number after RC), the Trilobit number (2nd number) and finally instead of Auto the Skew number. You just do that in the first row and ignore the other columns. So just adjust the first 2 and the 4th number in row 6! Also here, the digits are separated by a **tab** and not a **space**; that’s why it looks a bit weird in the picture below.

```{image} assets/word_image48.jpg
:width: 519px
```

5. The very last step is now to go back into EDR208 and change the operation to “Seis to SEGY”.

```{image} assets/word_image49.jpg
:width: 428px
```

6. Click on “Start Conversion” and select any of the 4 files you should see now (it will automatically convert the other files as well. You will then be requested to enter the previously modified RCV and SHT file and finally you enter the “header_edr” file.

**It happens quite easily that you did not save the RCV or SHT file correctly or had a type in it. Then the conversion will cancel and you should revisit those files.**

```{image} assets/word_image50.jpg
:width: 519px
```

```{image} assets/word_image51.jpg
:width: 520px
```

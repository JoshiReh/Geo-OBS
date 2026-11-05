(10_app_route)=
# Alternative: The Trilobit Processor App

The Trilobit Processor app replaces everything **after "Decode Raw"**: the skew readout, the SHT/RCV files, EDR's "Seis to SEGY" export with drift correction, the chunking and the notebooks of Session 6 (header correction and daily SEG-Y files). Sessions 1-4 and the download, `fix_all` and "Decode Raw" steps of Session 5 stay the same.

```{admonition} Under construction
:class: warning
This route is still being tested. The app reproduces EDR's SEG-Y output sample by sample, but please compare with the classic route before relying on it.
```

## What You Need

- The decoded files of one recording: `.g1 .g2 .g3 .h1`, the `.aux` files and the `_seq1.txt` file from "Decode Raw".
- Optional: the `.raw` file in the same folder. The app reads the skew from the decoded files and uses the `.raw` file only as a cross-check.
- The Trilobit Processor app on a Mac.

## Workflow

1. Download the data, run `fix_all` and "Decode Raw" as described in {ref}`06_data` and {ref}`06_decoding`. Decode the **whole** raw file, no chunking needed.
2. Copy the folder with the decoded files to the Mac. The folder and file names can be anything, as long as they contain the 4-digit station number (e.g. `full0989`).
3. Open the app and drop the folder into the window.
4. Choose the segment length (e.g. 24 h) and, if you want to cut away transport and deployment, a **start and end time in UTC** (e.g. `2026-07-07 16:00`).
5. Press "Check and process". The app first checks the data (gaps, skew, serial number) and then writes the segment files into a `DailyChunk` folder next to the data. A report is written into the input folder.

```{admonition} Good to Know
:class: tip
The app also writes `<station>_aux_per_minute.csv` with the accelerometer values, the tilt of the Trilobit, the battery voltage and the temperature for every minute of the recording. This shows when the Trilobit settled on the seafloor and whether it tipped over.
```

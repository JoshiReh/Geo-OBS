(10_app_route)=
# Alternative: The Trilobit Processor App

The Trilobit Processor app replaces everything **after "Decode Raw"**: the skew readout, the SHT/RCV files, EDRTest208's "Seis to SEGY" export with drift correction, the chunking and the notebooks of Session 6 (header correction and daily SEG-Y files). Sessions 1–4 and the download, `fix_all` and "Decode Raw" steps of Session 5 stay the same.

```{admonition} Under Construction
:class: warning
This route is still being tested. The app reproduces EDRTest208's SEG-Y output sample by sample, but please compare with the classic route before relying on it.
```

## What You Need

- The decoded files of one recording: `.g1 .g2 .g3 .h1`, the `.aux` files and the `_seq1.txt` file from "Decode Raw".
- Optional: the `.raw` file in the same folder. The app reads the skew from the decoded files and uses the `.raw` file only as a cross-check.
- The Trilobit Processor app on a Mac (Apple Silicon) or a Windows PC, see below.

## Download

Download the latest version from the [Trilobit Processor releases](https://github.com/JoshiReh/trilobit-processor/releases/latest) on GitHub:

- **macOS** (Apple Silicon, M1 or newer): `TrilobitProcessor-mac.zip`
- **Windows** (10/11): `TrilobitProcessor-windows.zip`

The source code, the tests and the technical details are in the [trilobit-processor repository](https://github.com/JoshiReh/trilobit-processor).

```{admonition} First Start
:class: tip
The app is not signed, so your computer may block it the first time.

- **macOS:** right-click the app → *Open* → *Open*.
- **Windows:** unzip the whole folder, start `Trilobit Processor.exe`, and if a blue window appears click *More info* → *Run anyway*.
```

## Workflow

<video src="../../_static/trilobit_processor_howto.mp4" width="100%" autoplay loop muted playsinline controls></video>

1. Download the data, run `fix_all` and "Decode Raw" as described in {ref}`06_data` and {ref}`06_decoding`. Decode the **whole** raw file; no chunking is needed.
2. Copy the folder with the decoded files to the computer with the app (or run the app directly on the EDRTest208 PC with the Windows version). The folder and file names can be anything, as long as they contain the 4-digit station number (e.g. `full0989`).
3. Open the app and drop the folder into the window.
4. Choose the segment length (e.g. 24 h) and, if you want to cut away transport and deployment, a **start and end time in UTC** (e.g. `2026-07-07 16:00`).
5. Press "Check and process". The app first checks the data (gaps, skew, serial number) and lists the sample interval, the recording start and end and the new start and end. After 10 s it writes the segment files into a folder like `24hourChunks` next to the data. A report is written into the input folder.

```{admonition} Good to Know
:class: tip
The app also writes `<station>_aux_per_minute.csv` with the accelerometer values, the tilt of the Trilobit, the battery voltage and the temperature for every minute of the recording. This shows when the Trilobit settled on the seafloor and whether it tipped over.
```

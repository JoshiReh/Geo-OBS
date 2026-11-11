(08_segy_daily)=
# Cutting Long-Term SEG-Y Files into Daily Files

Notebook: [3_cut_daily_files.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/3_cut_daily_files.ipynb)

After step 2 every station has one file per component and per chunk folder, each about 1.7 GB for 10 days. Most analyses look at a few hours or one day, and reading 1.7 GB to plot one hour is slow. This notebook joins the chunk folders of a station (`1stChunk`, `2ndChunk`, ...) into one continuous recording and cuts it into files of one day, about 170 MB each:

```
<station>/DailyChunk/<station>_z_chunk0000_20260707T160000.segy
                     <station>_z_chunk0001_20260708T160000.segy
                     ...
```

The number after `chunk` counts the days from the start time you choose; the date is the start of the file in **UTC**.

In the cell **Settings** choose:

- `DATA_FOLDER` and `STATIONS`, as in step 2,
- `COMPONENTS`: usually all four, `["x", "y", "z", "h"]`,
- `START_LOCAL`: the start of the first file in local time. Use the deployment time rounded to the full hour; add some settling time if you want to leave out the first hour on the seafloor.
- `END_LOCAL`: `None` for the whole recording, or a time before the recovery,
- `HOURS_PER_FILE`: `24` for daily files, `1` for hourly files.

## How the time is kept right

Every input trace is placed at the time written in its own trace header, not simply appended to the previous one. If a minute is missing (for example between two EDR exports), the output contains zeros there and the notebook prints `WARNING: 59 s without data (zeros)`. If two chunks overlap, the doubled minutes land on the same place.

```{admonition} Why this matters
:class: tip
In 2026 one EDR export started one minute late. An earlier version of this notebook simply joined the traces, so the gap was closed and all later data of that station were 59 s too early. It was only noticed because the earthquake of 27 July 2026 seemed to arrive at that station almost a minute before the others. Always run step 1 (export check) and read the warnings of this notebook.
```

Only one output file is in memory at a time, so a normal laptop is enough. One station with four components and 27 days takes about 15 to 30 minutes on an external hard drive.

At the end the notebook plots the noise level and the maximum amplitude of every file. Use it to find quiet days, noisy days and days with large events, and look at them in detail with {ref}`08_segy_qc`.

(08_segy_qc)=
# SEG-Y QC Explorer

Notebook: [4_qc_daily_files.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/4_qc_daily_files.ipynb)

This notebook shows one day of one station and one component, so you can check that the data look like real seismic data and that the times are right. It reads the daily files from {ref}`08_segy_daily`.

In the cell **Settings** choose:

- `STATION`, e.g. `"0498"`,
- `COMPONENT`: `"x"`, `"y"`, `"z"` (geophones) or `"h"` (hydrophone),
- `TIME_LOCAL`: any time inside the day you want to see, in local time. The Trilobit records in UTC; `UTC_OFFSET_HOURS = 2` converts to Svalbard summer time.
- `ZOOM_MINUTES` and `FILTER_HZ` for the zoomed plots and the bandpass filter.

The notebook finds the right daily file by reading the trace times and prints how many traces contain no data at all. Then it plots:

1. **Raster plot of the whole day.** One row per 60 s trace, one pixel per second, color = loudness (RMS amplitude, log scale). Look for black rows (missing data), sudden jumps in the noise level and long noisy periods (ships, weather, tides).
2. **Wiggle plot** of a few minutes around `TIME_LOCAL`. Every trace is scaled to its own maximum, so you see the shape of the signals. Real ground motion is smooth with clear onsets; spikes of a single sample or flat lines are not data.
3. **Spectrogram** of the same minutes: which frequencies carry the energy. Constant horizontal lines are usually technical noise.
4. The raster and wiggle plots again after a **bandpass filter** (default 3-30 Hz).

The notebook on GitHub already shows the plots of station 0498, component z, on 9 July 2026, as an example of what good data look like.

```{note}
Geophone data often have a large constant offset (for 0498 z about -42 000 counts). This is normal. The raster plot removes the mean of every trace, and the bandpass filter removes it as well.
```

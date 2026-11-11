(08_binary_header)=
# Export Check and Binary Header Correction

## Step 1: Check the EDR export

Notebook: [1_check_edr_export.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/1_check_edr_export.ipynb)

Run this notebook directly after exporting the SEG-Y files from EDR. It only reads the first and the last trace header of every file, so it takes a few seconds. It catches two mistakes that happened in 2026 and that are invisible in the data:

- **A missing minute.** One export started at 16:00:59 instead of 16:00:00. The data of that station were later 59 s too early.
- **A wrong clock skew.** One chunk was exported with the skew of a different Trilobit in `Trilobit_RCV`, so its clock drift correction was wrong by about half a second.

The notebook checks, for every station, chunk and component:

1. no gap inside a file,
2. no gap between `1stChunk`, `2ndChunk`, ... (an overlap is fine),
3. `g1`, `g2`, `g3` and `h1` have the same start, end and number of traces,
4. the skew, serial number and station number in the trace headers are consistent (same skew in all chunks, equal to the `.raw` file, different from all other stations; serial number as in the EDR log; station number as the folder name).

If the last cell prints `All ... files OK`, continue with step 2. Otherwise export the chunk again in EDR and run the check again.

## Step 2: Repair the binary header

Notebook: [2_fix_header_and_xyz.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/2_fix_header_and_xyz.ipynb)

GeoGiga cannot open the SEG-Y files written by EDR208, because a few numbers in the binary header (bytes 3201-3600) are wrong. The most important one is the number of samples per trace: EDR writes `-2768` instead of `30000`. The notebook writes the correct values:

| Bytes | Field | Value |
|---|---|---|
| 3217-3218 | sample interval [µs] | 2000 |
| 3219-3220 | sample interval of the original recording [µs] | 2000 |
| 3221-3222 | samples per trace | 30000 |
| 3223-3224 | samples per trace of the original recording | 30000 |
| 3227-3228 | ensemble fold | 1 |
| 3229-3230 | trace sorting code | 1 (as recorded) |
| 3231-3232 | vertical sum code | 1 |
| 3235-3236 | sweep frequency at end [Hz] | 0 (no sweep) |
| 3255-3256 | measurement system | 1 (meters) |

Text header, trace headers and samples are not changed. The same notebook also converts the geophones to x, y and z, see {ref}`08_xyz_conversion`.

**Before you run it**, set in the cell **Settings**:

- `DATA_FOLDER`: the folder with one folder per station,
- `STATIONS`: the stations to process, e.g. `["0498"]`,
- `DELETE_RAW_FILES`: leave `False` for the first run.

The notebook writes `<station>_<chunk>_x.segy`, `_y.segy`, `_z.segy` and `_h.segy` into every chunk folder and checks that each new file has the same size and the same first and last trace time as its EDR file. One station takes about 10 to 20 minutes on an external drive. When you have looked at the result (step 4 or GeoGiga), you can set `DELETE_RAW_FILES = True` and run the notebook again to delete the EDR files. Converted chunks are then only checked, not converted again.

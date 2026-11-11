(08_python_processing)=
# Processing the Data with Python

After decoding and converting the data to SEG-Y in EDR (Session 5), the files still need a few Python steps before you can work with them. Each step is one Jupyter notebook. You only have to change the cell **Settings** at the top of each notebook, then run all cells from top to bottom.

All notebooks are in the folder [notebooks](https://github.com/JoshiReh/trilobit-processor/tree/main/notebooks) of the trilobit-processor repository on GitHub, next to the app ({ref}`10_app_route`). Open a notebook there and use the download button (*Download raw file*), or clone the whole repository with `git clone https://github.com/JoshiReh/trilobit-processor.git`.

| Step | Notebook | What it does | Chapter |
|---|---|---|---|
| 1 | [1_check_edr_export.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/1_check_edr_export.ipynb) | Checks the EDR export for gaps and wrong clock skew | {ref}`08_binary_header` |
| 2 | [2_fix_header_and_xyz.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/2_fix_header_and_xyz.ipynb) | Repairs the binary header and converts g1/g2/g3 to x/y/z | {ref}`08_binary_header`, {ref}`08_xyz_conversion` |
| 3 | [3_cut_daily_files.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/3_cut_daily_files.ipynb) | Joins the chunks and cuts them into daily files | {ref}`08_segy_daily` |
| 4 | [4_qc_daily_files.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/4_qc_daily_files.ipynb) | Plots one day to check the data quality | {ref}`08_segy_qc` |

## Folder structure

The notebooks expect one folder per station, with one subfolder per exported chunk:

```
DATA_FOLDER/
├── 0498/
│   ├── 1stChunk/   0498_1stChunk_seq1.g1_segy, ..._g2_segy, ..._g3_segy, ..._h1_segy, ..._seq1.txt
│   ├── 2ndChunk/
│   ├── 3rdChunk/
│   └── DailyChunk/ (written in step 3)
├── 0578/
...
```

## What you need

- Python 3 with `numpy`, `scipy`, `pandas`, `matplotlib` and `jupyter`. With conda:

  ```bash
  conda create -n trilobit python numpy scipy pandas matplotlib jupyterlab
  conda activate trilobit
  jupyter lab
  ```

- Enough free disk space: step 2 writes four new files of the same size as the EDR files (about 1.7 GB per file for 10 days). The EDR files are only deleted when you ask for it.
- An external drive is fine. The notebooks read the files in small blocks, so 8 GB of RAM are enough (step 4 needs about 2 GB for one day).

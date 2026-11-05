(06_chunking)=
# Chunking Large Files

```{admonition} Note
:class: warning
Whenever you record with the default settings shown in {ref}`04_start_recording` (same sampling interval etc.), you most likely have to chunk your files when you record for more than 10 days.
```

You should have a file that is already fixed with the command fix_all_ln as explained in {ref}`06_data`. If you follow the naming sceme of the next steps you can use the attached python files without any changes other than the data-path.

1.  In your “data” folder, create a folder calling it like the Trilobit you want to analyze the data from. In my example it is “1069”. Put the fixed Raw file into this folder.

2.  In this folder create one sub-folder per chunk and name them “1stChunk”, “2ndChunk”, … How many chunks you need follows from one rule: **after decoding, every single component file (g1, g2, g3, h1) has to be smaller than 2 GB.** The raw file contains all 4 components, so roughly:

    *size of one component ≈ size of the raw chunk ÷ 4*

    In our example the raw file of the whole 25-day deployment is 11.8 GB, which is about 0.47 GB per day. A 10-day chunk is therefore about 4.7 GB raw, or about 1.2 GB per component, which is safely below 2 GB. This gives us 3 chunks: 10 + 10 + 5 days.

3.  Go into the EDR program and in the “Convert” panel select “Extract raw”.

4.  Select the time and date for your first Chunk. We would recommend 10 days. (Here we would set the start at a time that was our starting time across all Data analysis. We deployed the Trilobits at 12:32 o’clock and I set the start time to 12:00 PM. UTC, so 14:00 in Svalbard summer time to let the sediment settle.)

5.  Check the box “use convert times” and press “start conversion”. Select the raw file first before going into your folder 1stChunk and create a new file and name it 1069_1stChunk. Press “send/okay”.

6.  Wait until that has worked and repeat for the next chunk. **Let every new chunk start 10 minutes before the previous chunk ended**, so that neighbouring chunks overlap by 10 minutes. The end time stays on your regular grid. In our case:

    | Chunk | Start (UTC) | End (UTC) |
    |---|---|---|
    | 1069_1stChunk | 07/01/2026 12:00 | 07/11/2026 12:00 |
    | 1069_2ndChunk | 07/11/2026 **11:50** | 07/21/2026 12:00 |
    | 1069_3rdChunk | 07/21/2026 **11:50** | end of recording |

7.  Repeat for all chunks until your previous raw-file is chunked into smaller, slightly overlapping files.

```{admonition} Good to Know: Skew and Why the Chunks Overlap
:class: tip
The internal clock of the Trilobit drifts slightly while it is on the seafloor. The difference between the Trilobit clock and the GPS time at the end of the deployment is called the **skew**. You read it out with `get_skew_new.ps1` and enter it in the RCV file, see {ref}`06_segy`, so that EDR can correct the time of every sample.

Because of this correction, the samples of a chunk do not sit exactly on the times you selected when you cut it. If two chunks met exactly at 12:00, a few samples right at the border could be lost. The 10 minutes overlap makes sure that no data is lost between two chunks. Keep in mind that these 10 minutes are then contained in two chunks, so remove the doubled part when you later combine the chunks again.
```

```{admonition} Good to Know
:class: tip
We deployed the Trilobits for about 25 days, so the last chunk was just 5 days long, which is totally fine for the rest of this workflow.
```

```{admonition} Attention
:class: danger
Don't forget to copy the files from the "Files to copy into new data folder" folder into each chunk folder before you continue.
```

8.  After you have chunked the entire file follow {ref}`06_decoding` and {ref}`06_segy`! **You will have to do it separately for each Chunk.**

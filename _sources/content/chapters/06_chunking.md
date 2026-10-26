(06_chunking)=
# Chunking Files Larger than 2 GB

You should have a file that is already fixed with the command fix_all_ln as explained in {ref}`06_data`. If you follow the naming sceme of the next steps you can use the attached python files without any changes other than the data-path.

1.  In your “data” folder, create a folder calling it for example like the Trilobit you want to analyze the data from. In my example it is “01069”. Put the fixed Raw file into this folder.

2.  In this folder create folders you name “01069_1stChunk”, “01069_2ndChunk”… Create as many folders as you need to get the data into Chunks that are smaller then 2 GB. In my example the raw data contains 11.8 GB so I get 3 Chunks each containing 4 components that are xxx

3.  Go into the EDR program and in the “Scan Raw” panel select “Extract raw”.

4.  Select the time and date for your first Chunk e.g. 10 days. (Here I would recommend to start at a time that will be your starting time across all Data analysis. We deployed the Trilobits at 14:32 o’clock and I set the start time to 14:00 UTC, so 16:00 in Svalbard time to let the sediment settle)

5.  Check the box “use convert times” and press “start conversion”. Select the raw file first before going into your folder 01069_1stChunk and create a new file and name it the same way. Press “send/okay”.

6.  Wait until that has worked and repeat the last 3 steps for the 01069_2ndChunk by changing the time to the next 10 days.

7.  Repeat for all chunks until your previous raw-file is chunked into 3 smaller chunked files.

8.  After you have chunked the entire file follow {ref}`06_decoding` and {ref}`06_segy`! **You will have to do it separately for each Chunk.**

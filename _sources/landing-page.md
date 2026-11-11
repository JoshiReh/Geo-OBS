# Welcome to Geo-OBS

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a>

```{admonition} Under Construction
:class: danger
Geo-OBS is still under construction. Some chapters are incomplete and will be extended. Feedback is welcome!
```


## Operating Trilobit Ocean Bottom Seismometers

````{margin} Based on Geo-UAV

The structure of this manual is based on the UNIS compendium
[Geo-UAV](https://unisvalbard.github.io/Geo-UAV/) (CC-BY-NC 4.0).

````

This manual is designed for teaching students, as well as scientific and technical staff, how to prepare, deploy and recover Trilobit ocean bottom seismometers (OBS) and how to process the recorded data.

### About Geo-OBS

Geo-OBS is **open for everyone to follow online**. It is meant as an open reference work for operating Trilobit ocean bottom seismometers in the field.

The instructions are given step by step and in great detail. Please follow each and every step precisely.

```{admonition} Usage Restrictions
:class: important
The Trilobit units used at UNIS were given free of charge to the University of Bergen (UiB) by Seabed Geosolutions (now merged with PxGeo). According to this agreement, the Trilobits:

- may be used for **academic research only**,
- may only be deployed in **Norwegian waters** (including Svalbard),
- must **not be dismantled** to use parts for other purposes.
```

### Course Content

Geo-OBS is split into several sessions:

- {ref}`01_introduction`
- Session 1: {ref}`03_preparation`
- Session 2: {ref}`04_deployment`
- Session 3: {ref}`05a_field_deployment`
- Session 4: {ref}`05_recovery`
- Session 5: {ref}`Downloading, Decoding and Converting the Data <06_data>`
- Session 6: {ref}`08_python_processing`
- Alternative path: {ref}`10_app_route`
- Supplementary: {ref}`09_documents`

### Learning Outcomes

After working through Geo-OBS, you will be able to:

✔️ Set up the hardware and change the batteries of a Trilobit\
✔️ Connect to the Trilobit and start a recording\
✔️ Stop the Trilobit and correct the time after recovery\
✔️ Download the RAW data and convert it into (chunked) SEG-Y files\
✔️ Display the recorded data\
✔️ Process the data with Python

### Project Status

```{admonition} Under Construction
:class: warning
Geo-OBS is still being written. New chapters, pictures and videos are added continuously.
```

### Contribute or Improve the Resource

Notice an unclear section? A typo in the text? Get in touch!

```{figure} assets/github_tut.gif
:name: github_tut

This page uses [GitHub](https://youtu.be/w3jLJU7DT5E) as a backbone.
All it takes is a [GitHub account](https://github.com/join).
Once connected, feel free to open an issue, whether suggesting improvements or highlighting bugs.
```

### Funding and Support

`````{grid} 2 2 2 2

````{grid-item}
:columns: 4
:class: funding-logo

```{image} ./content/assets/UNIS_logo.gif
:width: 200px
:target: https://www.unis.no
```
````
````{grid-item}
:columns: 7
:class: funding-text
[UNIS](https://www.unis.no/) supports Geo-OBS by providing the instruments as well as technical and logistical assistance.
````

````{grid-item}
:columns: 4
:class: funding-logo

```{image} ./content/assets/CAFE_logo.gif
:width: 200px
```
````
````{grid-item}
:columns: 7
:class: funding-text
The development of Geo-OBS is funded by the Centre of Excellence in Arctic Field Education (CAFE) through a FieldSoTL.
````

`````

### Acknowledgements and Licensing
Special thanks to **Bent Ole Ruud** and **Franck Arnljot Andersen** (University of Bergen) for taking the time to teach us how to operate the Trilobit OBS units and for patiently answering our countless questions about deployment, recovery and data processing.

Geo-OBS is implemented through Jupyter Book and the Executable Book Project. Its structure is based on [Geo-UAV](https://unisvalbard.github.io/Geo-UAV/).
This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

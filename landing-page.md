# Welcome to Geo-OBS

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a>

## Operating Trilobit ocean bottom seismometers

````{margin} Based on Geo-UAV

The structure of this manual is based on the UNIS compendium
[Geo-UAV](https://unisvalbard.github.io/Geo-UAV/) (CC-BY-NC 4.0).

````

This manual is designed for students, as well as scientific and technical staff, who want to learn how to prepare, deploy and recover Trilobit ocean bottom seismometers (OBS) and how to process the recorded data.

### About Geo-OBS

```{admonition} Open access
Geo-OBS is **open for everyone to follow online**. It is meant as an open reference work for operating Trilobit ocean bottom seismometers in the field.
```

The instructions are given step by step and in great detail. Please follow each and every step precisely.

### Course content

Geo-OBS is split into several sessions:

- {ref}`01_introduction` and {ref}`02_components`
- Session 1: {ref}`03_preparation`
- Session 2: {ref}`04_deployment`
- Session 3: {ref}`05_recovery`
- Session 4: {ref}`Decoding and cleaning data <06_data>`
- Session 5: {ref}`08_python_processing`
- Supplementary: {ref}`07_checklists` and {ref}`09_documents`

### Learning outcomes

After working through Geo-OBS, you will be able to:

- ✔️ Set up the hardware and charge the batteries of a Trilobit
- ✔️ Connect to the Trilobit and start a recording
- ✔️ Stop the Trilobit and correct the time after recovery
- ✔️ Download the RAW data and convert it into SEG-Y files
- ✔️ Display the recorded data
- ✔️ Process the data with Python: fix the binary header, convert to x, y, z and cut daily files

### Project status

```{admonition} Under construction
:class: warning
Geo-OBS is still being written. New chapters, pictures and videos are added continuously.
```

### Contribute or improve the resource

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

```{image} ./content/assets/UNIS_logo.gif
:class: m-auto
:width: 200px
:target: https://www.unis.no
```
````
````{grid-item}
:columns: 7
[UNIS](https://www.unis.no/) supports Geo-OBS by providing the instruments as well as technical and logistical assistance.
````

````{grid-item}
:columns: 4
````
````{grid-item}
:columns: 7
The development of Geo-OBS is funded by **[NAME OF FUNDER / PROJECT, grant number]**.
````

`````

### Acknowledgements and licensing

Geo-OBS is implemented through Jupyter Book and the Executable Book Project. Its structure is based on [Geo-UAV](https://unisvalbard.github.io/Geo-UAV/).
This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

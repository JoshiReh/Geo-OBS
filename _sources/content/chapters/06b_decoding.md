(06_decoding)=
# Decoding the Raw Data

```{admonition} Before You Start
:class: warning
If you want to continue with **EDR**, recordings that produce files larger than 2 GB have to be chunked first, see {ref}`06_chunking`. If you work with the beta of the **Trilobit Processor**, which shortens the whole process considerably, you can simply continue here without chunking.
```

1.  Go back to EDR208. In the “Convert” panel, set the “Operation” to “Scan Raw” and select the raw dataset you created in {ref}`06_data`.

2. The panel should now show when the dataset starts and when it ends.

```{image} assets/word_image42.jpg
:width: 466px
```

3. Now select the operation “Decode Raw” and press “Start Conversion”. This produces 9 new files: 4 .aux files (aux0 is the temperature, aux1 the voltage and aux5 the tilt), 4 files .g1, .g2, .g3 and .h1 for the geophones and the hydrophone of the Trilobit, and a text file that you will need later.

```{image} assets/word_image43.jpg
:width: 373px
```

```{admonition} Good to Know
:class: tip
You can open EDR208 several times and run several decodings at once to reduce the waiting time. This is especially useful if you chunked your dataset before.
```

```{image} assets/word_image44.jpg
:width: 411px
```

## How to Continue

There are two ways to continue. EDR is the intended route, built by the manufacturer for processing Trilobit data. The Trilobit Processor app automates all of the following steps and is therefore much faster, but it is still in beta.

`````{grid} 1 2 2 2
:gutter: 3

````{grid-item-card} **EDR**
:link: 06_segy
:link-type: ref

Continue with **EDR**, the original software built for processing OBS data.
````

````{grid-item-card} **Trilobit Processor (beta)**
:link: 10_app_route
:link-type: ref

Continue with the **Trilobit Processor** app, which does all of the following steps in one go.
````

`````

(06_decoding)=
# Decoding the Raw Data

```{admonition} Before You Start
:class: warning
If you want to continue with **EDR**, recordings with files larger than 2 GB have to be chunked first, see {ref}`06_chunking`. If you work with the beta of the **Trilobit Processor**, which shortens the whole process considerably, you can simply continue here without chunking.
```

1.  Go back into EDR. In the panel "Convert" set the “Operation” to “Scan Raw” and select your raw dataset as you named it in {ref}`06_data`.

2. The panel in EDR should show you when the dataset started and when it stopped.

```{image} assets/word_image42.jpg
:width: 466px
```

3. Now select Operation “Decode Raw” and press "Start Conversion". This should produce 9 new files: 4 .aux files (where aux0 is the temperature, aux1 is the voltage, and aux5 is the tilt) and 4 files .g1,.g2,.g3,.h1 that refer to our geophones and hydrophone in the trilobit. You will also get a text-file that you need later.

```{image} assets/word_image43.jpg
:width: 373px
```

```{admonition} Good to Know
:class: tip
You can open EDR multiple times and run several decodes at once to minimise the waiting time. This is especially useful if you chunked your dataset before.
```

```{image} assets/word_image44.jpg
:width: 411px
```

## How to Continue

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

Continue with the beta of the **Trilobit Processor**, which tries to automate all steps from EDR.
````

`````

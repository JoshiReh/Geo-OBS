(08_xyz_conversion)=
# X, Y, Z Conversion

Notebook: [2_fix_header_and_xyz.ipynb](https://github.com/JoshiReh/trilobit-processor/blob/main/notebooks/2_fix_header_and_xyz.ipynb) (the same notebook as the header correction, see {ref}`08_binary_header`)

The three geophones of the Trilobit are mounted in a Galperin configuration: each sensor is tilted by 54.7° from the vertical, and the three sensors are 120° apart in the horizontal plane. None of them measures vertical or horizontal motion directly. The recorded channels g1, g2 and g3 are therefore converted into the conventional x, y and z components:

$$
\begin{pmatrix} x \\ y \\ z \end{pmatrix} =
\begin{pmatrix}
-\sin 54.7^\circ & \sin 54.7^\circ \cos 60^\circ & \sin 54.7^\circ \cos 60^\circ \\
0 & -\sin 54.7^\circ \cos 30^\circ & \sin 54.7^\circ \cos 30^\circ \\
\cos 54.7^\circ & \cos 54.7^\circ & \cos 54.7^\circ
\end{pmatrix}
\begin{pmatrix} g_1 \\ g_2 \\ g_3 \end{pmatrix}
$$

With numbers:

```python
x = -0.81650 * g1 + 0.40825 * (g2 + g3)
y =  0.70711 * (g3 - g2)
z =  0.57735 * (g1 + g2 + g3)
```

- **x** points along geophone 1,
- **z** is positive **downward** (the seismic convention),
- x, y and z form a right-handed system.

x and y are still in the frame of the instrument. Where north and east are depends on how the Trilobit landed on the seafloor; finding this orientation is a separate step.

The hydrophone (h1) is not converted. It only gets the header correction and is saved as `_h.segy`.

The background, including the exact orientation and polarity of the sensors in the Trilobit and the derivation of the matrix, is described in the manufacturer's note {download}`Trilobit geophone configurations (PDF) <../assets/docs/Trilobit_galperin_configuration.pdf>`.

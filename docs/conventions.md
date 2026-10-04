# Conventions

Shared notation, units and code conventions. Every module follows them, so
that equations, Python code and MATLAB code can be compared line by line.

## Coordinates

- $x$: lateral (azimuth), along the array.
- $y$: elevation, across the array.
- $z$: depth (axial), pointing into the medium.
- The origin is the centre of the transducer face, which lies in the plane
  $z = 0$.
- A linear array of $N$ elements with pitch $p$ has element centres at

```math
x_i = \left(i - \frac{N - 1}{2}\right) p, \qquad i = 0, 1, \dots, N - 1 .
```

MATLAB code uses the same positions with one-based indices.

## Symbols

| Symbol | Meaning | SI unit | Code name (Python / MATLAB) |
| --- | --- | --- | --- |
| $c$ | Speed of sound | m/s | `c` |
| $f_0$ | Centre frequency | Hz | `f0` |
| $\lambda = c / f_0$ | Wavelength at the centre frequency | m | `wavelength` |
| $f_s$ | Sampling frequency | Hz | `fs` |
| $t$ | Time since the start of the transmit event | s | `t` |
| $N$ | Number of array elements | – | `n_elements` / `nElements` |
| $p$ | Element pitch | m | `pitch` |
| $x_i$ | Lateral position of element $i$ | m | `element_x` / `elementX` |
| $D$ | Aperture width | m | `aperture` |
| $F_\mathrm{n}$ | F-number (often written F#), depth divided by aperture width | – | `f_number` / `fNumber` |
| $\tau_i$ | Transmit delay of element $i$ | s | `tx_delays` / `txDelays` |
| $w_i$ | Apodisation weight of element $i$ | – | `weights` |
| $s_i(t)$ | Signal received on element $i$ (channel data) | arbitrary | `rf` |
| $b(x, z)$ | Beamformed signal at a point | arbitrary | `beamformed` |

A module that needs further symbols defines them on first use and keeps to
this table for the ones listed here.

## Units

- Code uses SI units without prefixes: metres, seconds, hertz. A depth of
  30 mm is written `30e-3`.
- Text and figure axes may use millimetres, microseconds and megahertz. The
  conversion happens at the point of display, never inside a calculation.
- Decibel values state their reference, for example "dB relative to the peak".

## Channel data

- Channel data of one transmit event is a real array `rf` of shape
  `(n_samples, n_elements)` in both Python and MATLAB: time runs along the
  first dimension and the element index along the second.
- Sample $k$ (zero-based) is taken at $t = k / f_s$. Time $t = 0$ is the
  instant at which the first element fires, so transmit delays are
  non-negative and the smallest one is zero.
- A beamformed image is an array of shape `(n_z, n_lines)`: depth along the
  first dimension and lateral position along the second.

## Code

### Python

- The package is `usip` in `src/usip/`. It supports Python 3.10 and later and
  uses NumPy arrays of `float64`.
- Functions and variables use `snake_case`. Public functions have NumPy-style
  docstrings that give the unit and shape of every array.
- Invalid input raises `ValueError` with a message that names the argument.
- Tests are in `tests/` and run with `pytest`.

### MATLAB

- The package is `usip` in `matlab/+usip/`, one function per file, called as
  `usip.functionName`. It targets MATLAB R2021a and later and needs no
  toolboxes.
- Functions and variables use `camelCase`. Each function starts with a help
  block that gives the unit and size of every array.
- Invalid input raises an error with an identifier of the form
  `usip:functionName:reason`.
- Tests are function-based `matlab.unittest` tests in `matlab/tests/`.

### Parity

The Python and MATLAB functions of a module take the same arguments in the
same order, implement the same equations and return arrays of the same shape.
Names differ only in case style: a function called `fractional_delay` in
Python is `usip.fractionalDelay` in MATLAB. A Python function with many scalar
parameters may require them to be passed by name; they are still declared in
the MATLAB order. For each module a shared reference case in `tests/data/` is
checked by both test suites, so that numerical agreement between the two
languages is tested and not only asserted.

## Figures and notebooks

- A notebook is committed without outputs. The figures it produces are
  exported to a `figures` folder next to it, each as a PNG file and an SVG
  file with the same name, `mNNN_description`. Lessons show the PNG files at
  a width of 336 pixels, which is 3.5 in at 96 pixels per inch.
- Notebook sources contain ASCII characters only. A character outside ASCII
  is written as an escape, for example `\u00b5` for the micro sign, because
  some tools read a notebook with the default encoding of the operating
  system.
- Figures are made with `usip.plotting`, which fixes the style below.
- Figures carry no titles and no annotations. What a figure shows is said in
  the text next to it.

| Item | Setting |
| --- | --- |
| Width | 3.5 in, one column of a two-column page |
| Line plots | 3.5 in by 2.625 in |
| Images | 3.5 in by 4.2 in |
| Font | Arial; axis labels 11 pt, tick labels 10 pt, legend 9 pt |
| Lines | 2 pt, solid; blue `#0072B2` and vermillion `#D55E00` |
| Frame | All four sides, black, 1.2 pt; no grid |
| Legend | Inside the axes where it does not cover data, in a thin grey box |
| Images | Grey scale; B-mode images show the 50 dB below the maximum |
| Labels | Initial capitals, unit in brackets: `Lateral Position (mm)` |
| Export | PNG at 600 dpi and SVG with text as outlines; fixed canvas size |

## Writing

- British spelling in text, as in the curriculum plan: apodisation, colour,
  centre.
- Inline mathematics uses `$...$`. Displayed equations use a fenced `math`
  block, which keeps Markdown from interpreting underscores and backslashes
  inside an equation.
- Inline mathematics must not contain a backslash followed by a punctuation
  character, such as `\#`, `\,` or `\{`. GitHub removes the backslash before
  the equation is rendered. An expression that needs one goes in a `math`
  block.
- Equations that are referred to elsewhere are numbered within the module:
  in module 19 they are (19.1), (19.2) and so on, written with `\tag{19.1}`.
- References give authors, year, title, venue and, for books, the chapter or
  section. Each entry is checked against the source before it is added.

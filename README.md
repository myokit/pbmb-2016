# Files accompanying the 2016 PBMB paper

This repository contains example models and code accompanying the paper "[Myokit: A simple interface to cardiac cellular electrophysiology](https://doi.org/10.1016/j.pbiomolbio.2015.12.008)" that appeared in PBMB in 2016 (full citation info at the bottom of this page).

![A schematic overview of Myokit's main functionality](overview-v11.png)


## Example 1

The first example can be opened in the Myokit IDE (the Myokit "app") and contains a model, protocol, and script: [example-1a-ide.mmt](https://raw.githubusercontent.com/myokit/pbmb-2016/main/example-1a-ide.mmt).
To use it, download the file by right clicking the link above and selecting "Save link as", then open it in the IDE.

When writing scripts _inside an mmt file_, like in the example above, you can access the model and protocol parts with:
```
m = get_model()
p = get_protocol()
```

In many cases it's better to write a script separately from the `mmt` file (for example to re-use the exact same model in multiple simulations).
To access an `mmt` file's model and protocol externally, use:
```
m = myokit.load_model('my-model.mmt')
p = myokit.load_protocol('my-protocol.mmt')
```
or
```
m, p, _ = myokit.load('my-model.mmt')
```
if both are in the same file (this also loads the script part as `_`).

A version of example 1 that loads the model and protocol externally is given in the jupyter notebook [example-1b-notebook.ipynb](https://raw.githubusercontent.com/myokit/pbmb-2016/main/example-1b-notebook.ipynb).
You can download this and [the required model file]() to try offline, or you can view the example in your browser using [github's viewer](example-1b-notebook.ipynb) or the slightly nicer [nbviewer](https://nbviewer.jupyter.org/github/myokit/myokit-pbmb-2016/blob/main/example-1b-notebook.ipynb).
















## Citing

To cite the paper, use

- Michael Clerx, Pieter Collins, Enno de Lange, Paul G.A. Volders
  Myokit: A simple interface to cardiac cellular electrophysiology
  Progress in Biophysics and Molecular Biology, 2016, Volume 120, issues 1-3, pages 100-114
  doi: [10.1016/j.pbiomolbio.2015.12.008](https://doi.org/10.1016/j.pbiomolbio.2015.12.008)

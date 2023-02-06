# Examples from the 2016 PBMB paper

Michael Clerx, Pieter Collins, Enno de Lange, and Paul G.A. Volders (2016).
_Myokit: A simple interface to cardiac cellular electrophysiology_.
Progress in Biophysics and Molecular Biology, Volume 120, issues 1-3, pages 100-114.
[10.1016/j.pbiomolbio.2015.12.008](https://doi.org/10.1016/j.pbiomolbio.2015.12.008).

This repository contains up-to-date example code, adapted from the files originally published with the paper cited above.

An updated version of the schematic describing Myokit is shown below.

![A schematic overview of Myokit's main functionality](overview-v11.png)

## Example 1
_Called example-ttp-1-model.mmt in the paper._


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
You can download this and [the required model file](https://raw.githubusercontent.com/myokit/models/main/c/tentusscher-2006.mmt) to try offline, or you can view the example [in your browser](example-1b-notebook.ipynb).

## Example 2
_Called example-ttp-2-transmural-differences.mmt in the paper._

The [second example](example-2-transmural-differences.ipynb) follows up from example 1b, and shows how to change a model variable in a simulation.
Some models, like the Ten Tusscher et al. one used in this example, have a variable used as a "mode switch".
Here, we use this to show the three different cell types the model can represent.

The example also shows how to save simulation data to CSV files and load it again for later processing.

## Example 3
_Called example-ttp-3-gto.mmt in the paper._

The [third example](example-3-gto.ipynb) uses the same technique as the second, but this time to explore the effects of varying the Ito conductance in the epicardial model.
It also shows how to modify a model after loading it.

## Example 4
_Called example-ttp-4-sensitivity.mmt in the paper._

The [fourth example](example-4-sensitivity.ipynb) does something more mathematical, and shows how Myokit can be used to calculate the partial derivatives of dependent variables (e.g. state variables or currents) on independent variables (e.g. conductance parameters).

## Examples 5
_Called example-ttp-5-transmural-baseline.mmt in the paper._

In [example 5](example-5-fiber-baseline.ipynb) a strand consisting of 60 endocardial, 45 mid-myocardial, and 60 epicardial cells is simulated, with pacing from the endocardial end.

The example can be viewed in any browser, but re-running the simulations requires [a working OpenCL installation](http://myokit.org/install/#opencl)

## Example 6
_Called example-ttp-6-transmural-modified in the paper._

The [sixth example](example-6-fiber-modified.ipynb) follows up from example 5, but adds 50% ICaL block 240% Ito increase, and a reduced cell-to-cell conductance.
This results in a gradual loss of the spike-and-dome shape of the APs.

## Example 7







## Parameter estimation examples
_Called example-parameter-estimation.mmt and example-parameter-estimation-2.mmt in the paper._

In 2016 Myokit contained methods for parameter estimation.
These have since been merged into the [PINTS](https://github.com/pints-team/pints) library.

Examples of using PINTS and Myokit to perform parameter estimation in ion current models [are provided in a seperate repository](https://github.com/CardiacModelling/fitting-notebooks).


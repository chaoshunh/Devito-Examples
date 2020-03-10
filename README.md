
# Devito-Examples


This repository contains a set of examples and tutorials for seismic modeling and inversion using [Devito].
These examples use four different wave equations, namely

- The acoustic isotropic wave equation in`seismic/acoustic`
- The TTI pseudo-acoustic wave equation in `seismic/tti`
- The elastic isotropic wave equation in `seismic/elastic`
- The viscoelastic isotropic wave equation in `seismic/elastic`

Currently, the acoustic isotropic wave equation solver also contains the propagator associated with the adjoint and linearized (Born) wave-equation solution and the gradient of the FWI objective (application of the Jacobian to data residual)

## Disclaimer

A good part of these examples can also be found in the [Devito] examples directory as a fork of this one. These examples for seismic applications have been developed and implemented by [Mathias Louboutin](https://slim.gatech.edu/people/mathias-louboutin) at Georgian Institute of Technology. Some extra examples are also included over there, such as tutorials on the [Devito] compiler as these examples have been developed primarily at Imperial College London.

## Installation

To install this set of examples with it's dependencies run:

```
git clone https://github.com/slimgroup/Devito-Examples
cd Devito-Examples
pip install -e .
```
This command will install all dependencies including [Devito] and wil lallow you to run the examples. To verify your installation you can run:

```
python seismic/acoustic/acoustic_example.py -nd 1
```

## How to navigate this directory

Examples and tutorials are provided in the form of single Python files and as Jupyter
notebooks.Jupyter notebooks are files with extension `.ipynb`. To execute these, run
`jupyter notebook`, and then click on the desired notebook in the window that
pops up in your browser.

The seismic examples and tutorials are organized as follows:

* `seismic/tutorials`: A series of Jupyter notebooks of incremental complexity,
  showing a variety of Devito features in the context of seismic inversion
  operators. Among the discussed features are modeling, adjoint modeling, computing a gradient and a seismic image, FWI and elastic modeling on a staggered grid.
* `seismic/acoustic`: Example implementations of isotropic acoustic forward,
  adjoint, gradient and born operators, suitable for full-waveform inversion
  methods (FWI).
* `seismic/tti`: Example implementations of several anisotropic acoustic
  forward operators (TTI).
* `seismic/elastic`: Example implementation of an isotropic elastic forward
  operator. `elastic`, unlike `acoustic` and `tti`, fully exploits the
  tensorial nature of the Devito symbolic language.
* `seismic/viscoelastic`: Example implementation of an isotropic viscoelastic
  forward operator. Like `elastic`, `viscoelastic` exploits tensor functions
  for a neat and compact representation of the discretized partial differential
  equations.

## Related litterature

Some of these examples are described in the following papers:

[Devito's symbolic API](https://slim.gatech.edu/content/devito-embedded-domain-specific-language-finite-differences-and-geophysical-exploration)\
[TTI imaging](https://slim.gatech.edu/content/effects-wrong-adjoints-rtm-tti-media)\
[Mathias Louboutin's thesis](https://slim.gatech.edu/content/modeling-inversion-exploration-geophysics)

More advanced geophysical application can be found in the [JUDI] repository. [JUDI] is a linear algebra DSL built on top of [Devito] for large scale inverse problems and including abstraction for source/receivers and handles large SEG-Y datasets with [SegyIO](https://github.com/slimgroup/SegyIO.jl). A complete description of [JUDI] and the related seismic inversion application can be found in [Philipp Witte's thesis](https://slim.gatech.edu/content/modeling-inversion-exploration-geophysics).

[JUDI]:https://github.com/slimgroup/JUDI.jl
[Devito]:https://www.devitoproject.org

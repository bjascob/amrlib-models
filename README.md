# amrlib models
This repository contains [releases](https://github.com/bjascob/amrlib-models/releases) of models
for the [amrlib](https://github.com/bjascob/amrlib) library.  For information on how to download
and install see [ReadTheDocs Installation Instructions](https://amrlib.readthedocs.io/en/latest/install/)
or follow the instructions below.

Note that because these models are large binary files, they are not directly tracked with git.
Instead the are provided for download as `.tar.gz` files.

## Installation
Download the pre-trained models from the [releases](https://github.com/bjascob/amrlib-models/releases)
directory and extract in them in `amrlib/data`.  Set a link to the directory (or rename it) as either
`model_stog` (sentence to graph) for the parse style models or `model_gtos` (graph to sentence) for
the generate style models.

If you're unsure where amrlib is installed you can do...
```
pip3 show amrlib
```
or
```
python3
>>> import amrlib
>>> amrlib.__file__
```

## Available Models

| Name | Type | Version | Date | Size | Score | | |
| ---- | ---- | ------- | ---- | ---- | ----- | --- | --- |
| Parse T5 | STOG | 0.1.0 | 2020-12-12 | 785M | 81 SMATCH | [![][i]][i-model_parse_t5-v0_1_0] | [![][dl]][model_parse_t5-v0_1_0]

[model_parse_t5-v0_1_0]: https://github.com/bjascob/amrlib-models/releases/download/model_parse_t5-v0_1_0/model_parse_t5-v0_1_0.tar.gz                         

[i-model_parse_t5-v0_1_0]: https://github.com/bjascob/amrlib-models/releases/model_parse_t5-v0_1_0


[dl]: http://i.imgur.com/gQvPgr0.png
[i]: http://i.imgur.com/OpLOcKn.png


## Issues and bug reports
To report an issue with a model please use the  [amrlib issues](https://github.com/bjascob/amrlib/issues) list.

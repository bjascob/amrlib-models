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

## Sentence to Graph Models

| Name | Version | Date | Size | Score | Speed |||
| ---- | ------- | ---- | ---- | ----- | --- | --- |---|
| parse_xfm_bart_large | 0.1.0 | 2022-02-16 | 1.4GB | 83.7 SMATCH | 17/sec| [![][i]][i-parse_xfm_bart_large] | [![][dl]][d-parse_xfm_bart_large]
| parse_xfm_bart_base | 0.1.0 | 2022-02-16 | 492 MB | 82.3 SMATCH | 31/sec| [![][i]][i-parse_xfm_bart_base] | [![][dl]][d-parse_xfm_bart_base]
| parse_spring | 0.1.0 | 2021-11-25 | 1.5GB | 83.5 SMATCH | 14/sec| [![][i]][i-parse_spring] | [![][dl]][d-parse_spring]
| parse_t5 | 0.2.0 | 2020-11-27 | 785MB | 81.9 SMATCH | 11/sec| [![][i]][i-parse_t5] | [![][dl]][d-parse_t5]
| parse_gsii | 0.1.0 | 2020-08-30 | 787MB | 76.8 SMATCH | 28/sec| | [![][dl]][d-parse_gsii]

All models are trained and scored on AMR-3 (LDC2020T02). This is a more difficult test set than the older
AMR-2 set and generally scores a bit lower for similar models.  All scores are without adding the :wiki tags.
However, when using BLINK, scores typically stay approximately the same since the wikification process itself scores in the
low to mid 80s on smatch.  Speed is the inference speed on the AMR-3 test using an RTX3090 and a bach size of 32.
The units are sentences/second.

[d-parse_xfm_bart_large]: https://github.com/bjascob/amrlib-models/releases/download/parse_xfm_bart_large-v0_1_0/model_parse_xfm_bart_large-v0_1_0.tar.gz
[d-parse_xfm_bart_base]: https://github.com/bjascob/amrlib-models/releases/download/parse_xfm_bart_base-v0_1_0/model_parse_xfm_bart_base-v0_1_0.tar.gz
[d-parse_spring]: https://github.com/bjascob/amrlib-models/releases/download/model_parse_spring-v0_1_0/model_parse_spring-v0_1_0.tar.gz
[d-parse_t5]: https://github.com/bjascob/amrlib-models/releases/download/model_parse_t5-v0_2_0/model_parse_t5-v0_2_0.tar.gz
[d-parse_gsii]: https://u.pcloud.link/publink/show?code=XZD2z0XZOqRtS2mNMHhMG4UhXOCNO4yzeaLk

[i-parse_xfm_bart_large]: https://github.com/bjascob/amrlib-models/releases/parse_xfm_bart_large-v0_1_0
[i-parse_xfm_bart_base]: https://github.com/bjascob/amrlib-models/releases/parse_xfm_bart_base-v0_1_0
[i-parse_spring]: https://github.com/bjascob/amrlib-models/releases/model_parse_spring-v0_1_0
[i-parse_t5]: https://github.com/bjascob/amrlib-models/releases/model_parse_t5-v0_2_0


## Graph to Sentence Models

| Name | Version | Date | Size | Score | | |
| ---- | ------- | ---- | ---- | ----- | --- | --- |
| generate_t5wtense | 0.1.0 | 2020-12-30 | 787MB | 54 BLEU | [![][i]][i-model_generate_t5wtense-v0_1_0] | [![][dl]][model_generate_t5wtense-v0_1_0]

[model_generate_t5wtense-v0_1_0]: https://github.com/bjascob/amrlib-models/releases/download/model_generate_t5wtense-v0_1_0/model_generate_t5wtense-v0_1_0.tar.gz

[i-model_generate_t5wtense-v0_1_0]: https://github.com/bjascob/amrlib-models/releases/model_generate_t5wtense-v0_1_0


[dl]: http://i.imgur.com/gQvPgr0.png
[i]: http://i.imgur.com/OpLOcKn.png


## Issues and bug reports
To report an issue with a model please use the  [amrlib issues](https://github.com/bjascob/amrlib/issues) list.

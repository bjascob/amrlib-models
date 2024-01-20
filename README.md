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

#### Attribution:
* The parse_spring code is from the [SPRING model](https://github.com/SapienzaNLP/spring). Note that the author's license for their code is "Attribution-NonCommercial-ShareAlike 4.0 International". Details on the model can be found in this [paper](https://ojs.aaai.org/index.php/AAAI/article/view/17489).

* The parse_gsii model comes from [jcyk/AMR-gs](https://github.com/jcyk/AMR-gs), the details of which can be found in this
[paper](https://arxiv.org/abs/2004.05572).

* All other models were developed as part of [amrlib](https://github.com/bjascob/amrlib).

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
| generate_t5wtense | 0.1.0 | 2020-12-30 | 787MB | 54/44 BLEU | [![][i]][i-model_generate_t5wtense-v0_1_0] | [![][dl]][model_generate_t5wtense-v0_1_0]

The generate_t5wtense gives a **54 BLEU** with tense tags or **44 BLEU** with un-tagged LDC2020T02.
Note that the model is only scored with graphs that fit in the T5 model's 512 token limit. If including clipped
graphs, scores will be more like 52/43 BLEU.
Details on using this type of model for generation can be found in this [paper](https://arxiv.org/abs/2007.08426).

Additionally, there is a training config file for a T5-large based model in the [amrlib/config directory here](https://github.com/bjascob/amrlib/blob/master/configs/model_generate_xfm_t5_large_wTT.json). This model scores about 2 BLEU points higher than generate_t5wtense-v0_1_0
if you take the time to train it yourself.

[model_generate_t5wtense-v0_1_0]: https://github.com/bjascob/amrlib-models/releases/download/model_generate_t5wtense-v0_1_0/model_generate_t5wtense-v0_1_0.tar.gz

[i-model_generate_t5wtense-v0_1_0]: https://github.com/bjascob/amrlib-models/releases/model_generate_t5wtense-v0_1_0


[dl]: http://i.imgur.com/gQvPgr0.png
[i]: http://i.imgur.com/OpLOcKn.png


## Issues and bug reports
To report an issue with a model please use the  [amrlib issues](https://github.com/bjascob/amrlib/issues) list.

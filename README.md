NEMATUS
-------

Attention-based encoder-decoder model for neural machine translation

This package is based on the dl4mt-tutorial by Kyunghyun Cho et al. ( https://github.com/nyu-dl/dl4mt-tutorial ).
It was used to produce top-scoring systems at the WMT 16 shared translation task.

The changes to Nematus include:

 - ensemble decoding (and new translation API to support it)
 - dropout on all layers (Gal, 2015) http://arxiv.org/abs/1512.05287
 - automatic training set reshuffling between epochs
 - n-best output for decoder
 - more output options (attention weights; word-level probabilities) and visualization scripts
 - performance improvements to decoder
 - rescoring support
 - execute arbitrary validation scripts (for BLEU early stopping)
 - vocabulary files and model parameters are stored in JSON format (backward-compatible loading)


INSTALLATION
------------

Nematus requires the following packages:

 - Python >= 2.7
 - numpy
 - ipdb
 - Theano >= 0.7 (and its dependencies).

we recommend executing the following command in a Python virtual environment:
   pip install numpy numexpr cython tables theano ipdb

the following packages are optional, but *highly* recommended

 - CUDA >= 7  (only GPU training is sufficiently fast)
 - cuDNN >= 3 (speeds up training substantially)


you can run Nematus locally. To install it, execute `python setup.py install`


USAGE INSTRUCTIONS
------------------

Change the hard-coded paths to data in `test/train_nmt.py` then run
```
THEANO_FLAGS=device=gpu,floatX=float32 python train_nmt.py 
```

To decode, see the command `test/test.sh`

A sample setup that includes preprocessing is provided at https://github.com/rsennrich/wmt16-scripts/tree/master/sample


PUBLICATIONS
------------

the code is based on the following model:

Dzmitry Bahdanau, Kyunghyun Cho, Yoshua Bengio (2015): Neural Machine Translation by Jointly Learning to Align and Translate, Proceedings of the International Conference on Learning Representations (ICLR).

for the changes specific to Nematus, please consider the following papers:

TBD

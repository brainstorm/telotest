# Small Python and Bioinformatics interview test code

This is a small **(broken, incomplete)** code project to test your overall python ecosystem and knowledge about algorithms, complexity and general data handling. For some biological context, we are handling [Telomeres][telomeres] here.

You will be questioned and guided on several aspects during the code interview. Valuable 
experience is:

1) Being able to work in a collaborative way using Github.
2) Use [test driven development][TDD] methodology to reason about inputs/outputs of code pipelines, unit tests.
3) Identify bad coding practices.
4) Improve the performance, usefulness, cleanness and generality of the code.

## Install process

Those three commands assume that you have [Miniconda][miniconda] installed on your computer:

	git clone https://github.com/brainstorm/telotest && cd telotest
    conda create -n telotest python=3
	pip install -r requirements.txt

## Testing loop

In order to run the testsuite under `tests`, the [tox][tox] tool will be used to run them all:

    tox

## Download datasets

When tests pass, the input dataset for this code is the [2013 human reference genome (hg38)][hg38] (~950MB compressed), which can be downloaded to the `data` folder for further testing.

[TDD]: https://en.wikipedia.org/wiki/Test-driven_development
[tox]: https://tox.readthedocs.io/en/latest/
[hg38]: http://hgdownload.cse.ucsc.edu/goldenPath/hg38/bigZips/hg38.fa.gz
[miniconda]: https://conda.io/miniconda.html
[telomeres]: https://en.wikipedia.org/wiki/Telomere

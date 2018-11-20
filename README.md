# Small Python and Bioinformatics interview test code

This is a small **(broken, incomplete)** code project to test your overall python ecosystem and knowledge about algorithms, complexity and general data handling.

You will be questioned and guided on several aspects during the code interview. Valuable experience is:

1) Being able to work in a collaborative way using Github.
2) Use [test driven development][TDD] methodology to reason about inputs/outputs of code pipelines, unit tests.
3) Identify bad coding practices.
4) Improve the performance, usefulness, cleanness and generality of the code.
5) Last but not least (at all): Respect the importance of deployment of (scientific) code.

<blockquote class="twitter-tweet" data-lang="sv"><p lang="en" dir="ltr">Say you pick 100 random bioinformatics software tools -- how many will you actually be able to access, install, and run?<br><br>Our new paper: <a href="https://t.co/rllGmGdL1s">https://t.co/rllGmGdL1s</a> <a href="https://t.co/JzyWc0W44X">https://t.co/JzyWc0W44X</a></p>&mdash; Ran Blekhman (@blekhman) <a href="https://twitter.com/blekhman/status/1055625170809962496?ref_src=twsrc%5Etfw">26 oktober 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

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

## Biological context

[Telomere](https://en.wikipedia.org/wiki/Telomere) is a repetitive region found at each end of a chromosome. Its evolutionary role is to protect chromosome ends from degradation: after each division of our cells, the DNA shrinks a bit from each end, and telomeres take all the damage.

Unfortunately, the telomers are not endless, and after certain number of cell divisions they disappear, and the cell dies. For clinical porposes, it's very important to know how much of the telomere is left on each chromosome. 

This project is an attempt to solve this problem computationally from DNA sequencing data. As the first step, it finds boundaries of telomeric regions in a chromosome sequence. All telomeric regions consist of a motif CCCTAA repeated many times, and rely on that fact to find the regions.

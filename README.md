# Paper-Reviewer matcher

(work in progress)

Package for Paper-Reviewer matching which available at http://pr.scienceofscience.org/
(implementation based on this [article](http://www.cis.upenn.edu/~cjtaylor/PUBLICATIONS/pdfs/TaylorTR08.pdf)).
This package solves problem of assigning paper to reviewers with constrains by solving linear programming problem.
We minimize global distance between papers and reviewers in topic space (e.g. topic can be Principal component,
  Latent Semantic Analysis).

Here is a diagram of problem setup and how we solve the problem.

<img src="data/problem_setup.png" width="300">

<img src="data/paper_reviewer_matching.png" width="600">


## Usage

Here is a

```python
from paper_reviewer_matcher import preprocess, affinity_computation
papers = list(map(preprocess, papers)) # list of papers' abstract
reviewers = list(map(preprocess, reviewers)) # list of reviewers' abstract
A = affinity_computation(papers, reviewers)
# solve linear programming problem (adding soon)
```


## Dependencies

- numpy
- scipy
- nltk
- scikit-learn
- [or-tools](https://github.com/google/or-tools) (for linear programming solver)

please refer to [Stackoverflow](http://stackoverflow.com/questions/26593497/cant-install-or-tools-on-mac-10-10)
on how to install `or-tools` on MacOSX. I use `pip` to install `protobuf` before installing `or-tools`

```
$ pip install protobuf==3.0.0b4
$ pip install ortools
```

## Members

- Daniel Acuna
- Titipat Achakulvisut
- Tulakan Ruangrong
- Konrad Kording

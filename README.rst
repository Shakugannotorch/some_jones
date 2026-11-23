Jones polynomial of some large knots
============================

This repository stores the Jones polynomial of some large knot diagrams
accompanying the paper 

  Shana Yunsheng Li, Fixed-parameter tractable computation of Reshetikhin--Turaev knot polynomials via tensor networks `arXiv:2606.29662
  <https://arxiv.org/abs/2606.29662>`_

The folder :code:`PD` stores the planar diagrams of the knots in :code:`SnapPy`'s convention, and :code:`Jones` stores the Jones polynomials.

For the Jones polynomial, each file contains 4 lines and are of the following format::

    Number of crossings: xxx
    Runtime: xxx, Calculation time: xxx
    Peak RAM usage (MB): xxx
    xxx 

where the 4th line stores the plain text representing the Jones polynomial. The Runtime represents the total run time of the computation including
finding the contraction sequence, and the Calculation time represents the time spent after finding the contraction sequence; the unit of time is seconds.

The files with :code:`_cap_30` suffix record the computation where the O(n^2) greedy algorithm was used for finding the contraction sequence, while
those without record the computation where the O(n^3) greedy algorithm was used. The method for computing the Jones polynomial, using the latest copy
of `spherogram<https://github.com/Shakugannotorch/Spherogram>`_ , is::

    snappy.Link.colored_jones_polynomial(n, timed=False, min_long_cap=None)

where :code:`n=1` gives the Jones polynomial, :code:`timed=True` returns the Calculation time along with the answer for the polynomial, and
:code:`min_long_cap=None` corresponds to the O(n^3) greedy algorithm and :code:`min_long_cap=30` corresponds to the O(n^2) greedy algorithm. 


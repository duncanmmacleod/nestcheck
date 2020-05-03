nestcheck
=========

.. image:: https://travis-ci.org/ejhigson/nestcheck.svg?branch=master
   :target: https://travis-ci.org/ejhigson/nestcheck
.. image:: https://coveralls.io/repos/github/ejhigson/nestcheck/badge.svg?branch=master
   :target: https://coveralls.io/github/ejhigson/nestcheck?branch=master
.. image:: https://readthedocs.org/projects/nestcheck/badge/?version=latest
   :target: http://nestcheck.readthedocs.io/en/latest/?badge=latest
.. image:: http://joss.theoj.org/papers/10.21105/joss.00916/status.svg
   :target: https://doi.org/10.21105/joss.00916
.. image:: https://api.codeclimate.com/v1/badges/7fdfe74eb8256020c780/maintainability
   :target: https://codeclimate.com/github/ejhigson/nestcheck/maintainability
   :alt: Maintainability
.. image:: https://img.shields.io/badge/license-MIT-blue.svg
   :target: https://github.com/ejhigson/nestcheck/blob/master/LICENSE
.. image:: https://pepy.tech/badge/nestcheck
   :target: https://pepy.tech/project/nestcheck
.. image:: https://pepy.tech/badge/nestcheck/week
   :target: https://pepy.tech/project/nestcheck/week

Nested sampling is a popular numerical method for Bayesian computation, which simultaneously generates samples from the posterior distribution and an estimate of the Bayesian evidence for a given likelihood and prior.
``nestcheck`` provides Python utilities for analysing samples produced by nested sampling, and estimating uncertainties on nested sampling calculations (which have different statistical properties to calculations using other numerical methods). This includes implementations of the diagnostic tests and plots described in:

- "Sampling errors in nested sampling parameter estimation" (`Higson et al., 2018 <https://doi.org/10.1214/17-BA1075>`_);
- "nestcheck: diagnostic tests for nested sampling calculations" (`Higson et al., 2019 <https://doi.org/10.1093/mnras/sty3090>`_).

To get started, see the `installation instructions <http://nestcheck.readthedocs.io/en/latest/install.html>`_ and the `quickstart demo <http://nestcheck.readthedocs.io/en/latest/demos/quickstart_demo.html>`_. More examples of ``nestcheck``'s use can be found in the code used to make the results and plots in `Higson et al. (2019) <https://doi.org/10.1093/mnras/sty3090>`_ at https://github.com/ejhigson/diagnostic.

Compatible nested sampling software
-----------------------------------

Currently ``nestcheck.data_processing`` has functions to load results from:

- `PolyChord <https://github.com/PolyChord/>`_ >=v1.14;
- `MultiNest <https://ccpforge.cse.rl.ac.uk/gf/project/multinest/>`_ >=v3.11;
- `dyPolyChord <https://github.com/ejhigson/dyPolyChord>`_ (same output format as PolyChord);
- `dynesty <https://github.com/joshspeagle/dynesty>`_;
- `perfectns <https://github.com/ejhigson/perfectns>`_.

You can easily add input functions for other nested sampling software packages. Note that ``nestcheck`` requires information about the iso-likelihood contours within which dead points were sampled ("born"), which is needed to split nested sampling runs into their constituent single live point runs ("threads"); see `Higson et al. (2018) <https://doi.org/10.1214/17-BA1075>`_ for more details.
``nestcheck`` is fully compatible with `dynamic nested sampling <https://doi.org/10.1007/s11222-018-9844-0>`_, in which the number of live points is varied to increase calculation accuracy.


Documentation contents
----------------------

.. toctree::
   :maxdepth: 2

   install
   demos/quickstart_demo
   api


Attribution
-----------

If ``nestcheck`` is useful for your academic research, please cite the three papers introducing the software and the methods it implements. The BibTeX is:

.. code-block:: tex

    @article{higson2019diagnostic,
    title={nestcheck: diagnostic tests for nested sampling calculations},
    author={Higson, Edward and Handley, Will and Hobson, Mike and Lasenby, Anthony},
    journal={Monthly Notices of the Royal Astronomical Society},
    year={2019}
    volume={483},
    number={2},
    pages={2044--2056},
    doi={10.1093/mnras/sty3090},
    url={http://doi.org/10.1093/mnras/sty3090},
    archivePrefix={arXiv},
    arxivId={1804.06406}}

    @article{higson2018sampling,
    title={Sampling Errors in Nested Sampling Parameter Estimation},
    author={Higson, Edward and Handley, Will and Hobson, Mike and Lasenby, Anthony},
    year={2018}
    journal={Bayesian Analysis},
    number={3},
    volume={13},
    pages={873--896},
    doi={10.1214/17-BA1075},
    url={https://doi.org/10.1214/17-BA1075}}

    @article{higson2018nestcheck,
    title={nestcheck: error analysis, diagnostic tests and plots for nested sampling calculations},
    author={Higson, Edward},
    year={2018},
    journal={Journal of Open Source Software},
    number={29},
    pages={916},
    volume={3},
    doi={10.21105/joss.00916},
    url={http://joss.theoj.org/papers/10.21105/joss.00916}}


Changelog
---------

The changelog for each release can be found at https://github.com/ejhigson/nestcheck/releases.

Contributions
-------------

Contributions are welcome! Development takes place on github:

- source code: https://github.com/ejhigson/nestcheck;
- issue tracker: https://github.com/ejhigson/nestcheck/issues.

When creating a pull request, please try to make sure the tests pass and use numpy-style docstrings.

If you have any questions or suggestions please get in touch (e.higson@mrao.cam.ac.uk).

Authors & License
-----------------

Copyright 2018-Present Edward Higson and contributors (MIT license).

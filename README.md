# BootPy

![example workflow](https://github.com/UBC-MDS/bootpy/actions/workflows/ci-cd.yml/badge.svg)
[![codecov](https://codecov.io/gh/UBC-MDS/bootpy/branch/main/graph/badge.svg?token=ufgX4eYuYU)](https://codecov.io/gh/UBC-MDS/bootpy)

## Summary

Performs bootstrapping of a dataset column to produce plots and statistics for use in final reports and documents.

The purpose of this package is to simplify and automate the process of creating simple bootstrap distributions of numerical data columns. The package will have a module which intakes a dataset column and relevant parameters such as the desired confidence bounds and number of simulations. The module will perform the simulation statistics to generate the bootstrap mean distribution and relevant statistics such as the sample mean and bootstrapped confidence interval. The package will also contain a module for visualization of the bootstraped confidence interval, and a module for creating a professional publication-ready table of the relevant statistics.

## Package context within the Python ecosystem

The package will likely build on scipy's [stats module](https://docs.scipy.org/doc/scipy/reference/stats.html), which allows one to conduct the boostrap sampling in the first place using the bootstrap method. bootpy will streamline and extend this process from the pure statistical process done in this module. sklearn has a utils module with a [resample](https://scikit-learn.org/stable/modules/generated/sklearn.utils.resample.html) method which also seems popular and achieves similar functionality. While we cannot be certain that one does not exist, there does not seem to be a package which streamlines the process from data to visualization and presentation as proposed in this document. Some tutorials on bootstrap confidence intervals from [machinelearningmastery.com](https://machinelearningmastery.com/calculate-bootstrap-confidence-intervals-machine-learning-results-python/) and [towardsdatascience.com](https://towardsdatascience.com/bootstrapping-using-python-and-r-b112bb4a969e) encourage the reader to plot the results manually.


## Installation

```bash
$ pip install bootpy
```

## Usage

To import bootpy and check the version:

```python
import bootpy
print(bootpy.__version__)
```

To import the suite of functions:

```python
from bootpy import bootstrap
from bootpy import display
```

Please view our packaged documentation [here](https://bootpy.readthedocs.io/en/latest/).

## Functions

- `bootstrap_distribution`: Returns a sampling distribution of specified replicates is generated for a specified estimator with replacement for a given bootstrap sample size.  
- `calculate_boot_stats`: Calculates a confidence interval for a given sampling distribution as well as other bootstrapped statistics.  
- `plot_ci`: Creates a histogram of a bootstrapped sampling distribution with its confidence interval and observed sample statistic.  
- `tabulate_stats`: Generates a table that contains a given sampling distribution's mean and standard deviation along with relevant statistics as well as a summary table of the bootstrap distributions parameters. The code automatically saves the tables as html documents.

## Contributing
Julien Gordon, Gautham Pughazhendhi, Zack Tang, and Margot Vore.

## License

`BootPy` was created by Julien Gordon, Gautham Pughazhendhi, Zack Tang, Margot Vore. It is licensed under the terms of the MIT license.

## Credits

`BootPy` was created with [`cookiecutter`](https://cookiecutter.readthedocs.io/en/latest/) and the `py-pkgs-cookiecutter` [template](https://github.com/py-pkgs/py-pkgs-cookiecutter).

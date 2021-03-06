RStan
=====

:supportlevel: B
:pagelastupdated: 2018-07-26
:maintainer:

RStan is an R interface to Stan.  Stan is a platform for modeling.


Basic installation
------------------

RStan is installed as an R package and there is nothing too special
about it.

First, load the R module you need to use.  There are different
options, using different compilers.  Do **not** use an ``iomkl`` R
version, because it requires the intel compilers to work on the nodes
to compile every time you run, and they aren't available there.  If
you load a ``goolf`` R version, it will work (you could work around
this by pre-compiling models, if you wanted)::

  $ module spider R
  ...
  R/3.4.1-goolf-triton-2017a
  R/3.4.1-iomkl-triton-2017a

  $ module load R/3.4.1-goolf-triton-2017a

If you change R versions (from intel to gcc) or get errors about
loading libraries, you may have installed incompatible libraries.
Removing your ``~/R`` directory and reinstalling all of your libraries
is a good first place to start.

Notes
-----

You should detect the number of cores with::

  as.integer(Sys.getenv('SLURM_JOB_CPUS_PER_NODE', parallel::detectCores()))



Example
-------

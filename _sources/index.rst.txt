.. 
   GeoArmadillo documentation master file, created by
   sphinx-quickstart on Wed Aug 28 11:56:52 2024.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

GeoArmadillo
============
..
   The GeoArmadillo library is written using the reStructured Text markup language.
   You find more information on reStructuredText here: https://www.sphinx-doc.org/en/master/usage/restructuredtext/index.html

GeoAramdillo is built with `blockly <https://developers.google.com/blockly>`.
It is a graphical programming language for clicking together geochemical analysis pipelines.
Those pipelines are generated into pandas pipelines that are excutable with a python interpreter.
The design goal of GeoArmadillo is easing the programming of geochemical data analysis pipelines even for non programmers.
As the graphical pipelines as well as the python code are sharable artifacts, we hope that the GeoAramadillo project supports more transparent data processing in the geochemistry community.
Finally, we hope that automating an error prone and sometimes tedious task creates more time for scientist to interpet results and work with the data instead of doing the processing.

The documentation is split in four parts. It first describes the general :ref:`pipeline concept <GeoArmadillo-pipeline>`, followed by explaining the :ref:`blocks <GeoArmadillo-blocks>` that can be used to construct the analysis pipelines. :ref:`Examples <GeoArmadillo-example>` conclude this documentation. The last part links to the documentation of the GeoArmadillo python library and shortly describes the general layout for generating python code from a block.

Here are the entry points for the four blocks:

.. toctree::
   :maxdepth: 2
   :caption: User Docs

   pipelines/pipelines
   blocks/index
   examples/index

.. toctree::
   :maxdepth: 2
   :caption: How To

   dev/getting_started

.. toctree::
   :maxdepth: 2

   impressum

GeoArmadillo Mental Model
#########################
To add some context for using GeoArmadillo, we explain the idea for designing GeoArmadillo. It should help to understand what a pipeline, a dataframe, and pandas is.

Pipelines are configurable hardcoded programming routines that reexecute always the same analysis with the configured thresholds on the input data of the pipeline and create always the sames analysis artifacts for the input data.

`Pandas <https://pandas.pydata.org>`_ is one very popular libary for working with tabular data in python.
It started as a statistic tool powered by `NumPy <https://numpy.org>`_, the main library for running scientific computing in python.
Pandas added a convenient way to load tabular data into memory and to manipulate it there. The class holding the data in memory is the :class:`DataFrames <pandas.DataFrame>`. Therefore, we tend to talk about data as dataframes in the GeoArmadillo context.

GeoArmadillo allows to click analysis pipeline togehter by using blocks. It then generates the panadas pipeline in python from the graphical collection of blocks. In addition, we tried our best to make some educated guesses regarding encodings and file endings to make reading and writing files easier. The language assumes that there is one pipeline processing a set of values retrieved from measuring a sample. The pipeline transforms this set of data, produces side products, and potentially persists results of the analysis to the file system.

`Pyrolite <https://pyrolite.readthedocs.io>`_ is greate panadas extension that takes care of many geochemical analysis tasks. We integrated this heavily in the generated code of GeoArmadillo and ocassionally link directly into their docs.

Variables and Constant Inputs
#############################

.. image:: images/concrete_input_category.png
	:alt: The *Concrete Inputs* in the toolbox prefixed with a red stripe.


Variables
==========

GeoArmadillo uses the Blockly features to define variables.
After clicking on *create variable...* in the variables section of the toolbox,
Blockly creates a set of *Blocks* for accessing the variable.

This is the example output of creating the variable *my model*.

.. image:: images/variables.png

Currently, GeoArmadillo only uses the lowermost *Variable Block*, which can be joined into other blocks.

Paths
=======

To enter a file path in the file system, please use the *File Path Block*. The path can be absolute or relative:

.. image:: images/file_path_input.png
	:alt: a path input

Text
====

Text is represented by the green *Text Box*:

.. image:: images/text_input.png

Numbers
=======

Numbers are defined by the purple *Number Block*:

.. image:: images/number_input.png



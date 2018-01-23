.. _ipython_directive:

=================
Ipython Directive
=================

The ipython directive is a stateful ipython shell for embedding in
sphinx documents.  It knows about standard ipython prompts, and
extracts the input and output lines.  These prompts will be renumbered
starting at ``1``.  The inputs will be fed to an embedded ipython
interpreter and the outputs from that interpreter will be inserted as
well.  For example, code blocks like the following::

  .. ipython::

     In [136]: x = 2

     In [137]: x**3
     Out[137]: 8

will be rendered as

.. ipython::

   In [136]: x = 2

   In [137]: x**3
   Out[137]: 8

.. note::

   This tutorial should be read side-by-side with the Sphinx source
   for this document because otherwise
   you will see only the rendered output and not the code that
   generated it.  Excepting the example above, we will not in general
   be showing the liuteral rest in this document that generates the
   rendered output.


The state from previous sessions is stored, and standard error is
trapped.  At doc build time, ipython's output and std err will be
inserted, and prompts will be renumbered.  So the prompt below should
be renumbered in the rendered docs, and pick up where the block above
left off.

.. ipython::

    In [138]: z = x*4   # x is recalled from previous block

    In [139]: z

    In [23]: print z


You can create one or more pyplot plots and insert them with the
``@savefig`` decorator.

.. ipython::

   In [144]: from pylab import *

   @savefig plot_simple.png width=4in
   In [151]: plot([1,2,3]);

   # use a semicolon to suppress the output
   @savefig hist_simple.png width=4in
   In [151]: hist(np.random.randn(10000), 100);



.. _formatting-text:

Formatting text
===============

You use inline markup to make text *italics*, **bold**, or ``monotype``.

You can represent code blocks fairly easily::

   import numpy as np
   x = np.random.rand(12)

.. _sample:

*****************
Testing out stuff
*****************

In this doc we will try writing and extensions.


.. _using-math:

Using math
==========

In sphinx you can include inline math :math:`x\leftarrow y\ x\forall
y\ x-y` or display math

.. math::

  W^{3\beta}_{\delta_1 \rho_1 \sigma_2} = U^{3\beta}_{\delta_1 \rho_1} + \frac{1}{8 \pi 2} \int^{\alpha_2}_{\alpha_2} d \alpha^\prime_2 \left[\frac{ U^{2\beta}_{\delta_1 \rho_1} - \alpha^\prime_2U^{1\beta}_{\rho_1 \sigma_2} }{U^{0\beta}_{\rho_1 \sigma_2}}\right]

To include math in your document, just use the math directive; here is
a simpler equation::

    .. math::

      W^{3\beta}_{\delta_1 \rho_1 \sigma_2} \approx U^{3\beta}_{\delta_1 \rho_1}

which is rendered as

.. math::

   W^{3\beta}_{\delta_1 \rho_1 \sigma_2} \approx U^{3\beta}_{\delta_1 \rho_1}

.. _pyplots:

Inserting matplotlib plots
==========================

You can also inline code for plots directly, and the code will be
executed at documentation build time and the figure inserted into your
docs; the following code::

   .. plot::

      import matplotlib.pyplot as plt
      import numpy as np
      x = np.random.randn(1000)
      plt.hist( x, 20)
      plt.grid()
      plt.title(r'Normal: $\mu=%.2f, \sigma=%.2f$'%(x.mean(), x.std()))
      plt.show()

produces this output:

.. plot::

    import matplotlib.pyplot as plt
    import numpy as np
    x = np.random.randn(1000)
    plt.hist( x, 20)
    plt.grid()
    plt.title(r'Normal: $\mu=%.2f, \sigma=%.2f$'%(x.mean(), x.std()))
    plt.show()

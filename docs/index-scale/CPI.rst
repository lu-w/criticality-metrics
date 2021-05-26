Crash Potential Index (CPI)
===========================

Description
-----------

The CPI is a scenario-level metric and calculates the average probability that a vehicle can not avoid a collision by deceleration.
It sums over the probabilities that a given vehicle's :math:`{a}_{\mathit{long,req}}` exceeds its :math:`a_{\mathit{long},\mathit{min}}` for each time point and normalizes the value over the length of the scenario [Cunto2007]_ [Cunto2008]_.
The target value :math:`a_{\mathit{long},\mathit{min}}` is assumed to be normally distributed and dependent on factors such as road surface material and vehicle brakes.
While originally defined in discrete time, the CPI for a scenario can be defined in continuous time as

.. math::
		\mathit{CPI}(A_1, A_2) = \frac{1}{t_e-t_0}\int_{t_0}^{t_e}P({a}_{\mathit{long,req}}(A_1, A_2, t) < a_{1,\mathit{long,min}}(t)) \mathrm{dt}\,.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

No

Target values
~~~~~~~~~~~~~

Average CPI in simulation was found to be :math:`0.5\% \pm 0.3\%`, thus :math:`0.72\%` could be used [Cunto2008]_

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Intersecting predicted paths for a significant time span in the scenario

Inputs
~~~~~~

:math:`a_{\mathit{long,req}}`, :math:`a_{\mathit{long,min}}` probability distribution

Output scale
~~~~~~~~~~~~

:math:`[0,1]`, probability, ratio scale

Reliability
~~~~~~~~~~~

Depends on reliability of :math:`a_{\mathit{long,req}}`, but is potentially increased due to integration over time

Validity
~~~~~~~~

Comparable to BTN, potentially increased due to comparison with a normally distributed target value, but depends on validity of distribution [Guido2011]_, initially validated [Cunto2008]_

Sensitivity
~~~~~~~~~~~

Potentially high, but strongly depends on :math:`a_{\mathit{long,req}}` and validity of :math:`a_{\mathit{long,min}}` distribution for the given scenario

Specificity
~~~~~~~~~~~

Potentially high, but strongly depends on :math:`a_{\mathit{long,req}}` and validity of :math:`a_{\mathit{long,min}}` distribution for the given scenario

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time

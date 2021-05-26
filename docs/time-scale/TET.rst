Time Exposed TTC (TET)
======================

Description
-----------

The TET metric builds on the TTC together with a target value :math:`\tau` and is defined for a scenario as

.. math::
		\mathit{TET}(A_1,A_2,\tau) = \int_{t_0}^{t_e} \mathbf{1}_{\mathit{TTC}(A_1,A_2,t) \le \tau}\mathrm{dt}

where :math:`\mathbf{1}` denotes the indicator function [Minderhoud2001]_ [Johnsson2018]_.
The TET measures the amount of time for which the TTC is below a given target value :math:`\tau`.
The dependency of the TET on the scenario duration could easily be eliminated through division by :math:`t_e-t_0`.
Note that, while originally defined only for discrete time, we generalized the formula to continuous time.
Moreover, let us mention that the idea of 'time exposed below target value' can readily be adapted to any metric together with a target value and is essentially independent of the TTC.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes, but only retrospectively

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Depends on the underlying metric, e.g.\ TTC

Scenario type
~~~~~~~~~~~~~

Depends on the underlying metric, e.g.\ TTC

Inputs
~~~~~~

Inputs of the underlying metric, e.g.\ TTC, together with a target value :math:`\tau`

Output scale
~~~~~~~~~~~~

:math:`[0,t_e-t_0]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Medium, but greater than TTC alone due to reductions in fluctuations by integration over time

Validity
~~~~~~~~

Depends on TTC, but at most medium, as a binary decision is made at each point in time, thus information is lost during aggregation. Can be valid for inter-scenario comparison [Minderhoud2001]_

Sensitivity
~~~~~~~~~~~

Comparable to TTC, possibly reduced depending on :math:`\tau`

Specificity
~~~~~~~~~~~

Comparable to TTC, increased compared to using only TTC without time integration

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Depends on the underlying metric

Time mode
^^^^^^^^^
Depends on the underlying metric, e.g. linear time in case of TTC

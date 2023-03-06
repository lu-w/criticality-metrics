Time Integrated TTC (TIT)
=========================

Description
-----------

Similar to the TET, the TIT [Minderhoud.2001]_ is a scenario level metric based on the TTC and is given as

.. math::
		\mathit{TIT}(A_1,A_2,\tau) = \int_{t_0}^{t_e} \mathbf{1}_{\mathit{TTC}(A_1,A_2,t) \le \tau}(\tau - \mathit{TTC}(A_1,A_2,t)) \mathrm{dt}.

It aggregates the difference between the TTC and a target value :math:`\tau` in the time interval :math:`[t_0, t_e]`.
Therefore, the metric reflects criticality more accurately than the TET.
As for the TET, the construction of the TIT is independent of the TTC and can be adapted for other metrics.

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

Depends on the underlying metric, e.g. TTC

Scenario type
~~~~~~~~~~~~~

Depends on the underlying metric, e.g. TTC

Inputs
~~~~~~

Inputs of the underlying metric, e.g. TTC, together with a target value :math:`\tau`

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, s :math:`\cdot` x, where x is unit of the underlying metric (e.g. time squared s² for TTC), ratio scale

Reliability
~~~~~~~~~~~

Medium, but greater than TTC alone due to reductions in fluctuations by integration over time

Validity
~~~~~~~~

Higher than TET as continuous information is not lost during aggregation [Minderhoud2001]_, but also dependent on TTC

Sensitivity
~~~~~~~~~~~

Comparable to TTC, possibly even reduced depending on :math:`\tau`

Specificity
~~~~~~~~~~~

Comparable to TTC, increased compared to using only TTC without time integration [Guido2011]_

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Depends on the underlying metric

Time mode
^^^^^^^^^
Depends on the underlying metric, e.g. linear time in case of TTC

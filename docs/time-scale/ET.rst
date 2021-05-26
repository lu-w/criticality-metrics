Encroachment Time (ET)
======================

Description
-----------

The ET metric, proposed by Allen et al. [Allen1978]_, measures the time that an actor :math:`A_1` takes to encroach a designated conflict area CA, i.e.

.. math::
		\mathit{ET}(A_1,\mathit{CA})  = t_{\text{exit}}(A_1,\mathit{CA}) - t_{\text{entry}}(A_1,\mathit{CA})\,.

While the value of ET is loosely correlated with criticality, it completely ignores the dynamics and behavior of any other involved actor.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

No

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Any scenario with a conflict area (containing a potential intersection point

Inputs
~~~~~~

CA, :math:`t_{\mathit{entry}}(A_1,\mathit{CA})`, :math:`t_{\mathit{exit}}(A_1,\mathit{CA})`

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Low, changes in criticality are reflected marginally in ET, repetition on multiple days showed high measurement variance [Allen1978]_

Validity
~~~~~~~~

Low, as only one actor is considered; validation against historical collision records was performed on one intersection, but results were not significant [Allen1978]_

Sensitivity
~~~~~~~~~~~

Low, as the validity of the metric is low and no target values exist

Specificity
~~~~~~~~~~~

Low, as the validity of the metric is low and no target values exist

Prediction model
~~~~~~~~~~~~~~~~

None, since a-posteriori

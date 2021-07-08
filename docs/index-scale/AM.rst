Accident Metric (AM)
====================

Description
-----------

AM evaluates whether an accident happened in a scenario:

.. math::
		\mathit{AM}(\mathit{Sc}) =
		\begin{cases}
			0, \quad \text{no accident happened during } \mathit{Sc}, \\
			1, \quad \text{otherwise.}
		\end{cases}

This simplistic metric is implicitly used in accident databases, such as `GIDAS
<https://www.gidas.org/>`_.
It fails to identify critical non-accident scenarios.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

No

Target values
~~~~~~~~~~~~~

Not necessary

Subject type
~~~~~~~~~~~~

Any

Scenario type
~~~~~~~~~~~~~

Any

Inputs
~~~~~~

Any parameter combination that allows determination of whether an accident happened or not

Output scale
~~~~~~~~~~~~

:math:`\{0,1\}`, nominal scale

Reliability
~~~~~~~~~~~

Low, as a change in accident outcome can be related to only minor changes in criticality (i.e. near misses)

Validity
~~~~~~~~

Medium, due to maximal specificity but low sensitivity

Sensitivity
~~~~~~~~~~~

Low, as all critical non-accidents are missed

Specificity
~~~~~~~~~~~

Maximal as all accidents are critical

Prediction model
~~~~~~~~~~~~~~~~

None, since a-posteriori

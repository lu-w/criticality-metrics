Proportion of Stopping Distance (PSD)
=====================================

Description
-----------

The PSD metric, proposed by Allen et al., is defined as the distance to a conflict area CA divided by the MSD [Allen1978]_ [Mahmud2017]_ [Guido2011]_ [Astarita2012]_.
Therefore,

.. math::
		\mathit{PSD}(A_1,\mathit{CA},t) = \frac{d(p_1(t),p_\mathit{CA}(t))}{\text{MSD}(A_1,t)} \text{, } \text{MSD}(A_1,t) = \frac{\|v_1(t)\|_2^2}{2|a_{1,\mathit{long,min}}(t)|}\,.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

< 1 (point of no return), 1.5 (scenario classification) [Huber2020]_

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Any scenario with a conflict area (containing a potential intersection point)

Inputs
~~~~~~

CA, position :math:`p_1`, velocity :math:`v_1`, maximal deceleration of ego :math:`a_{1,\mathit{long,min}}`

Output scale
~~~~~~~~~~~~

:math:`[0, \infty)`, number, ratio scale

Reliability
~~~~~~~~~~~

Can be reduced if actor tries to bypass conflict area in order to avoid collision, reliability higher than ET [Allen1978]_

Validity
~~~~~~~~

Low, depending on validity of the conflict area; found to have lowest relation to collision history for an unprotected left turn scenario with a static CA [Allen1978]_

Sensitivity
~~~~~~~~~~~

High, assuming that the conflict area is defined as a dynamically changing predicted point of collision [Guido2011]_, reduced otherwise

Specificity
~~~~~~~~~~~

Low, if criticality is measured completely independent of other actors in the scenario, also low if defined relative to a predicted collision point [Guido2011]_

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time

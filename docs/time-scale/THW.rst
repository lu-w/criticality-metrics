Time Headway (THW)
==================

Description
-----------

The THW metric calculates the time until actor :math:`A_1` reaches the position of a lead vehicle :math:`A_2` [Jansson2005]_ [Junietz2018a]_.

.. math::
		\mathit{THW}(A_1,A_2,t) = \min \{ \tilde{t} \ge 0 \,\mid\, p_1(t+\tilde{t}) = p_2(t) \}

Analogously to THW, one can define the Headway (HW) metric [Jansson2005]_ simply as the distance to a lead vehicle, i.e.

.. math::
	\mathit{HW}(A_1,A_2,t) = d(p_1(t),p_2(t))\,.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

The THW, and HW in one example, are used by regulatory bodies in several countries to express driving recommendations and as a threshold for fines.

======= =========== ===================
Country Recommended Threshold for fines
======= =========== ===================
Germany 1.8 s       0.9 s
Sweden  3 s         1 s
Austria 2 s         0.4 s
======= =========== ===================

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Car following scenarios

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t

Output scale
~~~~~~~~~~~~

:math:`(0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Medium, comparable to HW with additional consideration of velocity

Validity
~~~~~~~~

Medium, comparable to HW with additional consideration of velocity

Sensitivity
~~~~~~~~~~~

High, indicated by its use in legislation [Junietz2018a]_, also considers velocity compared to HW

Specificity
~~~~~~~~~~~

Low, as comparable to HW, but additional consideration of velocity

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time

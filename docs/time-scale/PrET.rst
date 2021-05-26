Predictive Encroachment Time (PrET)
===================================

Description
-----------

Here, we summarize the various predictive versions of the PET.
The PrET [Neurohr2021]_ is the anticipated PET relative to an intersection point as predicted by the employed DMM, hence

.. math::
		\mathit{PrET}(A_1,A_2,t) = \min (\{|\tilde{t}_1 - \tilde{t}_2| \,\mid\, p_1(t+\tilde{t}_1) = p_2(t+\tilde{t}_2), \, \tilde{t}_1, \tilde{t}_2 > 0 \} \cup \{ \infty \})\,.

The Time Advantage (TA) metric [Hansson1975]_ can be interpreted as a special case of PrET for a constant velocity model, i.e. :math:`p_i(s+t) = p_i(t) + s v_i(t)`.
A scaled variant of the PrET, labeled Scaled Predictive Encroachment Time (SPrET) modifies the value of PrET by multiplication with the factor :math:`(\tilde{t}_1+\tilde{t}_2)`, with :math:`\tilde{t}_1` and :math:`\tilde{t}_2` as defined in the PrET formula, in order to decrease the weight of situations long before the predicted intersection [Neurohr2021]_.
This method therefore incorporates prediction uncertainty.

Properties
----------

.. note::
		Includes properties for SPrET and TA.

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

2 s (threshold for critical) and :math:`[2,3]` s (normal traffic) for TA [Laureshyn2010]_, 3 s (threshold for critical) for SPrET [Neurohr2021]_

Subject type
~~~~~~~~~~~~

Any two actors

Scenario type
~~~~~~~~~~~~~

Any scenario with a conflict area (containing a potential intersection point)

Inputs
~~~~~~

Static/dynamic objects and their state at time t, DMM for each object

Output scale
~~~~~~~~~~~~

:math:`[0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Comparable to PET, but additionally dependent on DMM

Validity
~~~~~~~~

Comparable to PET, but additionally dependent on DMM, increased validity for run-time applications; no empirical analysis available

Sensitivity
~~~~~~~~~~~

Comparable to PET, but additionally dependent on DMM

Specificity
~~~~~~~~~~~

Comparable to PET, but specificity decreases with increasing distance to intersection

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time

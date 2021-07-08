Conflict Severity (CS)
======================

Description
-----------

CS is concerned with solely estimating the severity of a potential collision in a scenario [Bagdadi2013]_.
It thus presents as a suitable factor that can enhance various collision probability metrics in ensuring a more accurate representation of criticality.
From the perspective of an actor :math:`A_1` performing a braking maneuver at time :math:`t_\mathit{evasive}`, it is defined as

.. math::
		\mathit{CS}(A_1, A_2) = \Delta v(A_1, A_2, t_\mathit{evasive}) - \left( \mathit{TTA}(A_1, A_2) \cdot \|a_{1}(t_\mathit{evasive})\|_2 \cdot \frac{m_2}{m_1 + m_2} \right) .

Thus, it compares the (extended) :math:`\Delta v` at time of the evasive maneuver against the :math:`\Delta v` at the potential collision point as predicted by TTA if :math:`A_1` conducts an emergency braking, assuming :math:`v_2(t_\mathit{evasive} + \mathit{TTA}(A_1, A_2)) = 0`. 
CS factors in the relative mass difference due to the correlation between severe injuries and fatality outcome, measured on the Abbreviated Injury Scale, and the mass ratio of the involved actors [Evans1994]_.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

No, as TTA can only be computed once evasive maneuver has been identified

Target values
~~~~~~~~~~~~~

Case study on manually labeled critical scenarios identified a mean CS of :math:`3.19 \pm 3.7`, but severity is dependent on speed and type of actors [Bagdadi2013]_

Subject type
~~~~~~~~~~~~

Any two actors, also suitable for VRUs

Scenario type
~~~~~~~~~~~~~

Any scenario for which a TTA can be determined

Inputs
~~~~~~

:math:`v_1(t_\mathit{evasive})`, :math:`v_2(t_\mathit{evasive})`, :math:`m_1, m_2`, :math:`\mathit{TTA}(A_1, A_2)`, :math:`a_{1,\mathit{min}}(t_\mathit{evasive})`

Output scale
~~~~~~~~~~~~

:math:`(-\infty,\infty)`, velocity (m/s), ratio scale

Reliability
~~~~~~~~~~~

Comparable to TTA

Validity
~~~~~~~~

High validity for severity estimation inside scenario type of TTA, as indicated by empirical analysis against a traffic conflict technique, specifically for actors with different masses [Bagdadi2013]_

Sensitivity
~~~~~~~~~~~

Medium, as for critical scenarios where no evasive maneuver is identified, CS returns no value

Specificity
~~~~~~~~~~~

Comparable to TTA, but increased due to consideration of severity

Prediction model
~~~~~~~~~~~~~~~~

Depends on prediction model of TTA

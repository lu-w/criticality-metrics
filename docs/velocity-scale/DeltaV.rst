
Delta-v (:math:`\Delta v`)
==========================

Description
-----------

:math:`\Delta v` is the change in speed over collision duration and widely used in collision databases, where it is typically calculated from post-collision measurements [Gabauer2006]_.
Introduced in the 1970s [Carlson1979]_, it uses the difference in speed to estimate the probability of a severe injury or fatality:

.. math::
		\Delta v(A_1) = \|v_1(t_\mathit{aftercol})\|_2-\|v_1(t_\mathit{beforecol})\|_2.

A more complex formula for two actors taking the masses into account is given by

.. math::
		\Delta v(A_1, A_2, t) = \frac{m_2}{m_1+m_2}(\|v_2(t)\|_2-\|v_1(t)\|_2),

for which also probabilistic studies have been done [Shelby2011]_.
An extended :math:`\Delta v` measure, which is additionally considering the mass as well as the driving angles of the collision participants, has been discussed by Laureshyn et al. [Laureshyn2017]_.

Joksch [Joksch1993]_ presents a model connecting :math:`\Delta v` to the probability :math:`P` of a two vehicle collision leading to a fatality using

.. math::
		P(A_1) \approx \left(\frac{\Delta v}{31.74\text{m}/\text{s}}\right)^4.

This connection provides an easily interpretable measure.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

70 km/h [Shelby2011]_ (deadly collisions), 40 km/h [Ryb2007]_ (higher mortality rate)

Subject type
~~~~~~~~~~~~

Any, but requires data basis for the target values depending on the involved traffic participants

Scenario type
~~~~~~~~~~~~~

Mainly collisions

Inputs
~~~~~~

- Assuming one traffic participant: :math:`v_1(t_\mathit{aftercol})` and :math:`v_1(t_\mathit{beforecol})`.
- Assuming two traffic participants: velocities :math:`v_i` and masses :math:`m_i` for :math:`i \in \{1, 2\}` over time

Output scale
~~~~~~~~~~~~

:math:`\left(-\infty,\infty\right)`, velocity (m/s), ratio scale, or :math:`\left[0,1\right]`, probability, ratio scale

Reliability
~~~~~~~~~~~

High reliability for collisions, greatly reduced for near-miss scenarios

Validity
~~~~~~~~

High, if used to estimate injury severity of a collision [Gabauer2006]_; very low if used for non-collision scenarios

Sensitivity
~~~~~~~~~~~

High for severity component of criticality, as it is often associated with a high :math:`\Delta v`, might also depend on DMM and MM

Specificity
~~~~~~~~~~~

Medium, non-criticality of collisions can be partially evaluated, but other factors influence non-criticality, e.g. impact angle and torsional rigidity of the vehicles

Prediction model
~~~~~~~~~~~~~~~~

None if used a-posteriori.

Otherwise:

Time window
^^^^^^^^^^^
Duration of collision

Time mode
^^^^^^^^^
Linear time

PTTC (Potential Time To Collision)
==================================

Description
-----------

The PTTC metric, as proposed by Wakabayashi et al. [Wakabayashi2003]_, constraints the general TTC metric by assuming constant velocity of :math:`A_1` and constant deceleration of :math:`A_2` in a car following scenario, where :math:`A_1` is following :math:`A_2`.
Then, the formula simplifies to

.. math::
		\mathit{PTTC}(A_1,A_2,t) = \frac{1}{-a_{2,\mathit{long}}(t)} \left(-\dot{d} \pm \sqrt{\dot{d}^2 + 2 (-a_{2,\mathit{long}}(t)) d}\right)

with :math:`\dot{d}= \dot{d}(p_1(t),p_2(t))` and :math:`d=d(p_1(t),p_2(t))` respectively. While imposing such constraints on the scenario type and the DMMs of the actors reduces the computational cost of evaluating the metric, 
its validity is significantly reduced compared to the general TTC.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

None found, but comparable to TTC

Subject type
~~~~~~~~~~~~

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Car following scenarios

Inputs
~~~~~~

Positions :math:`p_i` and velocities :math:`v_i` for :math:`i \in \{1,2\}` and acceleration :math:`a_2`

Output scale
~~~~~~~~~~~~

:math:`[0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Medium, but higher than a constant velocity TTC, as it increases the set of applicable scenarios by assuming constant deceleration of lead vehicle and constant velocity of following vehicle

Validity
~~~~~~~~

Medium, as the assumption of constant deceleration of lead vehicle and constant velocity of following vehicle is not viable for all car following scenarios; was exemplarily demonstrated to be more valid than a constant velocity TTC [Wakabayashi2003]_

Sensitivity
~~~~~~~~~~~

High inside the scenario type, as the metric's assumptions can be understood as an approximation of the worst-case for car following scenarios

Specificity
~~~~~~~~~~~

Low, as the assumptions may not be justified under all circumstances, thus metric can be raised too often

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Bound by assumptions on acceleration

Time mode
^^^^^^^^^
Linear time

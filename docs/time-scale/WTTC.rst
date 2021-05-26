Worst Time To Collision (WTTC)
==============================

Description
-----------

The WTTC metric extends the usual TTC by considering multiple traces of actors as predicted by an over-approximating DMM, i.e.

.. math::
		\mathit{WTTC}(A_1,A_2,t)  = \min_{p_1 \in \mathit{Tr}_1(t), p_2 \in \mathit{Tr}_2(t)}  (\{ \tilde{t} \ge 0 \,\mid\, d(p_1(t+\tilde{t}),p_2(t+\tilde{t})) = 0 \} \cup \{ \infty \}),

where :math:`\mathit{Tr}_1(t)` resp. :math:`\mathit{Tr}_2(t)` denotes the set of all possible trajectories available to actor :math:`A_1` resp. :math:`A_2` at time :math:`t`, as constraint by the employed DMM.
Similar to the TTC, the WTTC can be extended to multi-actor scenarios.
Defined by Wachenfeld et al. [Wachenfeld2016]_, it excels in selective data recording and data filtering applications.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

1 s (scenario classification) [Huber2020]_, comparison with ACC :math:`\tau` (gap time) made in [Wachenfeld2016]_

Subject type
~~~~~~~~~~~~

Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t

Output scale
~~~~~~~~~~~~

:math:`[0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Medium, as over-approximating DMM robustly assesses criticality increases (expert-based evaluation [Wachenfeld2016]_), but decreases potentially not reliably reflected

Validity
~~~~~~~~

Medium, as most critical scenarios can be detected depending on the DMM, but also not able to distinguish many uncritical ones, initial expert-based evaluation on four scenarios has been published [Wachenfeld2016]_

Sensitivity
~~~~~~~~~~~

Almost maximal, due to over-approximation of possible trajectories, depends on DMM (e.g. whether unstable dynamics are considered)

Specificity
~~~~~~~~~~~

Low, due to over-approximation of possible trajectories, depends on DMM

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Branching time

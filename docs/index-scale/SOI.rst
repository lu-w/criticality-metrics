Space Occupancy Index (SOI)
===========================

Description
-----------

The SOI defines a personal space for each actor and counts violations by other participants while setting them in relation to the analyzed period of time [Tsukaguchi1987]_ [Ogawa2007]_ [Johnsson2018]_.
For each actor :math:`A_i` at time :math:`t`, a personal space :math:`\mathit{Sp}(A_i, t)` is defined.
At time :math:`t`, if there exists some :math:`A_j \neq A_i` s.t. :math:`\mathit{Sp}(A_i, t) \cap \mathit{Sp}(A_j, t) \neq \emptyset`, a violation of the personal space of :math:`A_i` is given.
The number of conflicts is then given as :math:`C(A_1, \mathcal{A}, t) = \sum_{A_j \in \mathcal{A}\setminus\{A_1\}} [\mathit{Sp}(A_1) \cap \mathit{Sp}(A_j) \neq \emptyset]`, where :math:`[\cdot]` denotes the Iverson bracket.
Thus, for a given scenario in the time interval :math:`[t_0, t_e]`, the conflict index is defined as

.. math::
		\mathit{SOI}(A_1,\mathcal{A}) = \sum_{t=t_0}^{t_e} C(A_1, \mathcal{A}, t).

SOI was introduced for bicycles and pedestrians, however, it is possible to formulate a similar concept for road vehicles.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes, but only retrospectively

Target values
~~~~~~~~~~~~~

No

Subject type
~~~~~~~~~~~~

Originally defined for VRUs, could be extended to road vehicles

Scenario type
~~~~~~~~~~~~~

Any scenario

Inputs
~~~~~~

Actor type, size of safe space depending on type

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, hertz (1/s), ratio scale

Reliability
~~~~~~~~~~~

Medium, due to the nominal nature of the conflict definition, which leads to fluctuations if vehicles exist close the boundaries of personal space

Validity
~~~~~~~~

Medium, since temporal and dynamical aspects are ignored due to binary evaluation; no empirical analysis available

Sensitivity
~~~~~~~~~~~

Medium, as already a single safe space violation can lead to an accident

Specificity
~~~~~~~~~~~

Medium, as multiple safe space violations are associated but with but not necessarily causative for accidents

Prediction model
~~~~~~~~~~~~~~~~

None, since a-posteriori

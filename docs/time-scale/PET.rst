Post Encroachment Time (PET)
============================

Description
-----------

The PET [Allen1978]_ has been widely used as metric for the a-posteriori analysis of traffic data [Laureshyn2010]_ [Peesapati2018]_ [Johnsson2018]_.
The PET calculates the time gap between one actor leaving and another actor entering a designated conflict area.
Assuming :math:`A_1` leaves CA before or at the time :math:`A_2` enters it (i.e., :math:`t_{\text{entry}}(A_2,\mathit{CA}) \geq t_{\text{exit}}(A_1,\mathit{CA})`), we define

.. math::
		\mathit{PET}(A_1,A_2,\mathit{CA}) = t_{\text{entry}}(A_2,\mathit{CA}) - t_{\text{exit}}(A_1,\mathit{CA})\,.

Note that the PET is undefined for scenarios where the above assumption does not hold.
This can happen if both actors have entered CA before any of them was able to leave it.
Moreover, depending on the definition of CA, a PET of 0 might not indicate an accident [Laureshyn2010]_.

Allen et al. also introduce two semi-predictive versions of the PET, called GT and IAPE, which inherit the properties of PET and are not considered any further here [Allen1978]_.
Both metrics, GT and IAPE, measure :math:`t_{\text{exit}}(A_1,\mathit{CA})` and predict :math:`t_{\text{entry}}(A_2,\mathit{CA})` at different points in time using a constant velocity model.
Therefore, they can be seen as an evaluation of the PrET at a specific time point.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

No

Target values
~~~~~~~~~~~~~

<1 s [Varhelyi1998]_, 1.5 s [Peesapati2018]_ (threshold for critical), >2 s [Varhelyi1998]_ (normal interaction), multiple intersections, vehicle classes, and thresholds have been studied [Paul2020]_

Subject type
~~~~~~~~~~~~

Any two actors

Scenario type
~~~~~~~~~~~~~

Any scenario with a conflict area (containing a potential intersection point)

Inputs
~~~~~~

CA, :math:`t_{\mathit{exit}}(A_1,\mathit{CA})`, :math:`t_{\mathit{entry}}(A_2,\mathit{CA})`

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, time (s), ratio scale

Reliability
~~~~~~~~~~~

Can be reduced if reactive behavior leads to :math:`t_\mathit{exit}(A_1, \mathit{CA})` or :math:`t_\mathit{entry}(A_2, \mathit{CA})` being undefined (e.g. :math:`A_1` does full stop inside :math:`\mathit{CA}`)

Validity
~~~~~~~~

According to Allen, 'conceptually sound descriptor', correlation with collision history was highest, but non-significant [Allen1978]_, possibly reduced if actor bypasses CA for collision avoidance (e.g. emergency braking before reaching CA)

Sensitivity
~~~~~~~~~~~

Medium, as highly-critical braking maneuvers avoiding collisions may still result in a high PET due to re-accelerating [Zheng2019]_

Specificity
~~~~~~~~~~~

High, as it is unlikely for an uncritical scenario to exhibit a low PET value due to the implicated spatio-temporal proximity of the actors

Prediction model
~~~~~~~~~~~~~~~~

None, since a-posteriori

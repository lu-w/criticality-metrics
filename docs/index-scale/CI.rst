Conflict Index (CI)
===================

Description
-----------

The conflict index enhances the \acs{PET} metric with a collision probability estimation as well as a severity factor [Alhajyaseen2015]_.
For this, the estimated kinetic energy that would have been released assuming a hypothetical collision between :math:`A_1` and :math:`A_2` at their states when entering (:math:`A_2`) resp. exiting (:math:`A_1`) the conflict area is estimated:

.. math::
		\mathit{CI}(A_1, A_2, \mathit{CA}, \alpha, \beta) = \frac{\alpha \Delta K_e}{e^{\beta \mathit{PET}(A_1, A_2, \mathit{CA})}}

where the denominator is a collision probability estimation.

Therefore, it is proposed that the actual collision probability is proportional to :math:`e^{- \beta \mathit{PET}(A_1, A_2, \mathit{CA})}` with :math:`\beta` being a calibration factor dependent on the scenario factors, e.g. country, road geometry, or visibility and :math:`[\beta] = \text{s}^{-1}`.
The nominator represents a collision severity measure, where :math:`\alpha \in [0,1]` is again a calibration factor for the proportion of energy that is transferred from the vehicle's body to its passengers and :math:`\Delta K_e` is the predicted absolute change in kinetic energy before and after the predicted collision.

:math:`\Delta K_e` is estimated based on the masses as well as velocities and angles at time of entering (:math:`A_2`) resp. exiting (:math:`A_1`) the conflict area.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

None, since PET can only be determined a-posteriori

Target values
~~~~~~~~~~~~~

None given

Subject type
~~~~~~~~~~~~

Any two actors, but most suitable for road vehicles (automated and humans)

Scenario type
~~~~~~~~~~~~~

Any scenario with a conflict area (containing a potential intersection point)

Inputs
~~~~~~

CA, :math:`\theta_1(t_{\mathit{exit}}(A_1,\mathit{CA}))`, :math:`\theta_2(t_{\mathit{entry}}(A_2,\mathit{CA}))`, :math:`v_1(t_{\mathit{exit}}(A_1,\mathit{CA}))`, :math:`v_2(t_{\mathit{entry}}(A_2,\mathit{CA}))`, :math:`m_1, m_2`, :math:`\mathit{PET}(A_1, A_2, \mathit{CA})`, calibration factors :math:`\alpha, \beta`

Output scale
~~~~~~~~~~~~

:math:`(-\infty, \infty)`, joule (:math:`\text{kg}\cdot \text{m}^2 \cdot \text{s}^{-2}`), ratio scale

Reliability
~~~~~~~~~~~

Comparable to PET

Validity
~~~~~~~~

Initial validation was performed, exponential relationship to number of collisions over varying intersections was shown with a reasonably high coefficient of determination [Alhajyaseen2015]_

Sensitivity
~~~~~~~~~~~

Depends on the sensitivity of PET, but potentially increased due to consideration of severity

Specificity
~~~~~~~~~~~

Depends on the specificity of PET, but potentially increased due to consideration of severity

Prediction model
~~~~~~~~~~~~~~~~

None, since a-posteriori

Accepted Gap Size (AGS)
=======================

Description
-----------

The AGS is a quantity which can be used to measure the complexity of a traffic situation.
In general it quantifies the gap or the actual space between actors desired or required for others to make a positive action decision.
Therefore, for a given actor :math:`A_1` at time :math:`t`, its model approximates the temporal or spatial distance that is predicted to be required for the action of :math:`A_1`, i.e.

.. math::
		\mathit{AGS}(A_1, t) = \min \{ s \geq 0\, |\, \mathit{action}(A_1, t, s) = 1 \},

where :math:`\mathit{action(A_1, t, s)}` is a (complex) model predicting on a binary scale, based on the circumstances at time :math:`t`, whether :math:`A_1` will come to positive action decision for the gap size :math:`s`.

This model can for example refer to the size of the gap in a stream of pedestrians passing a crosswalk, which is required for a waiting driver to decide to cut in and continue.
For a time dependent distance measure, the metric is also called the accepted lag size.
In general the more critical a traffic situation is, the larger the desired distance to other actors will be.
For example, at an intersection, drivers tend to wait if the situation is unclear and the intersection itself is already crowded.

The interACT project used the AGS in such a way to analyze traffic complexity [InteractD61]_.
Their analysis shows that the accepted gap is a highly complex model depending on a vast set of inputs, such as gap size, driver age, gender, waiting time, distraction, and condition of the street.
Furthermore, to the authors' knowledge, the formulation of the AGS has not yet been generalized and is bound to specific situations.

Alhajyaseen et al. studied the accepted gap resp. lag size for a left-turn traffic situation and empirically developed a probabilistic model using Cumulative Weibull distributions [Alhajyaseen2013]_.
The natural link between the accepted gap size and the Time To Arrival has been studied by Petzoldt [Petzold2014]_.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Depends on model and inputs used

Target values
~~~~~~~~~~~~~

4.5s [Rakha2011]_ (for left-turn)

Subject type
~~~~~~~~~~~~

Any, but requires a sound data basis or study for the gap acceptance model itself

Scenario type
~~~~~~~~~~~~~

Intersecting predicted paths for a significant time span in the scenario

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time $t$, other quantities for the underlying model (e.g. driver age or road condition)

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, originally distance (m), sometimes seconds (s), ratio scale

Reliability
~~~~~~~~~~~

Depends on the influencing factors considered by :math:`\mathit{action}` model

Validity
~~~~~~~~

High under the assumption of a valid data basis for the acceptance model w.r.t. the given scenario [Alhajyaseen2013]_

Sensitivity
~~~~~~~~~~~

Medium, only aspects of criticality regarding gap acceptance are measured, thus critical scenarios may be missed (e.g. rear-end collisions)

Specificity
~~~~~~~~~~~

High, as an increased AGS is only present in highly complex situations which are often inherently critical

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Depends on the quality of behavior prediction models

Time mode
^^^^^^^^^
Linear time

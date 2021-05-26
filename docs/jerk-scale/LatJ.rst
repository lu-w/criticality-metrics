Lateral Jerk (LatJ)
===================

Description
-----------

Please refer to the :doc:`longitudinal jerk</jerk-scale/LongJ>`.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

0.1 g/s (curve safety) [Ambros2019]_, 0.5 g/s [UNECE79]_, other upper bounds exist [ISO11270]_ [ISO22179]_

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Any involving a rapid steering maneuver, e.g. curve driving, evasion maneuver

Inputs
~~~~~~

Jerk :math:`j_i` at time t

Output scale
~~~~~~~~~~~~

:math:`(-\infty,\infty)`, jerk (g/s or m/s³), ratio scale

Reliability
~~~~~~~~~~~

High, as jerk outcome is often in accordance with a change in criticality [Bagdadi2013]_

Validity
~~~~~~~~

Low for run-time applications, as jerk makes criticality only measurable on reaction, but high for a-posteriori analysis under the assumption of drivers being reacting to critical events [Bagdadi2013]_

Sensitivity
~~~~~~~~~~~

High, since critical situations either require the driver to react abruptly, or the jerk will be high during the collision itself

Specificity
~~~~~~~~~~~

Low, as critical situations can happen without lateral acceleration of the actors

Prediction model
~~~~~~~~~~~~~~~~

None, since instantaneous

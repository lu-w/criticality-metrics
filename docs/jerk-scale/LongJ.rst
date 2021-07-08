Longitudinal Jerk (LongJ)
=========================

Description
-----------

Jerk is the rate of change in acceleration, and thus quantifies over the abruptness of a maneuver.
The measure can simply be formulated as

.. math::
		\mathit{LatJ}(A_1,t) = j_{1,\mathit{lat}}(t), \quad \mathit{LongJ}(A_1,t) = j_{1,\mathit{long}}(t).

One of the main applications of the measure is the assessment of driving states.
Using the jerk, it possible to discern different classes of driving styles, e.g. comfortable, angry, anxious, and risky modes [Bellem2018]_ [Feng2017]_.
Ambros et al. derived an indicator using the longitudinal jerk for the safety of a horizontal curve [Ambros2019]_.
Another important application area are trains and buses, where for standing passengers, the jerk enables an analysis of their reaction capabilities on the maneuver, e.g. during a change of tracks of a train [Powell2015]_.

The usage of \acs{longj} and \acs{latj} varies, e.g. \acs{longj} can be utilized in the design of an \ac{ACC} \cite{ISO15622} function, whereas \acs{latj} is used for functions dealing with steering maneuvers, e.g. a \ac{LKAS} \cite{ISO11270}. 

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

1.2 g/s (reference driver) [UNECE157]_, 1.44 g/s (AEB) [UNECE157]_, other upper bounds exist [ISO11270]_ [ISO15622]_

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Any involving a rapid braking or kickdown maneuver

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

Low, as critical situations can happen without longitudinal acceleration of the actors

Prediction model
~~~~~~~~~~~~~~~~

None, since instantaneous

Time To Collision (TTC)
=======================

Description
-----------

For two actors :math:`A_1`, :math:`A_2` at time :math:`t`, the TTC metric returns the minimal time until :math:`A_1` and :math:`A_2` collide using an underlying one-track prediction model for both actors, 
or infinity if the predicted trajectories do not intersect.
It is defined by

.. math::
		\mathit{TTC}(A_1,A_2,t)  = \min \; (\{ \tilde{t} \ge 0 \,\mid\,  d(p_1(t+ \tilde{t}), p_2(t+ \tilde{t})) = 0 \} \cup \{ \infty \}).

A variety of the TTC, called Modified-TTC, is extended under the name of CrI, where it is multiplied with a velocity-based severity estimate [ozbay2008derivation]_. 


For car following scenarios and from the point of view of a distinguished actor, the TTC delivers a quality estimate on the temporal proximity to a collision that is induced by a maneuver of an actors, e.g. by a braking maneuvers of a lead vehicle. 
Its validity is however greatly reduced for most DMMs within intersection scenarios as well as, if not meaningfully aggregated over actors, in multi actor scenes. 
Furthermore, the resulting time still needs to be interpreted w.r.t. the abilities and environment of :math:`A_1`, either by using appropriate target values or composed metrics such as TTM. 


One possible aggregate of the TTC to the scenario level is the TTA metric which is defined as
 
.. math::
	\mathit{TTA}(A_1, A_2) = \mathit{TTC}(A_1, A_2, t_{\mathit{evasive}})

with :math:`t_{\mathit{evasive}}` being the first time where an evasive maneuver is performed [johnsson2018search]_. 
Such aggregations over time can increase the TTC's validity when used for a retrospective assessment. 
Further information is given when discussing the other two time aggregates of TTC in this work, TET and TIT.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

.. req:: Rune-time-capability
	:id: TTC_RTC
	:style: metricprop

	Yes

Target values
~~~~~~~~~~~~~

.. req:: Target values
	:id: TTC_TV

	1 s [Hayward1972]_ [Huber2020]_, 1.5 s, [Sacchi2016]_, [ElBasyouny2013]_, 3 s [Autey2012]_ (all data separation), 1.22 s [Junietz2018a]_ (threshold for critical)

Subject type
~~~~~~~~~~~~

.. req:: Subject type
	:id: TTC_SUT
	
	Optimal for road vehicles (automated and human), sub-optimal for VRUs

Scenario type
~~~~~~~~~~~~~

.. req:: Scenario type
	:id: TTC_SCT
	
	Overlapping predicted trajectories for a significant time span in the scenario

Inputs
~~~~~~

.. req:: Inputs
	:id: TTC_I
	
	Static/dynamic objects and their state (pose, shape, etc.) at time t

Output scale
~~~~~~~~~~~~

.. req:: Output scale
	:id: TTC_OS
	
	:math:`[0,\infty]`, time (s), ratio scale

Reliability
~~~~~~~~~~~

.. req:: Reliability
	:id: TTC_R
	
	Highly depending on the reliability of the predicted collision, for most DMMs reliability is reduced [Allen1978]_

Validity
~~~~~~~~

.. req:: Validity
	:id: TTC_V
	
	Medium, depending on the length of time interval with collision prediction in the scenario, as well as the validity of the DMM [StAubin2015]_

Sensitivity
~~~~~~~~~~~

.. req:: Sensitivity
	:id: TTC_SE
	
	Medium, as, due to the linear-time DMM, critical scenes may not have a predicted collision in the DMM [Allen1978]_

Specificity
~~~~~~~~~~~

.. req:: Specificity
	:id: TTC_SP
	
	High, as, due to the linear-time  DMM, only few uncritical situations have a predicted collision in the DMM [Zheng2019]_

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^

.. req:: Time window
	:id: TTC_PM_W
	
	Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^

.. req:: Time mode
	:id: TTC_PM_M
	
	Linear time


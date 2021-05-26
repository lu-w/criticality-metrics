Responsibility Sensitive Safety Dangerous Situation (RSS-DS)
============================================================

Description
-----------

The Responsibility Sensitive Safety (RSS) framework is designed to formally guarantee safety during a vehicle's drive.
It was developed to reflect a sound interpretation of law that leads to a efficient and verifiable AV behavior [Shalev-Shwartz2017]_.
To approach this goal, RSS states a set of mathematical rules.
Note that it has been shown that they may not consider certain edge cases, e.g. during braking maneuvers and on varying road surfaces and slopes, as well as perception uncertainty [Koopman2019]_.

In order to assess the safety of the ego, RSS formalizes the safe lateral and longitudinal distances :math:`d_\mathit{min}^\mathit{lat}` and :math:`d_\mathit{min}^\mathit{long}`, depending on the current road geometry.
Based on this, the metric RSS-DS for the identification of a dangerous situation :math:`S` with a set of actors :math:`\mathcal{A}` is defined as

.. math::
	\mathit{RSS}\text{-}\mathit{DS}(A_1, \mathcal{A}) =
	\begin{cases}
		1, \exists A_i \in \mathcal{A}\setminus\{A_1\}. d^\mathit{lat}(A_1, A_i) < d_\mathit{min}^\mathit{lat} \wedge d^\mathit{long}(A_1, A_i) < d_\mathit{min}^\mathit{long}, \\
		0, \text{otherwise.}
	\end{cases}

Note that to determine :math:`d_\mathit{min}^\mathit{lat}` and :math:`d_\mathit{min}^\mathit{long}`, different prediction models are utilized to estimate which distances are classified as safe, e.g. in intersections, highways, and unstructured roads.

The concept of measuring the safe distance has been extended by Jesenski et al. to measure the temporal extent to which the ego was not able to mitigate the dangerous situation [Jesenski2020]_.
In accident research, a similar concept of classifying situations as safe and unsafe depending on longitudinal stopping distances was introduced as the Stopping Distance Index (SDI) [Oh2006]_.
In turn, the SDI is partially based on the idea of the Potential Index for Collision with Urgen Deceleration (PICUD) [Uno2002]_, both comparing the stopping distances of the lead and following vehicle under emergency braking.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~



Target values
~~~~~~~~~~~~~



Subject type
~~~~~~~~~~~~



Scenario type
~~~~~~~~~~~~~



Inputs
~~~~~~



Output scale
~~~~~~~~~~~~



Reliability
~~~~~~~~~~~



Validity
~~~~~~~~



Sensitivity
~~~~~~~~~~~



Specificity
~~~~~~~~~~~



Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^


Time mode
^^^^^^^^^

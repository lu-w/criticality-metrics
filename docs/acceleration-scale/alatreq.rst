Required Longitudinal Acceleration (:math:`{a}_{\mathit{lat,req}}`)
===================================================================

Description
-----------

Please refer to the :doc:`required longitudinal acceleration<alongreq>`.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

:math:`[-7,-2.5]` m/s² dependent on speed [Benmimoun2011]_ (incident detection)

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Intersecting predicted paths for a significant time span in the scenario

Inputs
~~~~~~

:math:`v_i, a_i, p_i` for :math:`i \in \{1,2\}` assuming the constant acceleration motion model

Output scale
~~~~~~~~~~~~

:math:`(-\infty, \infty)`,  acceleration (m/s²), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that collisions can be reliably predicted in the prediction model

Validity
~~~~~~~~

High, but only lateral evasion considered, knowledge on vehicle capabilities necessary for interpretation [Zheng2019]_

Sensitivity
~~~~~~~~~~~

High, as most critical situations between two actors impose a high required acceleration at some point

Specificity
~~~~~~~~~~~

Medium, as there exists situations with intersecting paths of actors, but planned trajectory is deviating (e.g. turning maneuvers)

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time

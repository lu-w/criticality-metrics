Required Acceleration (:math:`{a}_{\mathit{req}}`)
==================================================

Description
-----------

Based on :math:`{a}_{\mathit{long,req}}` and :math:`{a}_{\mathit{lat,req}}`, the aggregate metric :math:`{a}_{\mathit{req}}` can be defined in various ways [Jansson2005]_, e.g. by taking the norm of the required acceleration of both directions, i.e.

.. math::
		{a}_{\mathit{req}}(A_1, A_2, t) = \sqrt{{a}_{\mathit{long,req}}(A_1, A_2, t)^2 + {a}_{\mathit{lat,req}}(A_1, A_2, t)^2}\,.

More complex aggregates might also take into account the maximally available acceleration in each direction by incorporating the coefficient of friction :math:`\mu`.
Moreover, let us mention the conditional required acceleration :math:`{a}_{\mathit{req,cond}}` combining :math:`{a}_{\mathit{req}}` and SPrET for the analysis of urban intersection scenarios [Neurohr2021]_.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

-3.4 m/s² (scenario classification) [Huber2020]_, other values for lateral and longitudinal required acceleration may apply

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Intersecting predicted paths for a significant time span in the scenario

Inputs
~~~~~~

:math:`{a}_{\mathit{lat,req}}`, :math:`{a}_{\mathit{long,req}}`

Output scale
~~~~~~~~~~~~

:math:`(-\infty, \infty)`,  acceleration (m/s²), ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption that the non-collision condition can be reliably predicted

Validity
~~~~~~~~

High, found to be lower than TTC and PET for large thresholds [Zheng2019]_, but comparable to CPI [Guido2011]_

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

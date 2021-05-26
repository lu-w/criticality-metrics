Aggregated Crash Index (ACI)
============================

Description
-----------

The ACI measures the collision risk for car following scenarios by extending the concept of CPI from :math:`{a}_{\mathit{req}}` to multiple factors.
First, a probabilistic causal model of the scenario type under consideration is needed to derive a collision tree with all possible outcomes and their probabilities [Kuang2015]_.

The concrete outcomes are represented by the tree's leaf nodes :math:`L_j`.
Every leaf node has a value :math:`C_{L_j}` which is 0 in case of no collision and 1 in case of a collision.
None-leaf nodes in the tree represent conditions which may occur during the scenario.
Similar to CPI, the conditions are defined based on other metrics, e.g. the current stopping time of the lead vehicle being smaller than a lognormally distributed reaction time.
The collision risk :math:`\mathit{CR}_{L_j}(S)` of a leaf node :math:`L_j` given a scene :math:`S` is hence represented by :math:`\mathit{CR}_{L_j}(S) = P(L_j) \cdot C_{L_j}`, where :math:`P(L_j)` is the probability of satisfying all conditions necessary to reach :math:`L_j` in the collision tree, when given the current conditions in the scene :math:`S`.

The end result of ACI is an aggregation of all collision risks in a scene :math:`S`, i.e.

.. math::
		\mathit{ACI}(S) = \sum_{j=1}^n \mathit{CR}_{L_j}(S) \text{,}

with :math:`n` being the number of leaf nodes in the collision tree.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

No

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Road vehicles [Kuang2015]_, could be extended to other road users

Scenario type
~~~~~~~~~~~~~

Car following

Inputs
~~~~~~

Static/dynamic objects and their state (pose, shape, etc.) at time t, probabilistic causal model and collision tree, probability for each scenario outcome

Output scale
~~~~~~~~~~~~

:math:`[0,1]`, risk number, ratio scale

Reliability
~~~~~~~~~~~

Depends strongly on employed $a_\mathit{min}$ model, reaction time model, and determination of probabilities

Validity
~~~~~~~~

High, but depends on validity of conditions, empiric analysis shows improvements over TTC, PSD, and CPI [Kuang2015]_

Sensitivity
~~~~~~~~~~~

Depends on how well the employed data set and collision tree represent the ground truth

Specificity
~~~~~~~~~~~

Depends on how well the employed data set and collision tree represent the ground truth

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Depends on metrics used in conditions

Time mode
^^^^^^^^^
Branching time

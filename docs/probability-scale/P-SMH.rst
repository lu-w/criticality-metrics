Collision Probability via Scoring Multiple Hypotheses (P-SMH)
=============================================================

Description
-----------

Similar to other probability-based approaches, Sánchez Morales et al. propose to assign probabilities to predicted trajectories and accumulate them into a collision probability [Morales2019]_.
The motion of the ego is modeled by a two track model.
Due to less information being known with a reasonable accuracy for the other actors, a one track model is used for those.
Pedestrians have the ability of changing direction, velocity, and acceleration in a finite set of steps under given constraints.
Once the number :math:`N` of trajectories for the ego and total number :math:`M` of trajectories of all other actors is determined, one can compute the collision probability as

.. math::
		\mathit{P}\text{-}\mathit{SMH}(A_1, \mathcal{A}, t) = \sum\limits_{i=1}^N\sum\limits_{j=1}^M \chi^i_j p_{\mathit{A_1}, i} p_{{(\mathcal{A} \setminus A_1)}, j}\ ,

where :math:`\chi^i_j` equals one if and only if the :math:`i`-th trajectory of :math:`A_1` and the :math:`j`-th trajectory of the actors in :math:`\mathcal{A} \setminus A_1` lead to a collision, and :math:`p_{\mathit{A_1}, i}` resp. :math:`p_{({\mathcal{A} \setminus A_1}), j}` are the probabilities of the trajectories being realized.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes, demonstrated by evaluation [Morales2019]_

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Any, but requires behavior and dynamic model of subject

Scenario type
~~~~~~~~~~~~~

Depends on definition of models

Inputs
~~~~~~

Static and dynamic objects as well as their state, estimated bounding boxes, ego: see TT model, other vehicles: see OT model

Output scale
~~~~~~~~~~~~

:math:`[0, 1]`, probability, ratio scale

Reliability
~~~~~~~~~~~

High, as the consideration of multiple futures and their likelihoods makes it robustly follow changes in criticality [Morales2019]_

Validity
~~~~~~~~

High, due to branching predictions and likelihood estimation, but depends on the validity of the motion model and probabilities, initial simulative validation results exist [Morales2019]_

Sensitivity
~~~~~~~~~~~

High, but depends on the validity of the motion model and available computational power, no analysis of false negatives was performed in initial evaluation [Morales2019]_

Specificity
~~~~~~~~~~~

High, an initial evaluation found no false positives by the metric [Morales2019]_

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but longer prediction horizons at a constant number of predicted trajectories lower reliability

Time mode
^^^^^^^^^
Branching time

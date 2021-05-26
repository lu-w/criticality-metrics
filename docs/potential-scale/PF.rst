Potential Functions as Superposition of Scoring Functions (PF)
==============================================================

Description
-----------

The general concept of the PF metric is to define a potential function for each static or dynamic object considered by the metric [Wolf2018]_.
This includes potentials for lane markings, the road geometry, other vehicles, or, in more urban areas, pedestrians and bicyclists.
Once a potential function for each object in the scene, denoted by :math:`U_i(A, S)`, is chosen, one can apply e.g. gradient descent for a given scene :math:`S` to the combined potential function :math:`U(A, S) = U_1(A, S) + \dots + U_k(A, S)`, where :math:`A` is an actor and :math:`k` denotes the number of objects.
A simple example of how to evaluate this metric for an actor :math:`A_1` and a given scene :math:`S'` is by inserting the values into :math:`U`, i.e.

.. math::
		\mathit{PF}(A_1, S') = U(A_1, S') = U_1(A_1, S') + \dots + U_k(A_1, S') \,.

However, methods involving the above mentioned gradient descent to assess the criticality will likely improve the precision and also provide a direction in which the vehicle should move to decrease the criticality.

Due to the way this metric is defined, almost all properties depend on the specified potential functions.
While ethical questions play a role when defining any safety surrogate, it becomes more evident for potential functions, as an active decision making in the definition of the potentials is required.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

None found, also highly dependent on the used potential functions

Subject type
~~~~~~~~~~~~

Any, but requires a potential function for each considered subject type

Scenario type
~~~~~~~~~~~~~

Depends on specified potential functions

Inputs
~~~~~~

Potential function for each static/dynamic object in the scene that is supposed to be considered, other inputs depend entirely on said potential functions

Output scale
~~~~~~~~~~~~

:math:`[-\infty, \infty]`, number (negative values are possible if goal locations are defined), ratio scale

Reliability
~~~~~~~~~~~

Largely depends on the used potential functions

Validity
~~~~~~~~

Largely depends on the used potential functions; no empirical analysis identified

Sensitivity
~~~~~~~~~~~

Largely depends on the used potential functions

Specificity
~~~~~~~~~~~

Largely depends on the used potential functions

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Depends on quality of potential functions and reliability of computation of the solution to the potential equation problem

Time mode
^^^^^^^^^
Branching time

Collision Probability via Stochastic Reachable Sets (P-SRS)
===========================================================

Description
-----------

Althoff et al. propose to estimate a collision probability using stochastic reachable sets [Althoff2009]_.
Firstly, the reachable set :math:`R([t,t+t_H])` (the set of possible positions until the horizon :math:`t_H`) is over-approximated for each actor, where the movement of the actor is approximated by Markov chains with time steps :math:`\{t_1, t_2, \dots, t+t_H\}` and a constant :math:`T = t_{k+1} - t_k`.
Due to computational effort, the abstraction from continuous models to Markov chains has to be pre-computed offline for real-time execution of the metric.
The ego's motion is not modeled as it is assumed to be known.

Afterwards, the state and input space are discretized, thus we can write :math:`R^\alpha_i(T)` for the reachable set given a state in the :math:`i`-th partition of the state space and the input in the :math:`\alpha`-th partition of the input space for time :math:`T`.
The transition probabilities to partitions :math:`X_j` of the state space are given by

.. math::
		\Phi_{ji}^\alpha(T) = \frac{V(R^\alpha_i(T) \cap X_j)}{V(R^\alpha_i(T))}

where :math:`V` returns the volume.
Aforementioned concepts are then generalized to :math:`\Phi_{ji}^\alpha([0,T])` by substituting :math:`R^\alpha_i(T)` with

.. math::
		R^\alpha_i([0,T]) = \bigcup\limits_{t \in [0,T]} R^\alpha_i(t)

not accounting for the discrete time aspect at this point [Althoff2009]_.
The transition probabilities can then be used to obtain the probability distribution for the time intervals by

.. math::
		p(t_{k+1}) = \Phi^\alpha(T) \cdot p(t_k)\, p([t_k, t_{k+1}]) = \Phi^\alpha([0,T]) \cdot p(t_k)

again simplified for readability.
Behaviors of other actor are modeled as Markov chains on the control input space of the motion models.
Due to the discretization of the state space, we can approximate the lateral deviation by a piecewise constant function and thus we can define intervals :math:`D_f` where said function is constant.
This leads to a lateral position probability of

.. math::
		p^{dev}_f([t_k, t_{k+1}]) = P(\delta \in D_f, t \in [t_k, t_{k+1}]) .

By splitting the state space partitions :math:`X_i` into position and velocity, i.e. :math:`X_i = S_e \times V_m`, one can define
.. math::
		p^{path}_e([t_k, t_{k+1}]) = \sum\limits_m P(s \in S_e, v \in V_m, t \in [t_k, t_{k+1}]).

Afterwards, all possible paths in which two actors could have intersecting vehicle bodies are identified and stored in a list :math:`\Omega`.
This list is finite due to the piecewise constant partitions.
Under the assumption of stochastic independence and using the previous concepts, we then have :math:`p^{pos}_{ef} = p^{path}_e \cdot p^{dev}_f`, hence leading to the collision probability

.. math::
		\mathit{P}\text{-}\mathit{SRS}(A_1, S, t) = p^{col} = \sum\limits_{(g,h,e,f) \in \Omega} \hat{p}^{pos}_{gh} \cdot p^{pos}_{ef}.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes, with precomputation

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Any, but requires behavior and dynamic model of subject

Scenario type
~~~~~~~~~~~~~

Any scenario, depends on the validity of the models

Inputs
~~~~~~

Static/dynamic objects and their state, estimated bounding boxes, possible control inputs, behavior models, various constants of objects in the scene

Output scale
~~~~~~~~~~~~

:math:`[0, 1]`, probability, ratio scale

Reliability
~~~~~~~~~~~

High, as the consideration of multiple futures and their likelihoods makes it robustly follow changes in criticality

Validity
~~~~~~~~

High, but largely depends on the models, available computational power and discretization coarseness [Althoff2009]_, no representative empirical analysis found

Sensitivity
~~~~~~~~~~~

High, but largely depends on the models and available computational power

Specificity
~~~~~~~~~~~

High, but largely depends on the models and available computational power

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but largely depends on available computational power

Time mode
^^^^^^^^^
Branching time

Safety Potential (SP)
=====================

Description
-----------

The SP is a part of the Safety Force Field (SFF) framework, which proposes a method to compute safe control policies on a collision-avoidance level.
Conceptually, the SFF tries to identify, under the assumption of all actors conducting some safe control policy (e.g. an emergency brake), whether there can exist a conflict [Nister2019]_.
To measure how unsafe w.r.t to collision avoidance a situation is, SFF uses SP as a numeric valuation.

SFF assumes that each actor :math:`A_1 \in \mathcal{A}` has a set of safe control policies, :math:`S_1`.
Each safe control policy :math:`s \in S_1` brings an actor :math:`A_1` to a full stop in finite time.
SFF defines the occupied set :math:`O_1` of an actor :math:`A_1` to include its safety margin as well as :math:`A_1` itself.
For each point on each trajectory that can arise from conducting a safe control policy :math:`s \in S_1`, :math:`O_1` is examined.
The resulting union of trajectories is the claimed set :math:`C_1`.

The unsafe set between two actors  :math:`A_1, A_2 \in \mathcal{A}` can then be identified as :math:`U_{1,2} = \{ x \in C_1 \times C_2 \mid C_1(x) \cap C_2(x) \neq \emptyset \}`.
Intuitively, it is the set of all actor state combinations for which there exist safe control policies leading to a collision.

Identifying the combined state space of :math:`A_1` and :math:`A_2` as :math:`\Omega_1 \times \Omega_2`, SFF subsequently employs a potential function :math:`\rho_{1,2}: \Omega_1 \times \Omega_2 \to \mathbb{R}` to rate the combined states of actors, where

- :math:`\rho_{1,2}(u) > 0` for all :math:`u \in U_{1,2}` and
- :math:`\rho_{1,2}(u) \geq 0` for all :math:`u \not\in U_{1,2}` and
- :math:`\rho_{1,2}(x) \geq \rho_{1,2}(x')` if :math:`x'` is a state derived from :math:`x` by :math:`A_1, A_2` applying :math:`s_1, s_2 \in S_1, S_2`.

The safety potential can hence rate a two-actor scene from one of their perspectives.

The authors state the following exemplary safety potential for some :math:`k \in \mathbb{Z}_{>0} \cup \{\infty\}`:

.. math::
		\mathit{SP}(A_1, A_2, t) = \rho_{1,2} = \| (t_\mathit{stop}(A_1) - t_\mathit{int}, t_\mathit{stop}(A_2) - t_\mathit{int}) \|_k

where :math:`t_{int}` is the the earliest intersection time when continuing the current situation under some model, and :math:`t_\mathit{stop}(A_i)` is the time of full stop of :math:`A_i` after applying a safety procedure.

Note that this framework can be extended with various more complex safety potentials [Nister2019]_.
Downstream, SFF uses the gradient of the safety potential to optimize for a safe control policy, if necessary.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

No

Subject type
~~~~~~~~~~~~

Automated road vehicles

Scenario type
~~~~~~~~~~~~~

Any for whose entities corresponding safety potentials and procedures can be defined

Inputs
~~~~~~

For :math:`k` actors: states (e.g. :math:`p_i`, :math:`d_i`, :math:`v_i`), safety procedures :math:`S_i` and definition of safety potential :math:`\rho_{i,j}` for :math:`i,j \in \{1, \dots, k\}`

Output scale
~~~~~~~~~~~~

:math:`[0, \infty)`, number, ordinal scale

Reliability
~~~~~~~~~~~

High, but additionally depends on the reliability of the safety potentials

Validity
~~~~~~~~

High inside time window, but greatly dependent on validity of potential definition; no empirical analysis available

Sensitivity
~~~~~~~~~~~

Potentially high, but depends on safety procedures and potential definition

Specificity
~~~~~~~~~~~

Potentially high, but depends on safety procedures and potential definition

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Duration of safety procedure

Time mode
^^^^^^^^^
Branching time

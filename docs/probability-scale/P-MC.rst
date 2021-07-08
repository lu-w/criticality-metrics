Collision Probability via Monte Carlo (P-MC)
============================================

Description
-----------

P-MC produces a collision probability estimation based on future evolutions from a Monte Carlo path planning prediction [Broadhurst2005]_.
At first, a binary representation of the road geometry with the distinction of drivable and non-drivable is generated.
If the ego enters a non-drivable region, a collision is detected. Every object in the scene has a state, denoted by :math:`s_i(t) = (p_i(t), v_i(t))`, and control inputs :math:`u_i(t)`.
The motion of each object is then described by an ODE of the form :math:`\dot s_i(t) = f(s_i(t), u_i(t))`.
For example stationary obstacles are modeled by :math:`f \equiv 0` and vehicles are modeled by the simple car state update equation

.. math::
	\begin{pmatrix}
		\dot s^{(1)} \\
		\dot s^{(2)} \\
		\dot s^{(3)} \\
		\dot s^{(4)}
	\end{pmatrix}
	=
	\begin{pmatrix}
		s^{(3)} \cos(s^{(4)}) \\
		s^{(3)} \sin(s^{(4)}) \\
		u^{(1)} \\
		\frac{s^{(3)}}{L} \sin(u^{(3)})
	\end{pmatrix}.

If the bounding boxes of two objects intersect at some point between :math:`t` and :math:`t+t_H`, a collision is detected.
A goal function :math:`g(u_i(t))` is defined for each object in the scene to specify the desirability of paths that the object might follow based on the possible control inputs.
Various choices for this goal function can be made, influencing the prior distribution :math:`P`.
With :math:`k` objects in a scene, the combined goal of all objects is defined as

.. math::
		P(\mathcal{U}) := P(u_1, \dots, u_k) := \prod\limits_{j=1}^k P(u_j)^{\alpha_j}

For an actor :math:`A_1` in a scene :math:`S`, the collision probability is then

.. math::
		\mathit{P}\text{-}\mathit{MC}(A_1, S, t) = P(\mathcal{C}) = \int P(\mathcal{C}~|~\mathcal{U}) P(\mathcal{U}) d\mathcal{U}\ ,

with :math:`P(\mathcal{C}~|~\mathcal{U})` being the collision probability of :math:`A_1` in :math:`S` under the given inputs :math:`\mathcal{U}`.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Any, but requires behavior and dynamic model of subject

Scenario type
~~~~~~~~~~~~~

Depends on the validity of the models

Inputs
~~~~~~

Static/dynamic objects and their state, estimated bounding boxes, possible control inputs, behavior model for each object

Output scale
~~~~~~~~~~~~

:math:`[0, 1]`, probability, ratio scale

Reliability
~~~~~~~~~~~

High, but this largely depends on the models used and thus also on available computational power

Validity
~~~~~~~~

High, but this largely depends on the models used and thus also on available computational power; no empirical analysis available

Sensitivity
~~~~~~~~~~~

High, but this largely depends on the models used and thus also on available computational power

Specificity
~~~~~~~~~~~

High, but this largely depends on the models used and thus also on available computational power

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Depends on the computational power, used behavior and MM and complexity of the situation

Time mode
^^^^^^^^^
Branching time

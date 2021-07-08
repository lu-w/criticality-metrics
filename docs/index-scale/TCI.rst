Trajectory Criticality Index (TCI)
==================================

Description
-----------

The \ac{TCI} metric models criticality using an optimization problem [Junietz2018]_.
The task is to find a minimum difficulty value, i.e. how demanding even the easiest option for the vehicle will be under a set of physical and regulatory constraints. 
For example, if the constraint is to avoid obstacles, then driving straight towards an obstacle and being only a few seconds away requires a large change in steering angle and acceleration to satisfy the constraint of collision avoidance.

Here, the possible set of vehicle actions are not only constrained by physically possible behavior; it additionally shall adhere to a mathematically modeled set of requirements.
Said requirements are based on the necessary longitudinal (:math:`a_x`) and lateral acceleration (:math:`a_y`) to avoid collisions as well as the margin ('reserve') for corrections in speed (:math:`R_x`) and course angle (:math:`R_y`).
Since both :math:`R_x` and :math:`R_y` are dependent on :math:`a_x` and :math:`a_y`, it suffices to minimize the combined function w.r.t. :math:`a_x` and :math:`a_y`.
The requirements include concepts such as holding a safe following distance and maximizing distance to obstacles.

Assuming the vehicle behaves according to Kamm's circle, \acs{TCI} for a scene $S$ with an ego vehicle $A_1$ reads as
.. math::
		\mathit{TCI}(A_1,S,t,t_H) = \min_{a_x, a_y} \sum_{\tilde{t}=t}^{t+t_H} w_x R_x(\tilde{t}) + w_y R_y^2(\tilde{t}) + \frac{w_{\mathit{ax}} a_x^2(\tilde{t}) + w_{\mathit{ay}} a_y^2(\tilde{t})}{(\mu_\mathit{max}g)^2}

where :math:`t_H` is the prediction horizon, :math:`a_x` and :math:`a_y` the longitudinal and lateral accelerations, :math:`\mu_\mathit{max}` the maximum coefficient of friction, :math:`g` the gravitational constant, :math:`w` weights, and :math:`R_x` and :math:`R_y` the longitudinal and lateral margin for angle corrections:

.. math::
		R_x(t) = \frac{\max(0, x(t) - r_x(t))}{d_x(t)},\\
		R_y^2(t) = \frac{(y(t) - r_y(t))^2v(t-t_s)}{d_y^2(t)v_\mathit{max}}.

Here, :math:`x(t)`, :math:`y(t)` is the position, :math:`t_s` the discrete time step size, :math:`v_\mathit{max}` the maximum velocity, :math:`r_x(t)` the reference for a following distance (set to :math:`2\text{s} \cdot v(t)`), :math:`r_y` the position with the maximum lateral distance to all obstacles in :math:`S`, :math:`d_x(t)`, :math:`d_y(t)` the maximum longitudinal and lateral deviations from :math:`r_x`, :math:`r_y`.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes, but not designed for active trajectory control

Target values
~~~~~~~~~~~~~

None found

Subject type
~~~~~~~~~~~~

Road vehicles (esp. automated)

Scenario type
~~~~~~~~~~~~~

Mostly highways

Inputs
~~~~~~

Velocities :math:`v_i`, positions :math:`p_i`, following distance :math:`r_x`, position maximizing lateral distances :math:`r_y`, :math:`\mu_\mathit{max}` maximum coefficient of friction

Output scale
~~~~~~~~~~~~

:math:`[0, \infty]`, number, ratio scale

Reliability
~~~~~~~~~~~

High, under the assumption of a reliable encoding of safety-critical factors in constraints

Validity
~~~~~~~~

High, as demonstrated by an expert-based assessment of the metric's results in four scenarios, but also found to be dependent on the cost function and constraints [Junietz2018]_

Sensitivity
~~~~~~~~~~~

High, no false negative identified in initial expert-based validation [Junietz2018]_, but also depends on cost function and constraints

Specificity
~~~~~~~~~~~

High, no false positive identified in initial expert-based validation [Junietz2018]_, but also depends on cost function and constraints

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but depends on computational power and choice of cost function and constraints

Time mode
^^^^^^^^^
Branching time

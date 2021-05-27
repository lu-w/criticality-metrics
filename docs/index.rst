.. title:: Criticality Metrics

==========================================
Criticality Metrics for Automated Vehicles
==========================================

Introduction
~~~~~~~~~~~~

This page is supplementary material to the publication [Westhofen2021]_ and provides descriptions and evaluations of criticality metrics for automated vehicles.

The descriptions and assessments arose from a systematic suitability analysis, which is described in detail in the reference.
It considers multiple properties that were deemed relevant for a broad albeit abstract set of applications the authors have observed criticality metrics being used in.
Among others, we consider the metrics' target values, scenario types, specificities, and sensitivities.
Definitions of the properties are given in the reference.

.. note::
  Please note that when applying one or multiple of the described metrics in a practical, concrete setting, a detailed analysis of the specific use case at hand is mandatory.

Abbreviations
~~~~~~~~~~~~~

For describing the criticality metrics, we use several abbreviations:

============  ==============================
Abbreviation  Meaning
============  ==============================
AV            Automated Vehicle
VRU           Vulnerable Road User
ODD			  Operational Design Domain
ACC           Adaptive Cruise Control
AEB           Automated Emergency Braking
LKAS          Lane Keeping Assistance System
DMM           Dynamic Motion Model
MM            Maneuver Model
CA            Conflict Area
TT            Two Track
OT            One Track
============  ==============================

Symbols
~~~~~~~

Within formulae, we use the following symbols:

====================================  ================================================================================
Symbol                                Meaning
====================================  ================================================================================
:math:`A_i`                           actor :math:`i`
:math:`\mathcal{A}`                   set of all actors in a scene or scenario
:math:`t_0`                           starting time of a scenario
:math:`t_e`                           ending time of a scenario
:math:`t`                             a point in time
:math:`t_H`                           a time horizon
:math:`p_O(t)`                        position of object :math:`O` at time :math:`t`
:math:`p_i(t)`                        position of actor :math:`i` at time :math:`t`
:math:`p_{i,m}(t)`                    position of actor :math:`i` at time :math:`t` when conducting maneuver :math:`m`
:math:`d(p_1(t),p_2(t))`              euclidean distance of :math:`p_1(t)` and :math:`p_2(t)`
:math:`\dot{d}(p_1(t),p_2(t))`        derivative of euclidean distance :math:`d`
:math:`v_i(t)`                        velocity of actor :math:`i` at time :math:`t`
:math:`a_i(t)`                        acceleration of actor :math:`i` at time :math:`t`
:math:`a_{i,\mathit{long,min}}(t)`    maximum available longitudinal deceleration of actor :math:`i` at time :math:`t`
:math:`a_{i,\mathit{lat,min}}(t)`     maximum available lateral deceleration of actor :math:`i` at time :math:`t`
:math:`a_{i,\mathit{min}}(t)`         maximum available deceleration of actor :math:`i` at time :math:`t`
:math:`j_i(t)`                        jerk of actor :math:`i` at time :math:`t`
:math:`u_i(t)`                        control inputs of actor :math:`i` at time :math:`t`
:math:`\beta_i(t)`                    sideslip angle of actor :math:`i` at time :math:`t`
:math:`\psi_i(t)`                     yaw angle of actor :math:`i` at time :math:`t`
:math:`\omega_i(t)`                   yaw rate of actor :math:`i` at time :math:`t`
:math:`F_{idxy}`                      tire forces of actor :math:`i` with direction :math:`d` for tire :math:`(x,y)`
:math:`c_{i\alpha f}`                 front tire cornering stiffness of actor :math:`i`
:math:`c_{i\alpha r}`                 rear tire cornering stiffness of actor :math:`i`
:math:`l_{if}`                        distance from front axle to center of gravity of actor :math:`i`
:math:`l_{ir}`                        distance from rear axle to center of gravity of actor :math:`i`
:math:`L`                             distance from front to rear axle
:math:`m_i`                           mass of actor :math:`i`
:math:`I_{iz}`                        moment of inertia of actor :math:`i`
:math:`\delta_{if}`                   front steering angle at the tires of actor :math:`i`
:math:`\tau`                          target value
:math:`\text{agg}`                    an aggregate function
:math:`\|\cdot\|_2`                   the euclidean norm
====================================  ================================================================================

Metrics
~~~~~~~

Each criticality metric is described textually, accompanied by a formula.
Furthermore, its properties are described concisely.

.. toctree::
  :hidden:
  :glob:
  :caption: Time-Scale Criticality Metrics

  /time-scale/*

.. toctree::
  :hidden:
  :glob:
  :caption: Distance-Scale Criticality Metrics

  /distance-scale/*

.. toctree::
  :hidden:
  :glob:
  :caption: Velocity-Scale Criticality Metrics

  /velocity-scale/*

.. toctree::
  :hidden:
  :glob:
  :caption: Acceleration-Scale Criticality Metrics

  /acceleration-scale/*

.. toctree::
  :hidden:
  :glob:
  :caption: Jerk-Scale Criticality Metrics

  /jerk-scale/*

.. toctree::
  :hidden:
  :glob:
  :caption: Index-Scale Criticality Metrics

  /index-scale/*

.. toctree::
  :hidden:
  :glob:
  :caption: Probability-Scale Criticality Metrics

  /probability-scale/*

.. toctree::
  :hidden:
  :glob:
  :caption: Potential-Scale Criticality Metrics

  /potential-scale/*

.. toctree::
  :hidden:
  :caption: References

  /references.rst

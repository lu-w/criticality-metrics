Headway (HW)
============

Description
-----------

Please refer to the :doc:`THW</time-scale/THW>`.

Properties
----------

Run-time capability
~~~~~~~~~~~~~~~~~~~

Yes

Target values
~~~~~~~~~~~~~

50 m [Junietz2018a]_ (threshold for fines)

Subject type
~~~~~~~~~~~~

Road vehicles (automated and human)

Scenario type
~~~~~~~~~~~~~

Car following scenarios

Inputs
~~~~~~

Positions :math:`p_i` for :math:`i \in \{1, 2\}`, information to determine lead vehicles

Output scale
~~~~~~~~~~~~

:math:`[0,\infty)`, meter (m), ratio scale

Reliability
~~~~~~~~~~~

Low, as many changes in criticality (e.g. significantly higher speed in a situation) are not reflected by HW

Validity
~~~~~~~~

Medium, a small distance to front does not always imply high criticality, but is also a factor present in many accidents

Sensitivity
~~~~~~~~~~~

High, as indicated by the use of HW in legislation [Junietz2018a]_, most critical situations do imply small distance to front for at least one involved actors

Specificity
~~~~~~~~~~~

Low, as a large distance to front does not always imply low criticality

Prediction model
~~~~~~~~~~~~~~~~

Time window
^^^^^^^^^^^
Unbound, but usefulness depends on DMM

Time mode
^^^^^^^^^
Linear time

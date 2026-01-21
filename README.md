# Rigid-Body Dynamics + IK + Torque & Impedance Control (2-DoF Arm)

This project demonstrates joint-level robot modeling and control for a planar 2-DoF manipulator.

## Features
- Forward kinematics (end-effector position)
- Jacobian computation
- Inverse kinematics (damped least squares)
- Rigid-body dynamics in joint space:
  - Mass matrix M(q)
  - Coriolis/centrifugal vector C(q,qdot)qdot
  - Gravity vector g(q)
- Inverse dynamics / computed torque control for trajectory tracking
- Joint impedance control (spring-damper behavior) with disturbance rejection

## Model
Robot dynamics:
M(q) qdd + C(q,qdot) + g(q) = tau

Computed torque control:
\tau = M(q)(qdd_d + Kd(qd_dot-qdot) + Kp(qd-q)) + C + g

Impedance control:
\tau = K(qd-q) - D qdot + g


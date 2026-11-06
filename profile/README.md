# Emrys Applied Mathematics™

We turn the open literature into software anyone can use. Each algorithm we ship comes
from a published source and cites it. Where no published method fills a need, we record the
problem and leave the solution to research rather than inventing one.

Each library is designed to cover as much of its field as one design can hold, without giving up
efficiency or ease of use. That means one set of types the whole field can be written in, instead
of a separate class for each well-known special case.

We write in **C++**, because it is both efficient and expressive: the same code runs on a
microcontroller and on a workstation, and templates can express a field's structure without
costing anything at run time. Our libraries are built on **Eigen**, the standard for linear
algebra in C++, and follow its conventions, so they fit into code that already uses it. We aim to stay current, so our libraries are written to recent
language standards (C++23 today) and are built for agentic development, with short examples,
checks that say pass or fail, and instructions an agent can follow from a fresh clone. We develop with coding agents ourselves, and
every change gets a thorough human review, backed by decades of experience in applied mathematics
and software engineering.

## EmrysFilter, coming very soon

A header-only C++23 library for state estimation on Eigen 5: one design that runs from the Kalman
filter to the Rao-Blackwellized particle filter. Its first release will include:

- **Filters:** the Kalman filter in covariance, square-root, information, and square-root
  information form; Gaussian mixture, interacting multiple model, and autonomous multiple model
  filters; particle, point-mass grid, and Rao-Blackwellized filters; a hidden Markov filter; and
  fixed-interval and fixed-lag smoothers over all of them.
- **Nonlinear measurements:** linearization with automatic differentiation or a supplied
  Jacobian, the unscented transform and other sigma-point sets, Gauss-Hermite quadrature, and
  iterated updates. Each is chosen per measurement, so the rest of the filter stays the same.
- **States on manifolds:** a state is made of named blocks, each a vector, an angle, a unit
  quaternion, a resizable block, or a discrete mode, and residuals, means, and covariances are
  taken in the right space.
- **Efficiency:** no allocation on bounded states, which the tests check; `float`, autodiff, and
  multiprecision scalars; no exceptions or RTTI required; builds for Cortex-M4F and M7; and
  execution policies that run particles, mixture components, and grid cells on threads.
- **Checks:** simulation, NIS and NEES consistency monitors, and the posterior Cramér-Rao bound.
- **Documentation:** a citation for each algorithm, documentation for every entity, design
  reviews for each area, and skills for a coding agent working in your project.

## Planned projects

Each builds on EmrysFilter's spaces and models. They are listed in the order they depend on one
another.

- **EmrysTracker:** multi-target tracking. Data association and track management (JPDA, MHT, and
  the random finite set filters PHD, CPHD, multi-Bernoulli, and PMBM), variable-structure IMM, and
  the radar, bearings-only, and TDOA measurement models and turn and Singer motion models that
  tracking uses.
- **EmrysAnalysis:** tuning and diagnosing filters over recorded runs. Noise identification by
  expectation-maximization, innovation correlation, and covariance matching; Jacobian checks;
  and fault detection.
- **EmrysController:** optimal control. LQR and LQG, iLQR and DDP, belief-space control and
  sensor scheduling, and H-infinity filtering.
- **EmrysOptimizer:** nonlinear least squares on manifolds (Gauss-Newton, Levenberg-Marquardt,
  dogleg), moving horizon estimation, and estimation under nonlinear constraints.
- **EmrysGraph:** factor graphs and Bayes nets on sparse matrices, with incremental smoothing and
  SLAM back ends.
- **EmrysSampler:** Markov chain Monte Carlo, Hamiltonian Monte Carlo on manifolds, SMC samplers,
  quasi-random sequences, and particle MCMC.
- **EmrysNavigation:** navigation for vehicles and robots. Inertial mechanization, IMU
  preintegration, wheel and legged odometry, GNSS, magnetometer, and camera aiding, and the
  gravity models, geodetic frames, and time scales they need.
- **EmrysOrbit:** orbit determination. Two-body motion with zonal gravity, drag, and solar
  radiation pressure; inertial and Earth-fixed frames; and range, range-rate, angle, and GNSS
  measurements.
- **EmrysBattery:** state of charge and state of health from equivalent-circuit battery models,
  with their parameters estimated alongside, for embedded systems.

---

Emrys™, Emrys Applied Mathematics™, and the names of the projects above are trademarks of Jay
Moore. The open-source licenses of our projects cover their code, not these names.

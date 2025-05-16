# Eagle MPC library
This library contains tools to solve *optimal control problems* (OCPs) that deal with *unmanned aerial manipulators* (UAMs).
It is strongly dependant on [Crocoddyl](https://github.com/loco-3d/crocoddyl), whose API is used to build the OCPs.

It has two principal pieces:
- **Trajectory generator**: It can be used to generate different maneuvers using any type of UAM. The OCP is easily specified by means of a YAML file (see the [example section](#examples))

- **Nonlinear model predictive controllers**: It contains several nMPC controllers. They differ on the way the OCP inside the controller is built and how it is updated at every nMPC step.

It also contains an implementation of the **Squash-box FDDP** solver presented in [this paper](http://www.iri.upc.edu/files/scidoc/2352-Squash-box-feasibility-driven-differential-dynamic-programming.pdf).

This is a C++ library. However, it can also be used within a Python environment since almost all classes have their corresponding **Python bindings**.
## 1 Installation

See [here for installation instructions](https://github.com/hidro-iri/eagle_mpc_lib#2-installation---dependencies)

## 2 Build

See [here for building instructions](https://github.com/hidro-iri/eagle_mpc_lib#3-installation---eagle-mpc)

---

| [Top of page](#eagle-mpc-library) | [Back to Software](../README.md) | [Back to Borinot HOME](../../README.md) |
| --- | --- | --- |
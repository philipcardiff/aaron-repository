# Channel flow over a cavity with a flexible bottom

## Overview
This case is described in Tuković, Ž., Karač, A., Cardiff, P., Jasak, H., &
 Ivanković, A. (2018). OpenFOAM finite volume solver for fluid-solid interaction.
 Transactions of FAMENA, 42(3), 1-31. https://doi.org/10.21278/TOF.42301.

## Notes
Although the steady-state solution is of interest,
The case is setup to solve transiently in time until steady-state is reached.
 Accordingly, 1st order `Euler` time discretisation schemes are chiosen for the
 fluid (`system/fluid/fvSchemes`) and the solid (`system/fluid/fvSchemes`) as
 they contain significant numerical damping, aiding convergence to steady state.
 In addition, damping is added to the solid (`dampingCoeff` in
 `constant/solid/solidProperties`) to aim convergence to the steady state.

Convergence of the fluid-solid interaction residuals can be monitored via the
 `residuals/fsiResiduals.dat` file.

## Results
The vertical displacement of point A (`(4 -1 0)`) are recorded in `postProcessing/0/solidPointDisplacement_displacement.dat`
 via the function object defined in `system/controlDict`. These predictions can
 be compared with the predictions from Tukovic et al.

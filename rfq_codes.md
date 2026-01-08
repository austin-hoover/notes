# RFQ codes


## PARMTEQ

* External fields are computed analytically using harmonic expansions (Bessel functions).
* Space charge (SCHEFF)
    * 2D r-z grid, assuming cylindrical symmetry.
    * Cannot incorporate image effects.
* Integration
    * Leap-frog integration with paraxial approximation. 
    * s-based (rather than t-based); ds = (1/10) * cell length.
* Image forces are solved by assuming point charge or line charge. They are weak (~3% of space charge force.)
* Losses
    * A particle is lost if it exits a square whose width is twice the cell gap.
    * The particle phase is wrapped in [0, 2pi].
* Shortcomings
    * Field approximation is ~valid inside a cylinder. See Fig. 5.2 in Dupperier's thesis.
    * Octupole focusing terms cause lozenge (diamond) shape in the x-y particle distribution. This violates the assumed cylindrical symmetry.
* The above two points imply that halo dynamics are not modeled accurately.
* The square method for transverse loss management can be unsatisfactory.
* Phase wrapping can yield small errors.
* Significant RMS deviations between PARTMEQ and Toutatis.


## Toutatis

* External fields computed numerically.
* Integration
    * t-based (rather than s-based).
    * Symplectic.
    * No paraxial approximation.
* Space charge
    * 3D x-y-z grid.
    * Handles non-symmetric boundary conditions --- exact pole shapes.
    * Relaxation method.
    * Mesh refinement.
* Losses
    * A particle is lost if it exits a square whose width is twice the cell gap.
    * If it is inside the square, it can still be lost if it hits the vane geometry.
    * Particles outside phase [0, 2pi] are frozen for one period before re-entering the bunch.
* Effects in order of importance: (i) transverse loss criterion, (ii) paraxial approximation, (iii) space charge and image effects. This is because focusing forces predominate.


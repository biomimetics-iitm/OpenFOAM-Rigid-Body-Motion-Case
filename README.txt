1. This is a templet for rigid flapping motion of a NACA0012 airfoil.
2. The mesh information is in polyMesh folder.
   The mesh motion is implemented by myRBF function compatible with foam-extend-3.0/3.1.
3. The flapping kinematics can be prescribed in "controlDict" under "RBFMotion" functionObject.
5. myRBF should be compiled each time by "compileLibrary myRBFMotionFunction".
6. Parallel run is governed by "decomposeParDict".
7. To run in parallel: mpirun -np 16 icoDyMFoam -parallel > log 
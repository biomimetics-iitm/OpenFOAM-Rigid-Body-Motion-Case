# OpenFOAM-Rigid-Body-Motion-Case

## This is a templet for rigid flapping motion of a NACA0012 airfoil.

* The mesh information is in polyMesh folder. The mesh was created using GAMBIT.

* The mesh motion is implemented by myRBF function compatible with foam-extend-4.0. 
   
   --> Make sure the "foamTime.H" header file is included in myRBFMotionFunctionObject.c instead of "Time.H". 
   
   --> Make sure: myRBFMotionFunction/Make/options -  
   "-I$(LIB_SRC)/triSurface/lnInclude" (in "EXE_INC = \")  and "-ltriSurface" (in "LIB_LIBS = \") are removed.
* The flapping kinematics can be prescribed in "controlDict" under "RBFMotion" functionObject.
* myRBF should be compiled each time by "compileLibrary myRBFMotionFunction".
* Parallel run is governed by "decomposeParDict". 
* To run in parallel: mpirun -np 16 icoDyMFoam -parallel > log 
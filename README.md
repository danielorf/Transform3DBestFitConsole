Console implementation of Transform3DBestFit class.  Intended to be an example for usage of Transform3DBestFit.

Transform3D class used to calculate best fit 3D transform between two sets of cartesian (X,Y,Z) points.
Once calculated, the following properties are available: 4x4 Transform matrix, 6DoF vector, 
Siemens NC style 6DoF vector, 4x4 Rotation matrix, 4x4 Translation matrix, fit error RMS and Rotation matrix determinant.  
This project relies on the Math.Net Numerics library.


    Usage:          The Transform3D class takes in two sets of 3D points and calculates the best-fit transform and fit error RMS.  
                    Transform3D works with any number of points so long as the number and order of points in both sets match.
                    Incoming point sets can be C# arrays or Math.Net matrices and must be formatted such that each row represents 
                    a point with column0 as "X", column1 as "Y" and column2 as "Z".
                
    Terminology:    "actuals" refers to the first 2D array/matrix of points and "nominals" refers to the second 2D array/matrix 
                    of points points.  The calculated transform is the best fit for actuals->nominals transform.
 
    References:     Details of SVD and rigid transform calculation can be found here:
                        http://graphics.stanford.edu/~smr/ICP/comparison/eggert_comparison_mva97.pdf
                        http://igl.ethz.ch/projects/ARAP/svd_rot.pdf
                        http://en.wikipedia.org/wiki/Wahba%27s_problem
                        http://en.wikipedia.org/wiki/Kabsch_algorithm
                        http://nghiaho.com/?page_id=671
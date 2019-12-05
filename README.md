# ImageStabilizer
A wrapper around the ImageJ plugin "ImageStabilizer" that enables the jar to be run from command line with conventional flags


# The original ImageStabilizer is provided here
https://imagej.net/Image_Stabilizer
https://www.cs.cmu.edu/~kangli/code/Image_Stabilizer.html

# Purpose
The original ImageJ plugin above requires images to be open in FIJI/ImageJ and writes them to new windows, or if it's a virtual stack, to disk.
It's not possible to execute it directly from command line without writing ImageJ macros and executing those in a headless mode ImageJ instance.
Instead, I wrote this simple jar that slightly modifies the original source code to accept files/paths instead of IJ window's ImageProcessor.
The "log-applier" functionality is included as well.

# Usage
from command line, type 
```
java -jar <path to ImageStabilizer.jar> <flags>
```

Allowed flags are:
```
 -applier,--logApplier <arg>   Flag to signify that a log file will be
                               applied
 -i,--input <arg>              input file path
 -iter,--maxIterations <arg>   Maximum num iterations (default 200)
 -log,--logEnabled             Flag to turn on coordinate logging
 -o,--output <arg>             output file path
 -p,--maxPyramids <arg>        Maximum Pyramid Levels: 0, 1, 2, 3, 4
 -s,--substring <arg>          substring with which to filter the input
                               files
 -t,--transformation <arg>     transformation type: Translation or Affine
 -tol,--maxTolerance <arg>     Error Tolerance (default 1e-7
 -update,--updateCoeff <arg>   Template Update Coefficient (default 0.9):
                               0 - 1
 -z,--zSlice <arg>             Flag to turn on coordinate logging
```

REQUIRED flags are:
```
 -i,--input <arg>              input file path
 -o,--output <arg>             output file path
 -t,--transformation <arg>     transformation type: Translation or Affine
```

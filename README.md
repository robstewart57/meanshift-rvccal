# Mean shift visual tracking in RVC-CAL

Mean shift is a feature-space analysis technique for locating the
maxima of a density function. This repository includes an
implementation of using mean shift for visual tracking in the RVC-CAL
dataflow language. The figure below shows a human being tracked using
a red tracking window.

![Mean shift tracking](http://www.macs.hw.ac.uk/~rs46/files/meanshift-tracking.png)

## Installation, compilation and running

1. Install [eclipse](https://www.eclipse.org) and the [Orcc
   plugin](http://orcc.sourceforge.net).

2. Import this eclipse project and compile the `TopMeanShift.xdf`
   network using the Orcc C backend.

3. Download the S2.L1 sequence PETS'09 data set [video](https://www.
dropbox.com/sh/cy50jgbtv26cc1w/AAA1g_Pt0pVV5smWOnBmJAmFa/PETS_176x144.yuv),
   copyright of the University of Reading.

4. Go to the C output directory and compile.

```
$ cd build
$ cmake ..
$ make
```

5. Run the mean shift executable.

```
cd ../bin/
$ ./TopMeanShift -i path/to/PETS_176x144.yuv -w PETS_Tracking_output.yuv -l 1
```

The `PETS_Tracking_output.yuv` shows a red window tracking a walking pedestrian on every frame.

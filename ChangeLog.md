# UPDATE 29-01-2012 #

SKT 2.1 available

  1. New method for point calibration using zones (much better)
  1. RANSAC fit for plane method (preparation for a future method)
  1. Now you can use the negative values only for distance (useful for clear rear projective film, i.e. back projection and kinetic placement)
  1. New plane moving function (always parallel), useful for the same as before and other instances.
  1. Deprecated the disparity functions, now the RGB and DEPTH images can be calibrated automatically using OpenCV's new option (checkbox in SKT).
  1. New mouse as "touch" function. Simple "touch is pressed" method just for blob 0.
  1. Other fixes....

# UPDATE 06-10-2011 #

SKT 2.0 "beta" available for linux.

  1. Source rewritten for a little more simplicity (and future portability to win and mac).
  1. More "kinect movement" stable
  1. New plane fitting method (using minimum squares)
  1. New threshold method (very basic options, IMPORTANT : must select zone first!)
  1. Now the settings are all initialized from "settings.xml" file. Now you can change the number of calibration points, max number of blobs, tuio host and port, etc...
  1. Better point calibration (easier to use)
  1. A simple automatic min-max distance search.
  1. Very simple mouse pointer implementation (moves the mouse following the blob with ID=0 and clicks when ID=1 appears together with ID=0). For better results be sure to have a good calibration before you activate the "mouse" checkbox.

Soon we will have a win and mac SKT-2.0 version.


# UPDATE 21-07-2011 #

SKT 1.4 Available.

- New point calibration
- Other fixes (includes fix for TUIO port different from default)
# UPDATE 14-07-2011 #

SKT 1.3 For windows and linux available.

- New option for touch point extraction. Works much better for screens (LCDs, LED, etc...)

# UPDATE 26-06-2011 #

SKT 1.2 for Windows available. VS solution and executable.

# UPDATE 25-06-2011 #

New version for linux available: SKT - 1.2.

-Linux src and bin included
-Option to save and load parameters!
-Few minor improvements

coming soon: windows and mac versions...

# UPDATE 14-06-2011 #

New version available!! SKT - 1.1.

-VS 10 Solution
-Binaries for Windows 7 (might work with vista)
-Binaries for Linux (with SSE 3 and TBB support).

# UPDATE 08-06-2011 #

Binaries for linux available. Instructions and dependencies: README file included.
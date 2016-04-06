# New features in version 2.0 #

-Threshold: Simple threshold of distance. Points that are in the interval between min Dist and max Dist are considered for blobs

-The plane method is now done with least squares (a lot better)

-The point calibration now has a timing between points. When touching a point keep the touch until the circle becomes green. Then remove the touch and go for the next one. You can modify the number of calibration points in settings.xml. The final number of points will be the number you set squared.

-All the Tuio information now goes in the settings.xml file. If you put an invalid
host or port the application WILL exit.

-New auto setup of min and max dist. When you feel your setup is ready, keep two "touches" on the surface (separated) and click "Auto Min-Max". You will see the values in the trackbars (in the "To Blobs" image) moving. The idea is that the program moves the values until it finds two blobs (closest to the surface possible) and keeps getting the same two blobs for at least 20 frames.

-You can stop the "Auto Min-Max" with "Stop Auto" at any time.

-Mouse: sends mouse move and click events in Windows and Linux. Use it when you have done a good calibration! (if not you will probably not be able to shut the program)

-Module: Calculates the absolute difference in background and plane methods (useful for transparent rear-projection). Normally the difference has sign (and is better for surfaces or screens)

-Other minor fixes have been included and hopefully we wont get too many more :)

ENJOY!!!

# Point calibration and extra mask space in version 1.4 #

-Now you can do point calibration in SKT!! just make sure you have a good calibration for the touch points and click "Point Calibration" (works in plane and back modes).

-Another new feature is the extra mask space. When you select a plane you might be hoping to use every inch of it so we included a "mask expander" slidebar. Move it and see what happens with the "Mask" image. With this option you can now get some features that would otherwise be outside the detected range.

# New Tips for version 1.3 and plane use instead of Background #

-The plane method is used when you want to get touch point from a planar surface that does not give a good infrared reflection for Kinect to determine depth. This is the case of LCDs, LEDs and other kind of screens.

-Select Use plane (not Back)

-Click calibrate zone. Make sure you select points in the border of the surface that do get some depth info and would belong to the plane you intend to use as a touch surface.

-Put your fingers on the surface and change "max distance" until you see them.

-Change min distance until you only see your fingers (or hand)... voila!!

-The plane method does not work with irregular or curved surfaces. It just calculates the 2d plane embeded in 3d that contains the first 3 points you select, then creates an image extrapolating the plane to be used instead of the background image.

# Tips for Using SKT #

- At less than 40-50 cm the Kinect sensor doesn't get distance data (the infrared grid used for detection has its dots to close at this distance to be analized) so always put your Kinect farther than this.

- The first parameter to be regulated is the accepted pixel's variance for qualifying as background. If you put the Kinect completely perpendicular to the surface, you probably will be okay with an accepted variance of 300 (0.03 really for it is divided by 10000) or less. If you put it in another direction try different values (and recalibrate background at each try) until you get a nice mask for the background (nice means that in the "Mask" image a lot of pixels from your intended surface are white). Remember not to oclude the image when doing background calibration.

- Then comes the min distance from the surface. SKT does a simple substraction between the new image and the background, then divides the result by the new image values. The first part is for detecting differences and the second one is for doing a little scale normalization (this makes a non-perpendicular capture of the surface posible). The min distance is a simple threshold for, as its name says, minimum distance values from the new pixels to the background in order to qualify as a usable pixel. Move this a little and look at the "To Blobs" image and you will notice the change. Try not to have too many "strayed sectors" when the surface doesn't have anything on it (this will produce false positives).

- The next ones are max distance and min blob area. The first is self-speaking. The second is the minimum connected component's area for it to be considered as a usable blob. Move this ones a bit and see what happens on the "RGB" image, then check the "To Blobs" to see the reason.

- That should about do it for basic parameters. To calibrate the RGB and Depth images move the alpha parameter (to 50 for example) and place any object a distance away from the background so you can see the depth difference between them. Then change the values of the XX, YY, etc... corresponding to the the affine warp parameters and try to fit the image in colors with the gray depth map of the object. This is trial and error at first, then you will get better at it. Each Kinect should have its own values for calibration.

- Then you should probably calibrate the zone. This is always done after calibrating background (each time you do). It is done clockwise starting from the top-left corner. This is very important so you wont get blobs from another part in the images. The zone sets the 0-1 bounds for both X and Y axis. You can do X or Y flips (0->1 , 1->0) and X-Y flips (even before zone selection).

- When you have a good calibration, you can save the parameters (the zone does not get saved, the rest of important parameters do). This settings will get auto loaded the next time. If you want to reset the parameters to default, delete or rename the "settings.xml" file.

- When everything is done and you want to use the tracking, remember that you will get more FPS if you stop updating the "RGB" and "To Blobs" images (unchecking the boxes) or reducing their size (see the output "FPS calculated" to get the idea).

- Have Fun!!
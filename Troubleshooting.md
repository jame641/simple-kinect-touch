If you had problems executing skt, you should run it in cmd (Win like OS) or terminal (Unix like OS) so you can read the output. In general skt prints a lot of details to the terminal (or cmd) so it is always better to run it there.

# LINUX #

  * ### The opencv libraries distributed have been compiled with 32-bit avin2 and openni (they will probably not work with 64-bit versions of the formers). If you want to use the 64-bit versions you will have to compile opencv yourself (for the moment). ###

# OSX #

### For the following error(s): ###

1) "Semantic Issue.
> No matching constructor for initialization of 'cvflann::LshIndexParams'   "

2) "Semantic Issue.
> Invalid operands to binary expression ('std::ostream' (aka 'basic\_ostream**<char**>') and 'const cdiggins::anyimpl::empty\_any')

The solution, given by "lahoz....@gmail.com" is:

Change the compiler to LLVM GCC 4.2 and link ALL the libraries in the "linker flags".

# Windows #

## General ##
  * ### The opencv libraries distributed have been compiled with 32-bit avin2 and openni (they will probably not work with 64-bit versions of the formers). If you want to use the 64-bit versions you will have to compile opencv yourself (for the moment). ###

## Binaries : ##

  * ### Some users have reported problems when the Microsoft SDK is installed along with avin2 drivers. This if fixed by uninstalling Microsoft SDK and avin2  and reinstalling avin2 drivers. We will make a Microsoft sdk version soon... ###

Typical presentation of the problem :

"OpenCV Error: Unspecified error (Failed to enumerate production trees: Can't
create
any node of the requested type!) in unknown function, file D:\OPENCV2.3\open
cv\modules\highgui\src\cap\_openni.cpp, line 188

Could not find any device. "

Thanks to vNakamura for this.

  * ### It has been reported that there is a possible conflict with having two different versions of openni installed (x86 and x64). If you are having problems try uninstalling both and avin2 drivers and reinstalling the same version of openni and avin2 (just one version of each). ###

  * ### It has also been reported that the x64 versions have some problems. If you have the following error try the 32 bit version of openni and avin2 (with the other versions uninstalled) : ###

"...init done opengl support available Kinect opening ... done.
FPS Given by Device : 0
Could not open the device. "

Thanks to 3dmark for this.

  * ### If you have a "msvcr100d.dll missing" message try copying this file to the folder where your SKT.exe file lies. ###

Thanks to Fike for this.
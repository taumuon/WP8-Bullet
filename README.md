WP8-Bullet
============

Demo of using the Bullet Physics Engine in a Windows Phone 8 DirectX 11 app.

Email queries to gary@taumuon.co.uk or on this post:
http://taumuon-jabuka.blogspot.co.uk/2012/04/bullet-physics-and-directx-11-on.html

Building bullet:

This was tested with Bullet 2.81 revision 2613

The steps to create the bullet libs were
. Download bullet source, and unzip to e.g. C:\Bullet
. Open and convert the solution from under build\vs2010
. Remove projects except: BulletCollision, BulletDynamics, LinearMath
. Add a new Solution Configuration ARM
. For each project, change the Platform Toolset to be Windows Phone 8.0 (v110)
. Change the Linker Target Machine to be MachineARM (/MACHINE:ARM)
. Add the following preprocessor define to all projects:
  BT_NO_PROFILE
  BT_USE_DOUBLE_PRECISION
. Change the use of the C Runtime to be Multi-threaded DLL/Multi-threaded Debug Dll

Change the MetroBullet project's C++ include path to point to the bullet source, e.g. C:\Bullet\src
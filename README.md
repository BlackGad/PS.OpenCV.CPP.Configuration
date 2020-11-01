[![Build status](https://ci.appveyor.com/api/projects/status/j5y41lu33fw29i0y?svg=true)](https://ci.appveyor.com/project/BlackGad/ps-opencv-cpp-configuration)
[![NuGet Badge](https://buildstats.info/nuget/PS.OpenCV.CPP.Configuration)](https://www.nuget.org/packages/NUnit/)
# PS.OpenCV.CPP.Configuration
Easy c++ projects configuration with OpenCV SDK

# How to use
1) Download SDK from https://opencv.org/releases/ 
2) Do **'Set the OpenCV environment variable and add it to the systems path'** step from [**Installation in Windows**](https://docs.opencv.org/master/d3/d52/tutorial_windows_install.html#tutorial_windows_install_path) tutorial.
3) System may require reboot to apply this variable (or may not)
4) Install this package to your c++ project

# What it does
1) Patch your c++ projects with additional **PS.OpenCV.CPP.Configuration.props** which based on **%OPENCV_DIR%** variable adds
    - Additional include directories
    - Additional static library directories
    - Add dependency to **opencv_world450d.lib** or **opencv_world450.lib** based on selected configuration
2) Patch your c++ projects with additional **PS.OpenCV.CPP.Configuration.targets** which copies additional dynamic libraries to target folder on every build.

# Control MSBuild
- Define **OPENCV_DIR** property before **PS.OpenCV.CPP.Configuration.props** import to set custom **OPENCV_DIR** path (default: **%OPENCV_DIR%** environment variable)
- Define **OpenCV_SourceFolder_Override** property to set custom dynamic libraries source directory
- Define **OpenCV_TargetFolder_Override** property to set custom dynamic libraries target directory



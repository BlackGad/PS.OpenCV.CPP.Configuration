# PS.OpenCV.CPP.Configuration
Easy c++ projects configuration with OpenCV SDK

# How to use
1) Download SDK from https://opencv.org/releases/ 
2) After extraction add **opencv2SDK** user environment variable to target folder
3) System may require reboot to apply this variable
4) Install this package to your c++ project

# What it does
1) Patch your c++ projects with additional **PS.OpenCV.CPP.Configuration.props** which based on **%opencv2SDK%** variable adds
    - build\include **AdditionalIncludeDirectories**
    - build\<platform>\<vc_version>\lib\ **AdditionalLibraryDirectories**
    - **opencv_world450d.lib** or **opencv_world450.lib** based on selected configuration to **AdditionalDependencies**
2) Patch your c++ projects with additional **PS.OpenCV.CPP.Configuration.targets** which copies additional dynamic libraries to target folder *.dll 

# Control MSBuild
- Define **OpenCV_SDK** property before **PS.OpenCV.CPP.Configuration.props** import to set custom opencv2 path (default: **%opencv2SDK%** user/system environment variable)
- Define **OpenCV_Platform_Override** property before **PS.OpenCV.CPP.Configuration.props** import to set custom platform (default: **x64**)
- Define **OpenCV_VCVersion_Override** property before **PS.OpenCV.CPP.Configuration.props** import to set custom vcVersion (default: **vc15**)
- Define **OpenCV_SourceFolder_Override** property anywhere to set custom *.Dll source directory (default: **build\$(OpenCV_Platform_Override)\$(OpenCV_VCVersion_Override)\bin\**)
- Define **OpenCV_TargetFolder_Override** property anywhere to set custom *.Dll target directory (default: empty (means target folder))



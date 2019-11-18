# vulkan_base
Vulkan testbed based on the online vulkan tutorial at https://vulkan-tutorial.com/  

## GLFW Build
Build it with cmake.  
cd glfw  
mkdir build  
cmake -G "Visual Studio 15 2017 Win64" ..  
Open with VS 2017, build the lib in Release mode.

## Visual Studio Build Configuration
### C++
General -> Additional Include Directories:  
$(VULKAN_SDK)\Include;..\..\glfw\include;..\..\glm;%(AdditionalIncludeDirectories)  

### Linker
General  -> Additional Library Directories:  (Note: uses VULKAN_SDK env variable)
..\..\glfw\build\src\Release;$(VULKAN_SDK)\Lib;%(AdditionalLibraryDirectories)  
Input  -> Additional Dependencies  
vulkan-1.lib;glfw3.lib;%(AdditionalDependencies)  

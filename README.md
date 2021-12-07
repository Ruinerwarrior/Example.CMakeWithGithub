# Example: CMake with Github

This example shows ways to build, test and release applications and libraries build with cmake using github actions

# How to build locally
- Run `cmake -S . -B ./build` to configure
- Run `cmake --build build` to build

In order to pass in a build configuration use:  
- `cmake -S . -B ./build -DCMAKE_BUILD_TYPE=Release`  
for single config buildsystems like make
- `cmake --build build --config Release`  
for multi config buildsystems like visual studio

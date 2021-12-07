# Example: CMake with Github

This example shows ways to build, test and release applications using cmake with github actions

# How to build locally
- Run `cmake -S . -B ./build` to configure
- Run `cmake --build build` to build

In order to pass in a build configuration use:  
- `cmake -S . -B ./build -DCMAKE_BUILD_TYPE=Release`  
for single config buildsystems like make
- `cmake --build build --config Release`  
for multi config buildsystems like visual studio

# How to use the build pipeline
The .github/workflows/build.yml file contains the build pipeline, 
this pipeline is used to confirm the branch can build on all specified platforms and the unit tests
succeed before merging the branch to main. In order to enforce this use the following settings in Github:  
![alt text](https://github.com/RuinerWarrior/Example.CMakeWithGithub/blob/main/assets/github_branch_settings.png?raw=true)  

If working alone, don't check the "Include administrators" option, as you won't be able to merge pr's yourself.

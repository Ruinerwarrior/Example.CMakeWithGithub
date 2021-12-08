cmake_minimum_required(VERSION 3.21.1)

project(Example.CMakeWithGithub
VERSION 1.0.0
LANGUAGES C
DESCRIPTION "Example of using cmake with github actions" 
HOMEPAGE_URL "https://github.com/Ruinerwarrior/Example.CMakeWithGithub")

# works only for multi-config generators
set ( BUILD_CONFIG $<$<CONFIG:Debug>:Debug>$<$<CONFIG:Release>:Release>$<$<CONFIG:RelWithdepInfo>:RelWithdepInfo>)

# if single config set buildtype variable
if(NOT BUILD_CONFIG)
    if(NOT CMAKE_BUILD_TYPE)
        set (CMAKE_BUILD_TYPE Release)
    endif(NOT CMAKE_BUILD_TYPE)
    set (BUILD_CONFIG ${CMAKE_BUILD_TYPE})
endif(NOT BUILD_CONFIG)

# specify output dir: build/os/compiler/buildconfig
set(OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/${CMAKE_SYSTEM_NAME}/${CMAKE_C_COMPILER_ID}/${BUILD_CONFIG}/)

# .lib/.a
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${OUTPUT_DIRECTORY}/lib)
# .dll/.so
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${OUTPUT_DIRECTORY}/lib)
# .exe/.dll/.pdb
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${OUTPUT_DIRECTORY}/bin)

include(CTest)
enable_testing()

add_subdirectory("application")

include(CPack)

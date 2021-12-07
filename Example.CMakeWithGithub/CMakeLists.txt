cmake_minimum_required(VERSION 3.21.1)

add_executable(Example.CMakeWithGithub "src/main.c")
target_include_directories(Example.CMakeWithGithub PRIVATE "include")
cmake_minimum_required(VERSION 3.21.1)

add_executable(Example "src/main.c")
target_include_directories(Example PRIVATE "include")
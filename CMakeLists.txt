# -------------------------- GENERAL --------------------------------
cmake_minimum_required(VERSION 3.23)
project(LOL)

# --------------------------GLOBAL ----------------------------------
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_EXE_LINKER_FLAGS "-static") # not need to copy dll to executable folder

# -------------------------- PROJECTS --------------------------------
add_subdirectory(Game)

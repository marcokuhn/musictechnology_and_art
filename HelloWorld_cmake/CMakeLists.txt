# GENERAL CMAKE https://cliutils.gitlab.io/modern-cmake/chapters/basics.html
# https://matgomes.com/cmake-add-executable/


# SET MINIMUM CMAKE VERSION
cmake_minimum_required(VERSION 3.7)

if(${CMAKE_VERSION} VERSION_LESS 3.26)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
else()
    cmake_policy(VERSION 3.26)
endif()

#setup Project – MyProgram is in that case the project name
project(MyProgram VERSION 1.0
            DESCRIPTION "MY FIRST PROJECT"
            LANGUAGES CXX)

# create executable MyProgram
add_executable(
    MyProgram
    ./src/main.cpp
    ./src/Log.cpp 
)

# Specify include directories for the target
target_include_directories(MyProgram PRIVATE ${PROJECT_SOURCE_DIR}/include)

# SET compile features using – C++ Version 20
target_compile_features(MyProgram PUBLIC cxx_std_20)
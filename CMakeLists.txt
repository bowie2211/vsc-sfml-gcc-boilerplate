cmake_minimum_required(VERSION 3.5.0)
project(starterkit_sfml VERSION 0.1.0 LANGUAGES C CXX)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src/SFML-2.6.1/include) 
add_executable(starterkit_sfml src/main.cpp)

#Library 
#Set static linkage 
set(SFML_STATIC_LIBRARIES TRUE) #important otherwise you have to install the dlls somewhere
# Set path variable to cmake files for the sfml libs (can be found in SFMLConfig.cmake)
set(SFML_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src/SFML-2.6.1/lib/cmake/SFML)
# Finde find libraries
find_package(SFML COMPONENTS system window graphics  REQUIRED) # find the graphics, window and system modules

target_link_libraries(starterkit_sfml sfml-graphics
                                        sfml-window
                                        sfml-system)
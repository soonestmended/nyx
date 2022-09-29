cmake_minimum_required(VERSION 3.10)

# set the project name
project(nyx)

find_package(Vulkan REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)
link_directories(/usr/local/lib/)
#include_directories(/opt/homebrew/opt/glm/include /opt/homebrew/opt/glfw/include)
# add the executable
add_executable(nyx src/main.cpp)
set_property(TARGET nyx PROPERTY CXX_STANDARD 17)
message(STATUS "Foo")
message(STATUS "${Vulkan_LIBRARIES}")
include_directories(${Vulkan_INCLUDE_DIRS})

target_link_libraries(nyx ${Vulkan_LIBRARIES} shaderc_combined glfw ${GLM_LIBRARY})

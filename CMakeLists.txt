cmake_minimum_required(VERSION 3.10)

# set the project name
project(nyx)

find_package(Vulkan REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)
#link_directories(/opt/homebrew/opt/glm/lib /opt/homebrew/opt/glfw/lib)
#include_directories(/opt/homebrew/opt/glm/include /opt/homebrew/opt/glfw/include)
# add the executable
add_executable(nyx src/main.cpp)
include_directories(${Vulkan_INCLUDE_DIRS})
target_link_libraries(nyx ${Vulkan_LIBRARIES} glfw ${GLM_LIBRARY})

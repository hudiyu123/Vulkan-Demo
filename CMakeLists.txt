cmake_minimum_required(VERSION 3.20)

project(VulkanDemo LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

find_package(Vulkan REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)

set(VulkanDemoLibs
    Vulkan::Vulkan
    glfw
    glm::glm)

add_executable(VulkanDemo VulkanDemo.cpp)
target_link_libraries(VulkanDemo ${VulkanDemoLibs})

configure_file(shaders/vert.spv shaders/vert.spv COPYONLY)
configure_file(shaders/frag.spv shaders/frag.spv COPYONLY)
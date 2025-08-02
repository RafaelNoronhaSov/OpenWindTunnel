cmake_minimum_required(VERSION 3.10)
project(OpenWindTunnel)

file(GLOB_RECURSE SOURCES "src/*.cpp")
file(GLOB_RECURSE HEADERS "include/*.h" "include/*.hpp")

add_executable(owt ${SOURCES} ${HEADERS})

find_package(imgui CONFIG REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)

target_link_libraries(owt PRIVATE imgui::imgui glfw glm::glm)
target_include_directories(owt PRIVATE include)
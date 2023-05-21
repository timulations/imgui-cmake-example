cmake_minimum_required(VERSION 3.16)

project(IMGUI_CMAKE LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(IMGUI_DIR imgui)

# Dependencies
find_package(SDL2 REQUIRED)
find_package(OpenGL REQUIRED)

# Headers
include_directories(
    ${SDL2_INCLUDE_DIR}
    ${IMGUI_DIR}/
    ${IMGUI_DIR}/backends
)

# Sources
set(IMGUI_CMAKE_SOURCES
    ${IMGUI_DIR}/imgui_demo.cpp
    ${IMGUI_DIR}/imgui_draw.cpp
    ${IMGUI_DIR}/imgui_tables.cpp
    ${IMGUI_DIR}/imgui_widgets.cpp
    ${IMGUI_DIR}/imgui.cpp
    ${IMGUI_DIR}/backends/imgui_impl_opengl3.cpp
    ${IMGUI_DIR}/backends/imgui_impl_sdl2.cpp
)

# Example binary
add_executable(imgui_cmake_example_sdl2_opengl3
               ${IMGUI_DIR}/examples/example_sdl2_opengl3/main.cpp
               ${IMGUI_CMAKE_SOURCES}
               )

target_link_libraries(imgui_cmake_example_sdl2_opengl3 
                      PUBLIC
                      ${OPENGL_LIBRARIES}
                      ${SDL2_LIBRARIES})

# imgui-cmake
Lightweight cmake configuration for ImGui for SDL2-OpenGL3

## Getting Started
Install SDL2 on your system and make sure the headers and library paths are in PATH. For example, in Mac:
```
brew install sdl2
```

Clone this repo with submodules, and build:
```
git clone https://github.com/timulations/imgui-cmake-example.git --recurse-submodules
cd imgui-cmake-example
mkdir build && cd build
cmake ..
make -j4
```

Run the example binary from ImGui:
```
./imgui_cmake_example_sdl2_opengl3
```


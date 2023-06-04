# CMake PC file generator

This modules allows for automatic PC file generation for your targets.


## Installation

This repo is meant to be cloned as a submoule inside your project CMake modules folder. Alternatively, you can copy the cmake module directly in your folder.

Remember to add your CMake modules folder to the module search path in your `CMakeLists.txt`. This can be done with the list append command:
```CMake
list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/<your_cmake_modules_folder>/cmake-pcfilegenerator")
```

Also, include the module in your `CMakeLists.txt`:
```CMake
include(PcFileGenerator)
```


## Usage

After you have included the module, the following variables will be available:
* `CMAKE_INSTALL_PKGCONFIGDIR`: The default value will be `${CMAKE_INSTALL_LIBDIR}/pkgconfig`.

The module also exposes the following functions:
* `target_pc_file_generate`: Generate a ".pc" file for the provided target.

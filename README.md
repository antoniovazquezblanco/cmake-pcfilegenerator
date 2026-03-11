# CMake PC file generator

This modules allows for automatic PC file generation for your targets. That is untill CMake supports the feature (https://gitlab.kitware.com/cmake/cmake/-/issues/22621).

## Installation

You may opt for any of the following options fo install and use this CMake module.

### Via FetchContent

You can use CMake's FetchContent module to automatically fetch and include this module:

```CMake
# Include the FetchContent module
include(FetchContent)

# Fetch the module...
FetchContent_Declare(
  pcfilegenerator
  GIT_REPOSITORY https://github.com/antoniovazquezblanco/cmake-pcfilegenerator.git
  GIT_TAG main  # Or specify a version
)
FetchContent_MakeAvailable(pcfilegenerator)
list(APPEND CMAKE_MODULE_PATH "${pcfilegenerator_SOURCE_DIR}")

# Include the module
include(PcFileGenerator)
```

### Via submodule or copy

This repo can be cloned as a submodule inside your project CMake modules folder. Alternatively, you can copy the cmake module directly in your folder.

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

- `CMAKE_INSTALL_PKGCONFIGDIR`: The default value will be `${CMAKE_INSTALL_LIBDIR}/pkgconfig`.

The module also exposes the following functions:

- `target_pc_file_generate`: Generate a ".pc" file for the provided target.

find_package(LLVM REQUIRED CONFIG)
list(APPEND CMAKE_MODULE_PATH "${LLVM_CMAKE_DIR}")
include(AddLLVM)
include_directories(SYSTEM ${LLVM_INCLUDE_DIRS})
add_definitions(${LLVM_DEFINITIONS})


add_llvm_library(detectors MODULE
    utils_arrayshapes.cpp
    utils_basicinfo.cpp
    utils.cpp
    ProtocolFlowGraph.cpp
    All.cpp
    PrintGraphInfo.cpp
    PrintGraphviz.cpp
    PLUGIN_TOOL
    opt
)

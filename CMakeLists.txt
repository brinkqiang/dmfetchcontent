cmake_minimum_required(VERSION 3.8)

PROJECT(dmfetchcontent)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
ModuleSetCompileOptions()
ModuleSetWinCompilerFlags()

include(FetchContent)

FetchContent_Declare(
    dmzipper
    URL https://github.com/brinkqiang/dmzipper/archive/refs/heads/main.zip
)
FetchContent_MakeAvailable(dmzipper)

ExeImport("tools" "dmzipper")

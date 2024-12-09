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


include(FetchContent)

FetchContent_Declare(
  cmodule
  URL https://github.com/scapix-com/cmodule/archive/refs/tags/v2.0.1.zip
)

FetchContent_MakeAvailable(cmodule)

find_package(Boost REQUIRED COMPONENTS filesystem)

ExeImport("tools" "dmzipper;Boost::filesystem")

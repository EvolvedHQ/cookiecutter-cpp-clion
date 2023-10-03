cmake_minimum_required (VERSION 3.12)
project ({{cookiecutter.project_name}})

set (CMAKE_CXX_STANDARD 23)
set (CMAKE_EXPORT_COMPILE_COMMANDS ON)

include(FetchContent)
FetchContent_Declare(
        Catch2
        GIT_REPOSITORY https://github.com/catchorg/Catch2.git
        GIT_TAG        6e79e682b726f524310d55dec8ddac4e9c52fb5f     # v3.4.0
        GIT_SHALLOW    1)
FetchContent_Declare(
        trompeloeil
        GIT_REPOSITORY https://github.com/rollbear/trompeloeil.git
        GIT_TAG        b21cdbad60657a802cf8dcd65970c3cc06f4dc60     # v45
        GIT_SHALLOW    1)
FetchContent_MakeAvailable(Catch2 trompeloeil)

set (production-sources
    src/{{cookiecutter.project_name}}.cpp)
add_library ({{cookiecutter.project_name}} STATIC ${production-sources})
target_include_directories ({{cookiecutter.project_name}} PUBLIC include)

set (test-sources
    test/{{cookiecutter.project_name}}_test.cpp)
add_executable ({{cookiecutter.project_name}}test ${test-sources})
target_link_libraries ({{cookiecutter.project_name}}test PRIVATE 
        {{cookiecutter.project_name}}, Catch2::Catch2WithMain trompeloeil)

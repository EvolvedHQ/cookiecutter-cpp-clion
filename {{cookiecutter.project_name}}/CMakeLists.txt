cmake_minimum_required (VERSION 3.12)
project ({{cookiecutter.project_name}})

# C++20, and export compile commands for secondary tooling to work well
#
set (CMAKE_CXX_STANDARD 20)
set (CMAKE_EXPORT_COMPILE_COMMANDS ON)

# This template is designed to work with the holy trinity of CLion, clang,
# and libc++. These flags below are specific to those tools, and to the intent
# of this cookiecutter template (debug, unit test, coverage etc). We'd
# typically have these externalised into toolchain files, but not in this
# very specific case.
#
set (CMAKE_CXX_FLAGS "-stdlib=libc++ -Wall")
set (CMAKE_CXX_FLAGS_DEBUG "-fstandalone-debug -fprofile-instr-generate -fcoverage-mapping -ggdb -O0")

# For the sake of form, and to give an idea of the sort of setup you'd
# find in a "real world" project, we're keeping the sources separate,
# and creating a separate archive
#
set (production-sources
    src/{{cookiecutter.project_name}}.cpp)
add_library ({{cookiecutter.project_name}} STATIC ${production-sources})
target_include_directories ({{cookiecutter.project_name}} PRIVATE include)

# The unit tests executable, statically linking the "production" code
#
set (test-sources
    test/test_runner.cpp
    test/{{cookiecutter.project_name}}_test.cpp)
add_executable ({{cookiecutter.project_name}}test ${test-sources})
target_link_libraries ({{cookiecutter.project_name}}test {{cookiecutter.project_name}})

target_include_directories ({{cookiecutter.project_name}}test PRIVATE
    lib/catch-2.13.0
    include)

# Template for TDD in modern C++

This is a cookiecutter template for a simple C++ project supporting
TDD, and optimised for the CLion IDE. This template uses
[Catch2](https://github.com/catchorg/Catch2/blob/master/docs/tutorial.md)
as the unit test framework of choice, and is intended to give you a
very efficient and highly repeatable way of very quickly getting
started with micro-experimentation in C++.

## Features of this template

The template is designed for use with CLion, far less so as a
standalone CMake-based project:

- Includes Catch2 as the unit test framework
- Generates a header, a "production" source file and an empty test
- Generates a CMake build designed to work "out of the box" in CLion
- Has a launcher pre-configured for running the tests inside CLion

## Pre-requisites

You'll need to have [cookiecutter
installed](https://github.com/audreyr/cookiecutter). This is a Python
tool - on most platforms, install using:

```
$ pip install cookiecutter
```

After the project is created, you'll open it in CLion. All going well,
you should have a project that you can compile, link and run from
inside the IDE.

There are some pre-requisites for CLion too. This assumes you have an
up-to-date clang and libc++ install, and that you have configured the
clang toolchain in `File | Settings | Build, Execution, Deployment |
Toolchains`. We recommend using the option for bundled LLDB too.

When we say "up to date", we currently mean "will support the
-std=c++2a" option. These assumptions are fixed into the CMake build.

We also assume that if you want to show code coverage in CLion - and
it's a nice thing to have when doing TDD - then you have congigured
the `llvm-cov` and `llvm-profdata` paths in the panel `File | Settings
| Build, Execution, Deployment | Coverage`. If so - when the project
is opened in CLion - you should be able to run the `All Tests` target
with coverage without further config.

## Generating your project

Start by invoking cookiecutter. This can be done locally - handy if
you're working disconnected:

```
$ cookiecutter <path-to-this-template>
```

or directly from the GitHub URL where the template lives:

```
$ cookiecutter https://github.com/13coders/cookiecutter-kata-catch
```

This template is intended to be very simple, so cookiecutter will
prompt you for only two parameters when you are creating your project:

```
project_name [Project name]:
```

We don't enforce it, but we'd recommend a single, lowercase word for
this - the generated artifacts are far neater.

If you want to, you can always add any extra tools you need (static
analyzers, sanitizers etc) into the CMake file yourself after
generating - it's a minimal starting point for simple experimentation.

## Next steps

Your newly generated project has its own README.md, which has the next
steps for compiling, linking and running the tests. There are also
some useful resources linked in there on TDD, software craft and code
katas to try out.

Happy coding !

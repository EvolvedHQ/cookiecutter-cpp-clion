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

After the project is created, you'll open it in CLion. All going well, you should have a project that you can compile, link and run from inside the IDE.

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

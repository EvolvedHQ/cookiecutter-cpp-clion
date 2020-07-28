# Welcome

Welcome to your new project. Test-driven C++ is both an effective
form of "deliberate practice", and a practical way of experimenting
with new language features. You're almost there - there's one more
step needed to get up and running.

## Open in CLion

The generated project has just enough CLion configuration that you
should be able to open it, and start running immediately.

After opening, seelct `Run -> Run 'All Tests'` and the project should
build, run, and display the test results in the Test Results
panel. You can also try `Run -> Run 'All Tests' with Coverage` if you
have configured your settings to identify the location of `llvm-cov`
and `llvm-profdata`.

## The TDD cycle

TDD gives you a fast feedback cycle, and helps you evolve a solution
incrementally, in very small steps. TDD gives you feedback on your
design and lets you make many, small improvements to your code. You
can do this with confidence because the tests will catch any
accidental regression as you apply these refactorings.

TDD uses a cycle of three phases, always starting with RED : a
failing test, or failing compilation.

```
  +--------------------------------+
  | RED: write the smallest amount |
  | of code to make the test fail, +------------+
  | and treat compilation failures |            |
  | as a test failure.             |            |
  +--------------------------------+            |
         ^                                      |
         |                                      v
         |                +-------------------------------------+
         |                | GREEN: write the smallest amount of |
         |                | production code to pass the one     |
         |                | failing test.                       |
         |                +---------------------+---------------+
         |                                      |
         |                                      |
     +---+-----------------------------+        |
     | REFACTOR: clean up the code,    |        |
     | remove duplication, improve     |<-------+
     | names to better express intent. |
     +---------------------------------+
```

## The Four Rules of Simple Design

When you're doing a kata, try to stick to the "four rules" as
described first by Kent Beck:

- Passes the tests
- Reveals intention
- No duplication
- Fewest elements

These are described very well by Joe Rainsberger
[here](http://blog.jbrains.ca/permalink/the-four-elements-of-simple-design)
and
[here](http://blog.thecodewhisperer.com/permalink/putting-an-age-old-battle-to-rest/). Corey
Haines wrote an [excellent, small
book](https://leanpub.com/4rulesofsimpledesign) on the subject based
on his observations running the "Game Of Life" Kata over many code
retreats.

## Resources

There's a great list of Code Kata exercises at
[codekata.com](http://codekata.com/). Emily Bache wrote and published
[a guide book](https://leanpub.com/codingdojohandbook) on code katas,
with guidance and ideas for running coding dojos.

Also read the manuals for the Catch2 test librarie we've included in
this cookiecutter template - the modern C++ [Catch2 unit testing
framework](https://github.com/catchorg/Catch2/blob/master/docs/tutorial.md)

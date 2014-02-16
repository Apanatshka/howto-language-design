Title: Programming Language Design, a list of high-level questions and
       suggestions
Author: Jeff Smits

Programming Language Design
===========================
_A list of high-level questions and suggestions_

Compiled by Jeff Smits  
Inspired by lots of programming languages, and personal considerations.

## Contents
[TOC]

Goal of the language
--------------------
_Why else have one?_

* General purpose or domain specific?
* Quick prototyping or static guarantees?

### Goal related
* Target platform(s)/language(s)?

Syntax
------
_How the code looks._

* Based on what language(s)?
* Text-based?
* Constrained or flexible?
    * Custom operators?
    * Custom brackets?
    * Larger custom syntactic structures?
* ASCII[^ASCII] or ANSI[^ANSI]?
* Simple basics or mandatory, structuring, reserved words?
* White-space/indentation sensitive?
* Split different kinds of information about the same thing?
  (e.g. types and values like in C, or code and documentation)
* Level of verbosity? Through mandatory syntax or through convention?

[^ASCII]: Standard of 256 characters the most simple editor supports. 
[^ANSI]: A large standard of encompassing every character you're likely
         to care about. 

### Syntax related
* Standard issue pretty-printer/auto-formatter?

Semantics
---------
_The meaning of the code, and the power of the language._

* Based of what paradigm(s)?
* Static or dynamic types? If static,
    * effect types?
    * dependent types?
        * proof assistant properties?

### Semantics related
* Foreign Function Interface?
* Meta-programming?
    * Static or at run-time?
* Built-in testing facilities? (Might be required for some work to
  support in some paradigms!)
* What compile-time checks are performed?
* What's a compile-time error, what a warning?
* Permissive & easy to prototype or strict & strong(er) stability
  claims?

Module system
-------------
_How code can/should be structured._

* Circular dependencies possible?
* Hierarchical?
* Based on e.g. URLs, like Java?
* Meaningful within file system? (i.e. `moduleA.moduleB` means can 
  be found in file `./moduleA/moduleB.language_extension`)

Facilities
----------
_Far more important than you might think!_

### Build system
* Part of the compiler? (Usually becomes more important when other
  languages get involved (e.g. through the FFI), so built into the
  compiler might not be scalable.)
* Automatic testing?

*[FFI]: Foreign Function Interface

### Dependency management
* Multiple versions allowed?
* Auto-download dependencies? (related to 
  [Library sharing](#library-sharing))

### Library sharing
* Self-hosted?
* Open or curated? Or both?
* What search facilities?
* Hosted documentation? (also consider the bullets at
  [Documentation](#documentation), especially tutorial stuff)

### Version control integration
* Incremental tools? (compiling/building/formatting)
* Pre-commit formatting? Or perhaps auto-packing and unpacking to
  keep formatting from being a change?

### Editor services
e.g. name resolution, outline, search by type, auto-formatting,
 documentation extraction, etc.

* Standalone IDE?
* Plug-in support for existing editors?
* Editor agnostic tools? (e.g. through CLI)

*[CLI]: Command-line interface

### Other tools
* Run-time introspection/ debugger?
* Performance and resource profiling?
* REPL? (interactive interpreter)
* Continuous integration[^CI]?
* Visualisation of program properties?

[^CI]: A combination of version control system with build/testing
       system, that validates changes don't break the build process
       and current tests before accepting those changes. 

*[REPL]: Read-Evaluate-Print Loop
*[IDE]: Integrated Development Environment

Documentation
-------------
_You can't really spend too much time on this._

* Formal description (document) of the language? (syntax, semantics,
  more?)
* Usage description of the syntax? (i.e. __not__ for language designers)
* Usage description of the semantics? (perhaps combined with the above)
* Beginner tutorial?
    * For people from different backgrounds? (Depends on 
      [Language goals](#goal-of-the-language))
    * For people who know different programming paradigms?
* Learn by example?
    * On a per library basis?
    * On a per subject basis? (e.g. some kind of cookbook)
* Online REPL?
* Community examples? (i.e. not contrived/educational, but more of a
  small showcase; although preferably with nice, well documented code)

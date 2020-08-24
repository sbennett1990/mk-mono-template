This is the README file for the make "include" files for Mono/C# programs
built on OpenBSD.
The files can be copied into specific directories, and are, by convention,
named with the suffix ".mk".

# Makefiles

* mono.prog.mk		- building programs from source files
* mono.lib.mk		- support for building libraries (i.e. projects that aren't part of the 'main' program)

# Caveats

These makefiles only work with BSD make because they depend on BSD
extensions. Additionally, they have only been tested on OpenBSD
because that's what I use.

# Variables

The following variables can be set to customize the build process for
your program. These should be defined in the primary makefile only;
there is no need to modify the make "include" files.

* PROG

> The name of the program to build. Do not tack on the extension.

* SRCS

> List of source files to build the program.

* MAIN

> Name of the class that holds the entry-point Main()

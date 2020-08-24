# Make Include Files

This is the README file for the make "include" files for Mono/C# programs
built on OpenBSD.
The files can be copied into specific directories, and are, by convention,
named with the suffix ".mk".

## Makefiles

* mono.prog.mk		- building programs from source files
* mono.lib.mk		- support for building libraries (i.e. projects that aren't part of the 'main' program)

## Caveats

These makefiles only work with BSD make because they depend on BSD
extensions. Additionally, they have only been tested on OpenBSD
because that's what I use.

### mono.prog.mk

The include file **"mono.prog.mk"** handles building C# programs
from one or more source files.

#### Targets

**all:**  
**release:**

> Build the program and the libraries it depends on.

**clean:**

> Remove the program and any other automatically generated files
> (including files from **debug** builds).

**debug:**

> Build a debug version of the program and dependencies.

**libs:**

> Build any dependent libraries.

**obj:**

> Create the output directory. This should be ran before anything else.

#### Variables

The following variables can be set to customize the build process for
your program. These should be defined in the primary makefile only;
there is no need to modify the make "include" files.

Required variables:

* PROG

> The name of the program to build. Do not tack on the extension.

* SRCS

> List of source files to build the program.

* SRCDIR

> Directory that contains the sources for the main program.
> This should be relative to the makefile.

* MAIN

> Name of the class that holds the entry-point *Main()*

* BINDIR

> Target directory for built artifacts.

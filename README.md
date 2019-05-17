<!--
author:   André Dietrich

email:    andre.dietrich@ovgu.de

version:  0.0.1

language: en

narrator: US English Female

comment:  Try to write a short comment about
          your course, multiline is also okay.

import:   https://raw.githubusercontent.com/liaScript/rextester_template/master/README.md

@run:     @Rextester.C

-->

# C-Programming

> **Wikibooks Contributors Present:**
>
> A comprehensive look at the C programming language and its features.

## Why learn C?

C is the most commonly used programming language for writing
[operating systems](https://en.wikipedia.org/wiki/operating_systems). The first
operating system written in C is [Unix](https://en.wikipedia.org/wiki/Unix).
Later operating systems like [GNU/Linux](https://en.wikipedia.org/wiki/Linux)
were all written in C. Not only is C the language of operating systems, it is
the precursor and inspiration for almost all of the most popular high-level
languages available today. In fact, [Perl](https://en.wikipedia.org/wiki/Perl),
[PHP](https://en.wikipedia.org/wiki/PHP),
[Python](https://en.wikipedia.org/wiki/Python_%28programming_language%29) and
[Ruby](https://en.wikipedia.org/wiki/Ruby_%28programming_language%29) are all
written in C.

By way of analogy, let's say that you were going to be learning Spanish,
Italian, French, or Romanian. Do you think knowing Latin would be helpful? Just
as Latin was the basis of all of those languages, knowing C will enable you to
understand and appreciate an entire family of programming languages built upon
the traditions of C. Knowledge of C enables freedom.

### Why C and not assembly language?

While [assembly language](https://en.wikipedia.org/wiki/Assembly_language) can
provide speed and maximum control of the program, C provides portability.

Different processors are programmed using different Assembly languages and
having to choose and learn only one of them is too arbitrary. In fact, one of
the main strengths of C is that it combines universality and portability across
various computer architectures while retaining most of the control of the
hardware provided by assembly language.

For example, C programs can be compiled and run on the HP 50g calculator
([ARM](https://en.wikipedia.org/wiki/ARM_architecture) processor), the TI-89
calculator ([68000](https://en.wikipedia.org/wiki/Motorola_68000) processor),
Palm OS Cobalt smartphones (ARM processor), the original iMac
([PowerPC](https://en.wikipedia.org/wiki/PowerPC)), the Arduino
([Atmel AVR](https://en.wikipedia.org/wiki/Atmel_AVR)), and the Intel iMac
([Intel](https://en.wikipedia.org/wiki/x86) Core 2 Duo). Each of these devices
has its own assembly language that is completely incompatible with the assembly
language of any other.

Assembly, while extremely powerful, is simply too difficult to program large
applications and hard to read or interpret in a logical way. C is a compiled
language, which creates fast and efficient executable files. It is also a small
“what you see is all you get” language: a C statement corresponds to at most a
handful of assembly statements, everything else is provided by library
functions.

So is it any wonder that C is such a popular language?

Like toppling dominoes, the next generation of programs follows the trend of its
ancestors. Operating systems designed in C always have system libraries designed
in C. Those system libraries are in turn used to create higher-level libraries
(like [OpenGL](https://en.wikipedia.org/wiki/OpenGL), or
[GTK](https://en.wikipedia.org/wiki/GTK)), and the designers of those libraries
often decide to use the language the system libraries used. Application
developers use the higher-level libraries to design word processors, games,
media players and the like. Many of them will choose to program in the language
that the higher-level library uses. And the pattern continues on and on and
on...

### Why C, and not another language?

The primary design of C is to produce portable code while maintaining
performance and minimizing footprint
([CPU time](https://en.wikipedia.org/wiki/CPU_time),
[memory](https://en.wikipedia.org/wiki/Computer_memory) usage, disk I/O, etc.).
This is useful for
[operating systems](https://en.wikipedia.org/wiki/Operating_systems),
[embedded systems](https://en.wikipedia.org/wiki/Embedded_systems) or other
programs where performance matters a lot (“high-level” interface would affect
performance). With C it’s relatively easy to keep a mental picture of what a
given line really does, because most of the things are written explicitly in the
code. C has a big codebase for low level applications. It is the “native”
language of [UNIX](https://en.wikipedia.org/wiki/Unix), which makes it flexible
and portable. It is a stable and mature language which is unlikely to disappear
for a long time and has been ported to most, if not all, platforms.

One powerful reason is memory allocation. Unlike most programming languages, C
allows the programmer to write directly to memory. Key constructs in C such as
structs, pointers and arrays are designed to structure and manipulate memory in
an efficient, machine-independent fashion. In particular, C gives control over
the memory layout of data structures. Moreover dynamic memory allocation is
under the control of the programmer (which also means that memory deallocation
has to be done by the programmer). Languages like
[Java](https://en.wikipedia.org/wiki/Java_%28programming_language%29) and Perl
shield the programmer from having to manage most details of memory allocation
and pointers (except for
[memory leaks](https://en.wikipedia.org/wiki/Memory_leak) and some other forms
of excess memory usage). This can be useful since dealing with memory allocation
when building a high-level program is a highly error-prone process. However,
when dealing with low-level code such as the part of the OS that controls a
device, C provides a uniform, clean interface. These capabilities just do not
exist in most other languages.

While Perl, PHP, Python and Ruby may be powerful and support many features not
provided by default in C, they are not normally implemented in their own
language. Rather, most such languages initially relied on being written in C (or
another high-performance programming language), and would require their
implementation be ported to a new platform before they can be used.

As with all programming languages, whether you want to choose C over another
high-level language is a matter of opinion and both technical and business
requirements could dictate which language is required.


## History

The field of computing as we know it today started in 1947 with three scientists
at Bell Telephone Laboratories —
[William Shockley](https://en.wikipedia.org/wiki/William_Shockley),
[Walter Brattain](https://en.wikipedia.org/wiki/Walter_Brattain), and
[John Bardeen](https://en.wikipedia.org/wiki/John_Bardeen) — and their
groundbreaking invention: the
[transistor](https://en.wikipedia.org/wiki/transistor). In 1956, the first fully
transistor-based computer, the [TX-0](https://en.wikipedia.org/wiki/TX-0), was
completed at MIT. The first
[integrated circuit](https://en.wikipedia.org/wiki/integrated_circuit) was
created in 1958 by [Jack Kilby](https://en.wikipedia.org/wiki/Jack_Kilby) at
Texas Instruments, but the first high-level programming language existed even
before then.

"The [Fortran](https://en.wikipedia.org/wiki/Fortran) project" was originally
developed in 1954 by IBM. A shortening of
"_The IBM Mathematical **For**mula **Tran**slating System_", the project had the
purpose of creating and fostering development of a procedural, imperative
programming language that was especially suited to numeric computation and
scientific computing. It was a breakthrough in terms of productivity and
programming ease (compared to assembly language) and speed (Fortran programs ran
nearly as fast as, and in some cases, just as fast as, programs written in
assembly). Furthermore, Fortran was written at a high-enough level (and thus was
machine independent enough) to become the first widely adopted programming
language. The Algorithmic Language
([Algol 58](https://en.wikipedia.org/wiki/ALGOL_58))
was derived from Fortran in 1958 and evolved into
[Algol 60](https://en.wikipedia.org/wiki/ALGOL_60) in 1960. The
[Combined Programming Language (CPL)](https://en.wikipedia.org/wiki/Combined_Programming_Language)
was then created out of Algol 60 in 1963. In 1967, it evolved into
[Basic CPL](https://en.wikipedia.org/wiki/BCPL), which was itself, the base for
B in 1969. Finally, B, the root of C, was created in 1971.

C was the direct successor of B, a stripped down version of BCPL, created by
[Ken Thompson](https://en.wikipedia.org/wiki/Ken_Thompson) at Bell Labs, that
was also a [compiled language](https://en.wikipedia.org/wiki/compiled_language) -
[User's Reference to B](https://www.bell-labs.com/usr/dmr/www/kbman.pdf), used
in early internal versions of the UNIX operating system. As noted in Ritchie's
[C History](https://www.bell-labs.com/usr/dmr/www/chist.html): "The B compiler
on the PDP-7 did not generate machine instructions, but instead 'threaded code',
an interpretive scheme in which the compiler's output consists of a sequence of
addresses of code fragments that perform the elementary operations. The
operations typically — in particular for B — act on a simple stack machine".
Thompson and [Dennis Ritchie](https://en.wikipedia.org/wiki/Dennis_Ritchie),
also working at Bell Labs, improved B and called the result NB. Further
extensions to NB created its logical successor, C. Most of UNIX was rewritten in
NB, and then C, which resulted in a more portable operating system.

The portability of UNIX was the main reason for the initial popularity of both
UNIX and C. Rather than creating a new operating system for each new machine,
system programmers could simply write the few system-dependent parts required
for the machine, and then write a C compiler for the new system. Since most of
the system utilities were thus written in C, it simply made sense to also write
new utilities in C.

The American National Standards Institute began work on standardizing the C
language in 1983, and completed the standard in 1989. The standard, ANSI
X3.159-1989 "Programming Language C", served as the basis for all
implementations of C compilers. The standards were later updated in 1990 and
1999, allowing for features that were either in common use, or were appearing in
C++.

## What you need before you can learn

### Getting Started

The goal of this book is to introduce you to and teach you the C programming language. Basic computer literacy is assumed, but no special knowledge is needed.

Before you can start programming in C, you will need a __C__
__[compiler](https://en.wikipedia.org/wiki/Compiler)__. A compiler is a program
that converts C code into executable
[machine code](https://en.wikipedia.org/wiki/machine_code).[^1]


__Popular C compilers/IDEs include:__


| Name                              | Website       | Platform  | License                     | Details |
|-----------------------------------|---------------|-----------|-----------------------------|---------|
| Microsoft Visual Studio Community | Visual Studio | Windows   | Proprietary, free of charge | Powerful and student-friendly version of an industry standard compiler. |
| Xcode                             | Xcode         | macOS, OSX         | Proprietary, free of charge | Default IDE on macOS             |
| Tiny C Compiler (TCC)             | tinycc        | GNU/Linux, Windows | LGPL                        | Small, fast and simple compiler. |
| Clang                             | clang         | GNU/Linux, Windows, Unix, OS X | University of Illinois/NCSA License | A free, permissively licensed front-end using a LLVM backend. |
| GNU C Compiler | gcc | GNU/Linux, MinGW or mingw-w64 (Windows), Unix, OS X. | GPL | The De facto standard. Ships with most Unix systems. |


The minimum software requirements to program in C is a
[text editor](https://en.wikipedia.org/wiki/Text_Editor), as opposed to a
[word processor](https://en.wikipedia.org/wiki/Word_Processor). A plain text
Notepad editor can be used but it does not offer any advanced capabilities such
as syntax highlighting and code completion. There are many text editors
([see List of Text Editors](https://en.wikipedia.org/wiki/List_of_text_editors)),
among the most popular are
[Notepad++](https://en.wikipedia.org/wiki/Notepad%2B%2B) for Windows as well as
[Atom](https://atom.io/),
[Sublime Text](https://en.wikipedia.org/wiki/Sublime_Text),
[gedit](https://en.wikipedia.org/wiki/gedit),
[Vim](https://en.wikipedia.org/wiki/Vim_%28text_editor%29) and
[Emacs](https://en.wikipedia.org/wiki/Emacs) which are also available on other
operating systems (“cross-platform”). These text editors come with
[syntax highlighting](https://en.wikipedia.org/wiki/syntax_highlighting) and
line numbers, which makes code easier to read at a glance, and to spot syntax
errors.

Though not absolutely needed, many programmers prefer and recommend using an
[Integrated development environment](https://en.wikipedia.org/wiki/Integrated_development_environment)
(__IDE__) instead of a text editor. An IDE is a
suite of programs that developers need, combined into one convenient package,
usually with a graphical user interface. These programs include a text editor
and file browser and are sometimes bundled with an easily accessible compiler.
They also typically include a debugger, a tool that will enable you to do such
things as step through the program you develop manually one source code line at
a time, or alter data as an aid to finding and correcting programming errors.

Many IDEs do not offer their users a console-based interface to the compiler and
for executing the developed program but offer only graphical buttons. For
beginners it is recommended not to use such an IDE, since it hides most of what
is going on. Using the command line builds up familiarity with the toolchain.
Such an IDE may still be useful to somebody with programming experience who
knows how the IDE works. So as a general guideline: Do not use an IDE unless you
know what the IDE does!


__Other popular compilers/IDEs include:__


| Name | Website | Platform | License | Details |
|------|---------|----------|---------|---------|
| Eclipse CDT   | Eclipse  | Windows, Mac OS X, GNU/Linux | Free/Libre and Open Source | Eclipse IDE for C/C++ developement, a popular open source IDE. |
| Netbeans      | Netbeans | Cross-platform               | CDDL and GPL 2.0           | A Good comparable matured IDE to Eclipse. |
| GNOME Builder | Builder  | GNU/Linux                    | GPL                        | A feature-rich but simple IDE for the GNOME desktop environment. |
| Anjuta        | Anjuta   | GNU/Linux                    | GPL                        | An extensible GTK+3 IDE for the GNOME desktop environment. |
| Geany         | geany    | Cross-platform               | GPL                        | A lightweight cross-platform GTK+ notepad based on Scintilla, with basic IDE features. |
| KDevelop      | KDevelop | Cross-platform               | GPL                        | A cross-platform IDE for the KDE project. |
| Little C Compiler (LCC) | lcc | Windows | Open Source but not Libre | Small open source compiler. |
| Xcode | Xcode | Mac OS X | Proprietary, free of charge | Available free of charge at Mac App Store. |
| Pelles C | Pelles C | Windows, Pocket PC | Proprietary, free of charge  |  A complete C development kit for Windows.  |
| Dev-C++  | Dev C++  | Windows | GPL | Updated version of the formerly popular Bloodshed Dev-C++.  |
| Microsoft Visual Studio Community |  Visual Studio  |  Windows | 	Proprietary, free of charge |  Microsoft’s compiler already mentioned above comes bundled with an IDE. |
| CodeLite | CodeLite | Cross-platform | GPL 2 | Free IDE for C/C++ development. |
| Code::Blocks | Code::Blocks | Cross-platform | GPL 3.0 | Built to meet users' most demanding needs. Very extensible and fully configurable. |

On __GNU/Linux__, GCC is almost always included by default.

On __Microsoft Windows__, Dev-C++ is recommended for beginners because it is
easy to use, free, and simple to install. Although the initial developer
(Bloodshed) hasn’t updated it since 2005, a new version appeared in 2011, made
by an independent programmer, and is being actively developed.[^2] An alternate
option for those working only in the Windows environment is the proprietary
Microsoft Visual Studio Community which is free of charge and has an excellent
debugger.

On __Mac OS X__, the Xcode IDE provides the compilers needed to compile various
source files. The newer versions do not include the command line tools. They
need to be downloaded via Xcode->Preferences->Downloads. Footnotes




[^1]: Actually, GCC’s (GNU C Compiler) __cc__ (C Compiler) translates the input
      .c file to the target CPU’s
      [assembly](https://en.wikipedia.org/wiki/Assembly_language), output is
      written to an .s file. Then __as__ (assembler) generates a machine code
      file from the .s file. Pre-processing is done by another sub-program
      __cpp__ (C PreProcessor), which is not to be confused with __c++__ (a
      compiler for another programming language).

[^2]: http://orwelldevcpp.blogspot.com/

## Obtaining a compiler

### Dev-C++

[Dev C++](https://en.wikipedia.org/wiki/Dev-C_Plus_Plus) is an Integrated
Development Environment(IDE) for the C++ programming language, available from
[Bloodshed Software](http://www.bloodshed.net/). An updated version is available
at [Orwell Dev-C++](http://orwelldevcpp.blogspot.com/). C++ is a programming
language which contains within itself most of the C language, plus extensions.
Most C++ compilers will compile C programs, sometimes with a few adjustments
(like invoking them with a different name or command line switch). Therefore,
you can use Dev C++ for C development.

However, Dev C++ is not the compiler. It is designed to use the
[MinGW](https://en.wikipedia.org/wiki/MinGW) or
[Cygwin](https://en.wikipedia.org/wiki/Cygwin) versions of
[GCC](https://en.wikipedia.org/wiki/GCC) - both of which can be obtained as part
of the Dev C++ package, although they are completely different projects. Dev C++
simply provides an editor, syntax highlighting, some facilities for the
visualisation of code (like class and package browsing) and a graphical
interface to the chosen compiler. Because Dev C++ analyses the error messages
produced by the compiler and attempts to distinguish the line numbers from the
errors themselves, the use of other compiler software is discouraged since the
format of their error messages is likely to be different.

The latest version of Dev-C++ is a
[beta](https://en.wikipedia.org/wiki/beta_version) for version 5. However, it
still has a significant number of bugs. All the features are there, and it is
quite usable. It is considered one of the best free software C IDEs available
for Windows.

A version of Dev C++ for Linux is in the pipeline. It is not quite usable yet,
however. Linux users already have a wealth of IDEs available. (e.g.
[KDevelop](https://en.wikipedia.org/wiki/KDevelop) and
[Anjuta](https://en.wikipedia.org/wiki/Anjuta).) Most of the graphical text
editors, and other common editors such as _emacs_ and _vim_, support
[syntax highlighting](https://en.wikipedia.org/wiki/syntax_highlighting).

__Steps for Obtaining Dev-C++ if You're on Windows__

1. Go to https://sourceforge.net/projects/orwelldevcpp/ and pick the download
   option.
2. The setup is pretty straight forward. Make sure the compiler option is ticked.
3. You can now use the environment provided by the software to write and run
   your code.
4. OPTIONALLY: "C:\Program Files (x86)\Dev-Cpp\MinGW64\bin" can be added to the
   global PATH variable of the operating system to compile with gcc from a
   command prompt.

### GCC

The [GNU Compiler Collection](https://en.wikipedia.org/wiki/GNU_Compiler_Collection)
(GCC) is a [free/libre](https://en.wikipedia.org/wiki/free_software) set of
compilers developed by the
[Free Software Foundation](https://en.wikipedia.org/wiki/Free_Software_Foundation).

__Steps for Obtaining the GCC Compiler if You're on GNU/Linux__

On __GNU/Linux__, Installing the GNU C Compiler can vary in method from
[distribution](https://en.wikipedia.org/wiki/Linux_distribution) to
distribution. (Type in __cc -v__ to see if it is installed already.)

* For [Ubuntu](https://en.wikipedia.org/wiki/Ubuntu), install the GCC compiler
  (along with other necessary tools) by using `sudo apt install` build-essential,
  or by using Synaptic. You do not need Universe enabled.
* For [Debian](https://en.wikipedia.org/wiki/Debian), install the GCC compiler
  (as root) by using `apt install gcc`.
* For [Fedora Core](https://en.wikipedia.org/wiki/Fedora_Core), install the GCC
  compiler (as root) by using `yum install gcc`.
* For [Redhat](https://en.wikipedia.org/wiki/Redhat), get a GCC
  [RPM](https://en.wikipedia.org/wiki/RPM_Package_Manager), e.g. using Rpmfind
  and then install (as root) using `rpm -ivh gcc-version-release.arch.rpm`
* For `Mandrake`, install the GCC compiler (as root) by using `urpmi gcc`.
* For [Slackware](https://en.wikipedia.org/wiki/Slackware), the package is
  available on their [website](http://www.slackware.com/pb/) - simply download,
  and type `installpkg gcc-xxxxx.tgz`.
* For [Gentoo](https://en.wikipedia.org/wiki/Gentoo), you should already have
  GCC installed as it will have been used when you first installed. To update it
  run (as root) `emerge -uav gcc`.
* For [Arch Linux](https://en.wikipedia.org/wiki/Arch_Linux), install the GCC
  compiler (as root) by using `pacman -S gcc`.
* If you cannot become root, get the GCC tarball from ftp://ftp.gnu.org/ and
  follow the instructions in it to compile and install in your home directory.
  Be warned though, you need a C compiler to do that - yes, GCC itself is
  written in C.
* You can use a commercial C compiler/IDE.


__Steps for Obtaining the GCC Compiler if You're on BSD Family Systems__

* For [Mac OS X](https://en.wikipedia.org/wiki/Mac_OS_X),
  [FreeBSD](https://en.wikipedia.org/wiki/FreeBSD),
  [NetBSD](https://en.wikipedia.org/wiki/NetBSD),
  [OpenBSD](https://en.wikipedia.org/wiki/OpenBSD),
  [DragonFly BSD](https://en.wikipedia.org/wiki/DragonFly_BSD),
  [Darwin](https://en.wikipedia.org/wiki/Darwin) the port of GNU gcc is
  available in the base system, or it could be obtained using the ports
  collection or [pkgsrc](https://en.wikipedia.org/wiki/pkgsrc).
* Homebrew is a commonly used package manager for Mac OS X.


__Steps for Obtaining the GCC Compiler if You're on Windows__

There are two ways to use GCC on Windows: Cygwin and MinGW. Applications
compiled with Cygwin will not run on any computer without Cygwin, so MinGW is
recommended. MinGW is simpler to install, and takes less disk space.

To get MinGW, do this:

1. Go to http://sourceforge.net/projects/mingw/ download and save this to your
   hard drive.
2. Once the download is finished, open it and follow the instructions. You can
   also choose to install additional compilers, or the tool Make, but these
   aren't necessary.
3. Now you need to set your PATH. Right-click on "My computer" and click
   "Properties". Go to the "Advanced" tab and click on "Environment variables".
   Go to the "System variables" section and scroll down until you see "Path".
   Click on it, then click "edit". Add ";C:\mingw\bin\" (without the quotes) to
   the end.
4. To test if GCC works, open a command prompt and type "gcc". You should get
   the message "gcc: fatal error: no input files compilation terminated.". If
   you get this message, GCC is installed correctly.

To get Cygwin, do this:

1. Go to http://www.cygwin.com and click on the "Install Cygwin Now" button in
   the upper right corner of the page.
2. Click "run" in the window that pops up, and click "next" several times,
   accepting all the default settings.
3. Choose any of the Download sites ("ftp.easynet.be", etc.) when that window
   comes up; press "next" and the Cygwin installer should start downloading.
4. When the "Select Packages" window appears, scroll down to the heading "Devel"
   and click on the "+" by it. In the list of packages that now displays, scroll
   down and find the "gcc-core" package; this is the compiler. Click once on the
   word "Skip", and it should change to some number like "3.4" etc. (the version
   number), and an "X" will appear next to "gcc-core" and several other related
   packages that will now be downloaded.
5. Click "next" and the compiler as well as the Cygwin tools should start
   downloading; this could take a while. While you're waiting for the
   installation to finish, download any text-editor designed for programming.
   While Cygwin does include some, you may prefer doing a web search to find
   other alternatives. While using a stock text editor is possible, it is not
   ideal.
6. Once the Cygwin downloads are finished and you have clicked "next", etc. to
   finish the installation, double-click the Cygwin icon on your desktop to
   begin the Cygwin "command prompt". Your home directory will automatically be
   set up in the Cygwin folder, which now should be at "C:\cygwin" (the Cygwin
   folder is in some ways like a small unix/linux computer on your Windows
   machine -- not technically of course, but it may be helpful to think of it
   that way).
7. Type "gcc" at the Cygwin prompt and press "enter"; if "gcc: no input files"
   or something like it appears you have succeeded and now have the gcc compiler
   on your computer (and congratulations -- you have also just received your
   first error message!).

Third option is to use WSL:

1. Go to http://aka.ms/wsldocs and follow the steps to install
   [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
2. Go to https://aka.ms/vscode and follow the steps to install
   [VSCode](https://code.visualstudio.com/docs/setup/windows)
3. Follow the guide and choose
   [Get Started with C++ and WSL](https://code.visualstudio.com/docs/cpp/config-wsl)
4. As a result you will need to install possibly
   [Ubuntu](https://code.visualstudio.com/docs/cpp/config-wsl#_set-up-your-linux-environment)
   and set-up accordingly installing GCC like the Linux guide above.

The current stable (usable) version of GCC is 4.9.1 published on 2014-07-16,
which supports several platforms. In fact, GCC is not only a C compiler, but a
family of compilers for several languages, such as C++,
[Ada](https://en.wikibooks.org/wiki/Ada_Programming),
[Java](https://en.wikibooks.org/wiki/Java), and
[Fortran](https://en.wikibooks.org/wiki/Fortran).


### Embedded systems

Most CPUs are microcontrollers in embedded systems, often programmed in C, but
most of the compilers mentioned above (except GCC) do not support such CPUs. For
specialized compilers that do support embedded systems, see
[Embedded Systems/C Programming](https://en.wikibooks.org/wiki/Embedded_Systems/C_Programming).


### Other C compilers

We have a long
[list of C compilers](https://en.wikibooks.org/wiki/C_Programming/Compilers) in
a much later section of this Wikibook.
_Which of those compilers would be suitable for beginning C programmers, that we should say a few words about getting started with that particular compiler in this section of this Wikibook?_


## Intro exercise

__The "Hello, World!" Program__

Tradition dictates that we begin with a very simple program, which simply
displays the characters "Hello, World!" on the screen and immediately exits.
Type the following source code in your preferred text editor/IDE and save this
in a file named __hello.c__.

``` c
#include <stdio.h>

int main(void)
{
  printf("Hello, World!\n");
  return 0;
}
```
@run

### Source code analysis

Below are described the parts the program is composed of. The various details
will be introduced and explained in later chapters.

``` c
#include <stdio.h>
```

This is a preprocessor directive.
[Preprocessor directives](https://en.wikipedia.org/wiki/Preprocessor_directives)
instruct a part of the compiler - the __preprocessor__ - to modify the code
we've written before it is compiled. In this case, the `#include` directive
retrieves C code from the __stdio.h__ file found in the standard library. Files
used in this way are called __header files__ and are saved with the __.h__
extension. The __stdio.h__ file contains many functions defined according to the
C standard. For this program, the only function we need from stdio.h is the
`printf` function.

``` c
int main(void)
```

The __function__ named main is the starting point of all C programs. In computer
science, the term function tends to be used a bit more loosely than in
mathematics, since functions often express imperative ideas (as in the case of
C) - that is, _how-to_ process, instead of declarations. For now, suffice it to
say, functions let us define a complex process that we want to reference
frequently.

``` c
  printf("Hello World!\n");
```

This line is of particular interest because it produces the actual output on the
__console__ (also known as the _terminal_ in the context of Unix-like operating
systems), a traditional text-based interface to system utilities and programs.

``` c
  return 0;
```

When terminating our program, it is useful to be able to let the operating
system know whether or not the program succeeded. We do this with an
__exit status__, which is sent to the operating system with a `return` statement
in the `main` function. In this case, we provide an exit status of `0` to
indicate that execution succeeded without error. As our programs grow in
complexity, we can use other integers as codes to indicate various types of
errors. This style of providing exit status is a long standing convention[^1].


[^1]: https://www.gnu.org/software/libc/manual/html_node/Exit-Status.html

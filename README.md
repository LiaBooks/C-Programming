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



### Compiling

__Unix-like__

If you are using a Unix(-like) system, such as
[GNU/Linux](https://en.wikipedia.org/wiki/GNU/Linux),
[Mac OS X](https://en.wikipedia.org/wiki/Mac_OS_X), or
[Solaris](https://en.wikipedia.org/wiki/Solaris_Operating_Environment), it will
probably have GCC installed, otherwise on Linux you can install it using yum or
apt-get commands depending on your distribution. Open the virtual console or a
terminal emulator and enter the following (be certain your current working
directory is the one containing your source code):

```bash
gcc hello.c
```

By default gcc will generate our executable binary with the name a.out. To run
your new generated program type:

```bash
./a.out
```

You should see `Hello, World!` printed after the last prompt.

To see the exit status of the last program you ran, type on your shell command:

``` bash
echo $?
```

This shows the value the main function has returned, which is 0 in the above
example.

There are a lot of options you can use with the gcc compiler. For example, if
you want the output to have a name other than a.out, you can use the `-o`
option. The following shows a few examples:

`-o` indicates that the next parameter is the name of the resulting program (or
library). If this option is not specified, the compiled program will, for
historic reasons, end up in a file called "a.out" or "a.exe" (for cygwin users).

`-Wall` indicates that gcc should warn about many types of suspicious code that
are likely to be incorrect.

You can use these options to create a program called "helloworld" instead of
"a.out" by typing:

``` bash
gcc -o helloworld hello.c -Wall
```

Now you can run it by typing:

``` bash
./helloworld
```

All the options are well documented in the manual[^2] for GCC.

__On IDEs__

If you are using an IDE you may have to select console project, and to compile
you just select build from the menu or the toolbar. The executable will appear
inside the project folder, but you should have a menu button so you can just run
the executable from the IDE. The process is roughly the same on all IDEs.

[^2]: https://gcc.gnu.org/onlinedocs/


## Preliminaries

Before learning C syntax and programming constructs, it is important to learn
the meaning of a few key terms that are central in understanding C.

### Block Structure, Statements, Whitespace, and Scope

Next we'll discuss the __basic structure__ of a C program. If you're familiar
with [PASCAL](https://en.wikipedia.org/wiki/Pascal_%28programming_language%29),
you may have heard it referred to as a __block-structured__ language. C does not
have complete block structure (and you'll find out why when you go over
functions in detail) but it is still very important to understand what blocks
are and how to use them.

> Sentences delimited with '`/*`' and '`*/`' are comments, and the compiler
> ignores them. They are described in Programming Structure and Style

So what is in a __block__? Generally, a block consists of executable
__statements__.

But before we delve into blocks, let's examine statements. One way to describe
statements is they are the text (and surrounding whitespace) the compiler will
attempt to turn into executable instructions. A simpler definition is statements
are bits of code that do things. For example:

``` c
int i = 6;
```

This __declares__ an integer variable, which can be __accessed__ with the
__identifier__ `i`, and __initializes__ it to the value 6. The various data
types are introduced in the chapter
[Variables](https://en.wikibooks.org/wiki/C_Programming/Variables).

You might have noticed the semicolon at the end of the statement. Statements in
C always end with a semicolon (`;`). Leaving off the semicolon is a common mistake
many people make, beginners and experts alike! So until it becomes second
nature, be sure to double check your statements!

Since C is a "free-format" language, several statements can share a single line
in the source file, like this:

``` c
/* this declares the variables 'i', 'test', 'foo', and 'bar'
    note that ONLY the variable named 'bar' is set to six! */
int i, test, foo, bar = 6;
```

There are several kinds of statements. You've already seen some of them, such as
the assignment (`i = 6;`). A substantial portion of this book deals with statement
construction.

Back to our discussion of blocks. In C, blocks begin with an opening brace `{`
and end with a closing brace `}`. Blocks can contain other blocks which can
contain their own blocks, and so on.

Let's look at a block example.

``` c
int main(void)
{
    // this is a 'block'
    int i = 5;

    {
        // this is also a 'block', nested inside the outer block
        int i = 6;
    }

    return 0;
}
```
@run

You can use blocks with the preceding statements, such as the main function
declaration (and other statements we've not yet covered), but you can also use
blocks by themselves.

__Whitespace__ refers to the tab, space and newline characters that separate the
text characters that make up the source code. Like many things in life, it's
hard to appreciate whitespace until it's gone. To a C compiler, the source code

``` c
printf("Hello world"); return 0;
```

is the same as

``` c
printf("Hello world");
return 0;
```

which is also the same as

``` c
printf (
"Hello world") ;



return 0;
```

The compiler simply ignores most whitespace (except, for example, when it
separates `return` from `0`). However, it is common practice to use spaces (or
tabs) to organize source code for human readability.

Most of the time we do not want other functions or other programmer's
[routines](https://en.wikipedia.org/wiki/Subroutine) accessing data we are
currently manipulating, which is why it is important to understand the concept
of scope.

__Scope__ describes the level at which a piece of data or a function is visible.
There are two types of scope in C, __local__ and __global__. When we speak of
__global__ scope, we're referring to something that can be seen or manipulated
from anywhere in the program. __Local__ scope applies to a program element that
can be seen or manipulated only within the block in which it was declared.

Let's look at some examples to get a better idea of scope.

``` c
int i = 5; // this is a 'global' variable, it can be accessed from anywhere in the program

// this is a function, all variables inside of it
// are "local" to the function.
int main(void)
{
  int i = 6; // 'i' now equals 6
  printf("%d\n", i); // prints a '6' to the screen, instead of the global variable of 'i', which is 5

  return 0;
}
```
@run

That shows an example of local and global. But what about different scopes
_inside_ of functions? (you'll learn more about functions later, for now, just
focus on the "main" part.)

``` c
/* the main function */
int main(void)
{
  // this is the beginning of a 'block', you read about those above

  int i = 6; // this is the first variable of this 'block', 'i'

  {
    // this is a new 'block', and because it's a different block, it has its own scope

    // this is also a variable called 'i', but in a different 'block',
    // because it's in a different 'block' than the first variable named 'i', it
    // doesn't affect the first one!
    int i = 5;
    printf("%d\n", i); // prints a '5' onto the screen
  }
  // now we're back into the first block

  printf("%d\n", i); // prints a '6' onto the screen

  return 0;
}
```
@run

### Basics of Using Functions

__Functions__ are a big part of programming. A function is a special kind of
block that performs a well-defined task. If a function is well-designed, it can
enable a programmer to perform a task without knowing anything about how the
function works. The act of requesting a function to perform its task is called a
__function call__. Many functions require a function call to hand it certain
pieces of data needed to perform its task; these are called __arguments__. Many
functions also return a value to the function call when they're finished; this
is called a __return value__ (the return value in the above program is __`0`__).

The things you need to know before calling a function are:

* What the function does
* The data type (discussed later) of the arguments and what they mean
* The data type of the return value and what it means

Many functions use the return value for the result of a computation. Some
functions use the return value to indicate whether they successfully completed
their work. As you have seen in the intro exercise, the `main` function uses the
return value to provide an exit status to the operating system.

All code other than global data definitions and declarations needs to be a part
of a function.

Usually, you're free to call a function whatever you wish to. The only
restriction is that every executable program needs to have one, and only one,
__main__ function, which is where the program begins executing.

We will discuss functions in more detail in a later chapter,
[C Programming/Procedures](https://en.wikibooks.org/wiki/C_Programming/Procedures_and_functions)
and functions.


### The Standard Library

In 1983, when C was in the process of becoming standardized, the
[American National Standards Institute](https://en.wikipedia.org/wiki/American_National_Standards_Institute)
(ANSI) formed a committee to establish a standard specification of C known as
"ANSI C". That standard specification created a basic set of functions common to
each implementation of C, which is referred to as the Standard Library. The
[Standard Library](https://en.wikipedia.org/wiki/C_standard_library) provides
functions for tasks such as input/output, string manipulation, mathematics,
files, and memory allocation. The Standard Library does not provide functions
that are dependent on specific hardware or operating systems, like graphics,
sound, or networking. In the "Hello, World" program, a Standard Library function
is used (`printf`) which outputs lines of text to the
[standard output](https://en.wikipedia.org/wiki/standard_output) stream.


## Basics of compilation

Having covered the basic concepts of C programming, we can now briefly discuss
the process of compilation.

Like any programming language, C by itself is completely incomprehensible to a
[microprocessor](https://en.wikipedia.org/wiki/microprocessor). Its purpose is
to provide an intuitive way for humans to provide instructions that can be
easily converted into machine code that is comprehensible to a microprocessor.
The ___compiler___ is what translates our human-readable source code into
machine code.

To those new to programming, this seems fairly simple. A naive compiler might
read in every source file, translate everything into machine code, and write out
an executable. That could work, but has two serious problems. First, for a large
project, the computer may not have enough memory to read all of the source code
at once. Second, if you make a change to a single source file, you would have to
recompile the entire application.

To deal with these problems, compilers break the job into steps. For each source
file (each `.c` file), the compiler reads the file, reads the files it
references via the `#include` directive, and translates them to machine code.
The result of this is an "object file" (`.o`). After all the object files are
created, a "linker" program collects all of the object files and writes the
actual executable program. That way, if you change one source file, only that
file needs to be recompiled, after which, the application will need to be
re-linked.

Without going into details, it can be beneficial to have a superficial
understanding of the compilation process.


### Preprocessor

The preprocessor provides the ability for the inclusion of so called header
files, macro expansions, conditional compilation and line control. Many times
you will need to give special instructions to your compiler. This can be done by
inserting preprocessor
[directives](https://en.wikipedia.org/wiki/Preprocessor_directives) into your
code. When you begin compiling your code, a special program called the
preprocessor scans the source code and performs simple substitution of token
strings for others according to predefined rules. The C preprocessor is not a
part of the C language.

All preprocessor directives begin with the hash character (#). You can see one
preprocessor directive in the
[Hello world program](https://en.wikibooks.org/wiki/Hello_world_program).
Example:

``` c
#include <stdio.h>
```

This directive causes the stdio header to be included into your program. Other
directives such as `#pragma` control compiler settings and macros. The result of
the preprocessing stage is a text string. You can think of the preprocessor as a
non-interactive text editor that prepares your code for compilation. The
language of preprocessor directives is agnostic to the grammar of C, so the C
preprocessor can also be used independently to process other kinds of text
files.


### Syntax Checking

This step ensures that the code is valid and will sequence into an executable
program. Under most compilers, you may get messages or warnings indicating
potential issues with your program (such as a
[conditional statement](https://en.wikipedia.org/wiki/Conditional_%28computer_programming%29)
always being true or false, etc.)

When an error is detected in the program, the compiler will normally report the
file name and line that is preventing compilation.


### Object Code

The compiler produces a machine code equivalent of the source code that can be
linked into the final program. At this point the code itself can't be executed,
as it requires linking to do so.

It's important to note after discussing the basics that compilation is a "one
way street". That is, compiling a C source file into machine code is easy, but
"decompiling" (turning machine code into the C source that creates it) is not.
Decompilers for C do exist, but the code they create is hard to understand and
only useful for
[reverse engineering](https://en.wikipedia.org/wiki/Reverse_engineering).


### Linking

Linking combines the separate object files into one complete program by
integrating libraries and the code and producing either an
[executable program](https://en.wikipedia.org/wiki/Executable) or a
[library](https://en.wikipedia.org/wiki/Library_%29computing%29). Linking is
performed by a linker program, which is often part of a compiler suite.

Common errors during this stage are either missing or duplicate functions.


### Automation

For large C projects, many programmers choose to automate compilation, both in
order to reduce user interaction requirements and to speed up the process by
recompiling only modified files.

Most Integrated Development Environments (IDE's) have some kind of project
management which makes such automation very easy. However, the project
management files are often usable only by users of the same integrated
development environment, so anyone desiring to modify the project would need to
use the same IDE.

On UNIX-like systems, [make](https://en.wikibooks.org/wiki/Make) and Makefiles
are often used to accomplish the same. Make is traditional and flexible and is
available as one of the standard developer tools on most Unix and GNU
distributions.

Makefiles have been extended by the

[GNU Autotools](https://en.wikipedia.org/wiki/GNU_Build_System), composed of
[Automake](https://www.gnu.org/software/automake/) and
[Autoconf](https://www.gnu.org/software/autoconf/) for making software
compilable, testable, translatable and configurable on many types of machines.
Automake and Autoconf are described in detail in their respective manuals.

The Autotools are often perceived to be complicated and various simpler build
systems have been developed. Many components of the
[GNOME project](https://en.wikipedia.org/wiki/GNOME) now use the declarative
[Meson build system](http://mesonbuild.com) which is less flexible, but instead
focuses on providing the features most commonly needed from a build system in a
simple way. Other popular build systems for programs written in the C language
include [CMake](https://cmake.org) and [Waf](https://waf.io).

Once gcc is installed, it can be called with a list of c source files that have
been written but not yet compiled. e.g. if the file main.c includes functions
described in myfun.h and implemented in myfun_a.c and myfun_b.c, then it is
enough to write

``` bash
gcc main.c myfun_a.c myfun_b.c
```

myfun.h is included in main.c, but if it is in a separate header file directory,
then that directory can be listed after a "-I " switch.

In larger programs, Makefiles and gnu make program can compile c files into
intermediate files ending with suffix .o which can be linked by gcc.

How to compile each object file is usually described in the Makefile with the
object file as a label ending with a colon followed by two spaces (tabs often
cause problems) followed by a list of other files that are dependencies, e.g. .c
files and .o files compiled in another section, and on the next line, the
invocation of gcc that is required.

Typing `man make` or `info make` often gives the information needed to on how to
use make, as well as gcc.

Although gcc has a lot of option switches, one often used is -g to generate
debugging information for gdb to allow gdb to show source code during a
step-through of the machine code program. gdb has an 'h' command that shows what
it can do, and is usually started with 'gdb a.out' if a.out is the anonymous
executable machine code file that was compiled by gcc. References


## Structure and style

This is a basic introduction to good coding style in the C Programming Language.
It is designed to provide information on how to effectively use indentation,
comments, and other elements that will make your C code more readable. It is not
a tutorial on actual C programming.

As a beginning programmer, the point of creating structure in the program code
might not be clear, as the compiler doesn't care about the difference. However,
as programs become complex, chances are that writing the program has become a
joint effort. (Or others might want to see how it was accomplished. Or you may
have to read it again years later.) Well-written code also helps you get an
overview of what the code does.

In the following sections, we will attempt to explain good programming practices
that will in turn make your programs clearer.

### Introduction

In C, programs are composed of statements. Statements are terminated with a
semi-colon, and are collected in sections known as functions. By convention, a
statement should be kept on its own line, as shown in the example below:

``` c
#include <stdio.h>

int main(void) {
  printf("Hello, World!\n");
  return 0;
}
```
@run

The following block of code is essentially the same. While it contains exactly
the same code, and will compile and execute with the same result, the removal of
spacing causes an essential difference: it's harder to read.

``` c
#include <stdio.h>
int main(void) {printf("Hello, World!\n");return 0;}
```
@run

The simple use of indents and line breaks can greatly improve code readability
without impacting code performance. Readable code makes it much easier to see
where functions and procedures end and which lines are part of which loops and
procedures.

This lesson is going to focus on improving the coding style of an example piece
of code which applies a formula and prints the result. Later, you'll see how to
write code for such tasks in more detail. For now, focus on how the code looks,
not what it does.


### Line Breaks and Indentation

The addition of white space inside your code is arguably the most important part
of good code structure. Effective use of white space can create a visual scale
of how your code flows, which can be very important when returning to your code
when you want to maintain it.

#### Line Breaks

> Note the use of line numbers. They are __not__ part of the actual code. They
> are __only__ for reference.

With minimal line breaks, code is barely human-readable, and may be hard to
debug or understand:

``` c
#include <stdio.h>

int main(void) { int revenue = 80; int cost = 50; int roi; roi = (100 * (revenue - cost)) / cost; if (roi >= 0) { printf ("%d\n", roi); } return 0; }
```
@run

Rather than putting everything on one line, it is much more readable to break up
long lines so that each statement and declaration goes on its own line. After
inserting line breaks, the code will look like this:

``` c
#include <stdio.h>
int main(void) {
int revenue = 80;
int cost = 50;
int roi;
roi = (100 * (revenue - cost)) / cost;
if (roi >= 0) {
printf ("%d\n", roi);
}
return 0;
}
```
@run


#### Blank Lines

Blank lines should be used to offset the main components of your code. Always
use them

* After preprocessor directives.
* After new variables are declared.
* Use your own judgment for finding other places where components should be
  separated.

Based on these two rules, there should now be at least two line breaks added.

* After line 1, because line 1 has a preprocessor directive.
* After line 5, because line 5 contains a variable declaration.

This will make the code much more readable than it was before:

The following lines of code have line breaks between functions, but without
indentation.

``` c
#include <stdio.h>

int main(void) {

int revenue = 80;
int cost = 50;

int roi;

roi = (100 * (revenue - cost)) / cost;

if (roi >= 0) {
printf ("%d\n", roi);
}

return 0;
}
```
@run

But it's still not as readable as it can be.


#### Indentation

Although adding simple line breaks between key blocks of code can make code
easier to read, it provides no information about the block structure of the
program. Using the tab key can be very helpful. Indentation visually separates
paths of execution by moving their starting points to a new column. This simple
practice will make it much easier to read and understand code. Indentation
follows a fairly simple rule:

* All code inside a new block should be indented by one tab[^1] more than the
  code in the previous path.

Based on the code from the previous section, there are two blocks requiring
indentation:

* Lines 4 to 16
* Line 13

``` c
#include <stdio.h>

int main(void) {

  int revenue = 80;

  int cost = 50;

  int roi;

  roi = (100 * (revenue - cost)) / cost;

  if (roi >= 0) {
    printf ("%d\n", roi);
  }

  return 0;
}
```
@run

It is now fairly obvious as to which parts of the program fit inside which
blocks. You can tell which parts of the program the coder has intended to be
conditional, and which ones he or she has not. Although it might not be
immediately noticeable, once many nested paths get added to the structure of the
program, the use of indentation can be very important. Thus, indentation makes
the structure of your program clear.

It is claimed that research has shown that an indentation size between 2 to 4
characters is easier to read than 8 character indents[^2]. However, an indent of
8 characters may still be in use for some systems[^3].

> Many text editors automatically indent appropriately when you hit the
> enter/return key.


[^1]: Several programmers recommend "use spaces for indentation. Do not use tabs
      in your code. You should set your editor to emit spaces when you hit the
      tab key."
      \[[1](http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml)\]
      \[[2](http://www.jwz.org/doc/tabs-vs-spaces.html)\] Other programmers
      disagree.
      \[[3](http://web.archive.org/20080118165124/diagrammes-modernes.blogspot.com/2006/04/tab-versus-spaces.html)\]
      \[[4](http://www.derkarl.org/why_to_tabs.html)\] Regardless of whether you
      prefer spaces or tabs, make sure you keep it consistent within the
      projects you are working on. Mixing tabs and spaces can cause code to
      become unreadable.

[^2]: http://www.oualline.com/vim/vim-cook.html#drawing Vim cookbook

[^3]: https://www.kernel.org/doc/html/latest/process/coding-style.html
      Linux Kernel Coding Style


### Comments

Comments in code can be useful for a variety of purposes. They provide the
easiest way to set off specific parts of code (and their purpose); as well as
providing a visual "split" between various parts of your code. Having good
comments throughout your code will make it much easier to remember what specific
parts of your code do.

Comments in modern flavors of C (and many other languages) can come in two
forms:

``` c
//Single Line Comments  (added by C99 standard, famously known as c++ style of comments)
```

and

``` c
/*Multi-Line
Comments
(only form of comments supported by C89 standard)*/
```

Note that Single line comments are a more recent addition to C, so some
compilers may not support them. A recent version of
[GCC](https://en.wikipedia.org/wiki/GNU_Compiler_Collection) will have no
problems supporting them.

This section is going to focus on the various uses of each form of commentary.

#### Single-line Comments

Single-line comments are most useful for simple 'side' notes that explain what
certain parts of the code do. The best places to put these comments are next to
variable declarations, and next to pieces of code that may need explanation.
Comments should make clear the intention and ideas behind the corresponding
code. What is immediately obvious from reading the code does not belong in a
comment.

Based on our previous program, there are various good places to place comments

* Line 5 and/or 6, to explain what `int revenue` and `int cost` represent,
* Line 8, to explain what the variable `roi` is going to be used for,
* Line 10, to explain the idea of the calculation,
* Line 12, to explain the purpose of the `if`.

This will make our program look something like

``` c
#include <stdio.h>

int main(void) {

  int revenue = 80;               // as of 2016
  int cost = 50;

  int roi;                        // return on investment in percent

  roi = (100 * (revenue - cost)) / cost;  // formula from accounting book

  if (roi >= 0) {                 // we don't care about negative roi
    printf ("%d\n", roi);
  }

  return 0;
}
```
@run


#### Multi-line Comments

> Single-line comments are a new feature, so many C programmers only use
> multi-line comments.

Multi-line comments are most useful for long explanations of code. They can be
used as copyright/licensing notices, and they can also be used to explain the
purpose of a block of code. This can be useful for two reasons: They make your
functions easier to understand, and they make it easier to spot errors in code.
If you know what a block is supposed to do, then it is much easier to find the
piece of code that is responsible if an error occurs.

As an example, suppose we had a program that was designed to print "Hello,
World!" a certain number of lines, a specified number of times. There would be
many for loops in this program. For this example, we shall call the number of
lines i, and the number of strings per line as j.

A good example of a multi-line comment that describes `for` loop `i`'s purpose
would be:

``` c
/* For Loop (int i)
   Loops the following procedure i times (for number of lines).  Performs 'for' loop j on each loop,
   and prints a new line at end of each loop.
*/
```

This provides a good explanation of what i's purpose is, whilst not going into
detail of what j does. By going into detail over what the specific path does
(and not ones inside it), it will be easier to troubleshoot the path.

Similarly, you should always include a multi-line comment before each function,
to explain the role, preconditions and postconditions of each function. Always
leave the technical details to the individual blocks inside your program - this
makes it easier to troubleshoot.

A function descriptor should look something like:

``` c
/* Function : int hworld (int i,int j)
   Input    : int i (Number of lines), int j (Number of instances per line)
   Output   : 0 (on success)
   Procedure: Prints "Hello, World!" j times, and a new line to standard output over i lines.
 */
```

This system allows for an at-a-glance explanation of what the function should
do. You can then go into detail over how each aspect of the program is achieved
later on in the program.

Finally, if you like to have aesthetically-pleasing source code, the multi-line
comment system allows for the easy addition of comment boxes. These make the
comments stand out much more than they would without otherwise. They look like
this.

``` c
/***************************************
 *  This is a multi line comment
 *  That is nearly surrounded by a
 *  Cool, starry border!
 ***************************************/
```

Applied to our original program, we can now include a much more descriptive and
readable source code:

``` c
#include <stdio.h>

int main(void){
  /************************************************************************************
   * Function: int main(void)
   * Input   : none
   * Output  : Returns 0 on success
   * Procedure: Prints 2016's return on investment in percent if it is not negative.
   ************************************************************************************/
  int revenue = 80;               // as of 2016
  int cost = 50;

  int roi;                        // return on investment in percent

  roi = (100 * (revenue - cost)) / cost;  // formula from accounting book

  if (roi >= 0) {                 // we don't care about negative roi
    printf ("%d\n", roi);
  }

  return 0;
}
```
@run

This will allow any outside users of the program an easy way to comprehend what
the code functions are and how they operate. It also inhibits uncertainty with
other like-named functions.

A few programmers add a column of stars on the right side of a block comment:

``` c
/***************************************
 *  This is a multi line comment       *
 *  that is completely surrounded by a *
 *  cool, starry border!               *
 ***************************************/
```

But most programmers don't put any stars on the right side of a block comment.
They feel that aligning the right side is a waste of time.

Comments written in source files can be used for documenting source code
automatically by using popular tools like Doxygen.[^4][^5]

[^4]: ["Coding Conventions for C++ and Java"](http://www.macadamian.com/index.php?option=com_content&task=view&id=34&Itemid=37)
      "all the block comments illustrated in this document have no pretty stars
      on the right side of the block comment. This deliberate choice was made
      because aligning those pretty stars is a large waste of time and
      discourages the maintenance of in-line comments.",

[^5]: [c2:BigBlocksOfAsterisks](http://c2.com/cgi/wiki?BigBlocksOfAsterisks),
      ["Code craft"](http://books.google.com/books?id=i4zCzpkrt4sC&pg=PA82&lpg=PA82&dq=programming+comment+block+waste+time+lining+up&source=bl&ots=TUpTMIHBnh&sig=NeZm23WPmvnw2aKMnIRUeQoHmJg&hl=en&ei=pri3SevGIYGyNMn9jd4K&sa=X&oi=book_result&resnum=8&ct=result)
      by Pete Goodliffe page 82,
      [Falvotech "C Programming Style Guide"](http://www.falvotech.com/content/publications/conventions/c/),
      [Fedora Directory Server Coding Style](http://directory.fedoraproject.org/wiki/Coding_Style)


## Variables

Like most programming languages, C is able to use and process named variables
and their contents. __Variables__ are simply names used to refer to some
location in memory – a location that holds a value with which we are working.

It may help to think of variables as a placeholder for a value. You can think of
a variable as being equivalent to its assigned value. So, if you have a variable
i that is __initialized__ (set equal) to 4, then it follows that _i + 1_ will
equal 5.

Since C is a relatively low-level programming language, before a C program can
utilize memory to store a variable it must claim the memory needed to store the
values for a variable. This is done by __declaring__ variables. Declaring
variables is the way in which a C program shows the number of variables it
needs, what they are going to be named, and how much memory they will need.

Within the C programming language, when managing and working with variables, it
is important to know the _type_ of variables and the _size_ of these types. A
type’s size is the amount of computer memory required to store one value of this
type. Since C is a fairly low-level programming language, the size of types can
be specific to the hardware and compiler used – that is, how the language is
made to work on one type of machine can be different from how it is made to work
on another.

All variables in C are __typed__. That is, every variable declared must be
assigned as a certain type of variable.

### Declaring, Initializing, and Assigning Variables

Here is an example of declaring an integer, which we've called `some_number`.
(Note the semicolon at the end of the line; that is how your compiler separates
one program _statement_ from another.)

``` c
int some_number;
```

This statement means we're declaring some space for a variable called
`some_number`, which will be used to store integer data. Note that we must
specify the type of data that a variable will store. There are specific keywords
to do this – we'll look at them in the next section.

Multiple variables can be declared with one statement, like this:

``` c
int anumber, anothernumber, yetanothernumber;
```

We can also declare _and_ assign some content to a variable at the same time.

``` c
int some_number = 3;
```

This is called initialization.

In early versions of C, variables had to be declared at the beginning of a
block. In C99 it is allowed to mix declarations and statements arbitrarily – but
doing so is not usual, because it is rarely necessary, some compilers still
don’t support C99 (portability), and it may, because it is uncommon yet,
irritate fellow programmers (maintainability).

After declaring variables, you can assign a value to a variable later on using a
statement like this:

``` c
some_number = 3;
```

You can also assign a variable the value of another variable, like so:

``` c
anumber = anothernumber;
```

Or assign multiple variables the same value with one statement:

``` c
anumber = anothernumber = yetanothernumber = 3;
```

This is because the assignment `x = y` returns the value of the assignment, `y`.
For example, `some_number = 3` returns 3. That said, `x = y = z` is really a
shorthand for `x = (y = z)`.

#### Naming Variables

Variable names in C are made up of letters (upper and lower case) and digits.
The underscore character ("\_") is also permitted. Names must not begin with a
digit. Unlike some languages (such as [Perl](https://en.wikipedia.org/wiki/Perl)
and some [BASIC](https://en.wikipedia.org/wiki/BASIC_programming_language)
dialects), C does not use any special prefix characters on variable names.

Some examples of valid (but not very descriptive) C variable names:

``` c
foo
Bar
BAZ
foo_bar
_foo42
_
QuUx
```

Some examples of invalid C variable names:

``` c
2foo    (must not begin with a digit)
my foo  (spaces not allowed in names)
$foo    ($ not allowed -- only letters, and _)
while   (language keywords cannot be used as names)
```

As the last example suggests, certain words are reserved as keywords in the
language, and these cannot be used as variable names.

It is not allowed to use the same name for multiple variables in the same
[scope](https://en.wikibooks.org/wiki/C_Programming/Preliminaries). When working
with other developers, you should therefore take steps to avoid using the same
name for global variables or function names. Some large projects adhere to
naming guidelines[^1] to avoid duplicate names and for consistency.

In addition there are certain sets of names that, while not language keywords,
are reserved for one reason or another. For example, a C compiler might use
certain names "behind the scenes", and this might cause problems for a program
that attempts to use them. Also, some names are reserved for possible future use
in the C standard library. The rules for determining exactly what names are
reserved (and in what contexts they are reserved) are too complicated to
describe here[citation needed], and as a beginner you don't need to worry about
them much anyway. For now, just avoid using names that begin with an underscore
character.

The naming rules for C variables also apply to naming other language constructs
such as function names, struct tags, and macros, all of which will be covered
later.

[^1]: Examples of naming guidelines are those of the
      [GNOME](https://developer.gnome.org/programming-guidelines/stable/namespacing.html)
      Project or the parts of the
      [Python interpreter](https://www.python.org/dev/peps/pep-0007/) that are
      written in C.


### Literals

Anytime within a program in which you specify a value explicitly instead of
referring to a variable or some other form of data, that value is referred to as
a __literal__. In the initialization example above, 3 is a literal. Literals can
either take a form defined by their type (more on that soon), or one can use
hexadecimal (hex) notation to directly insert data into a variable regardless of
its type.[citation needed] Hex numbers are always preceded with 0x. For now,
though, you probably shouldn't be too concerned with hex.


### The Four Basic Data Types

In Standard C there are four basic data types. They are `int`, `char`, `float`,
and `double`.


#### The `int` type

The `int` type stores integers in the form of "whole numbers". An integer is
typically the size of one machine word, which on most modern home PCs is 32 bits
(4 octets). Examples of literals are whole numbers (integers) such as 1, 2, 3,
10, 100... When `int` is 32 bits (4 octets), it can store any whole number
(integer) between -2147483648 and 2147483647. A 32 bit word (number) has the
possibility of representing any one number out of 4294967296 possibilities (2 to
the power of 32).


If you want to declare a new int variable, use the int keyword. For example:

``` c
int numberOfStudents, i, j=5;
```

In this declaration we declare 3 variables, `numberOfStudents`, `i` and `j`, `j`
here is assigned the literal 5.


#### The `char` type

The `char` type is capable of holding any member of the execution
[character set](https://en.wikipedia.org/wiki/Character_encoding#Character_sets.2C_maps_and_code_pages).
It stores the same kind of data as an `int` (i.e. integers), but typically has a
size of one byte. The size of a byte is specified by the macro `CHAR_BIT` which
specifies the number of bits in a `char` (byte). In standard C it never can be
less than 8 bits. A variable of type `char` is most often used to store
character data, hence its name. Most implementations use the ASCII character set
as the execution character set, but it's best not to know or care about that
unless the actual values are important.

Examples of character literals are 'a', 'b', '1', etc., as well as some special
characters such as '`\0`' (the null character) and '`\n`' (newline, recall
"Hello, World"). Note that the `char` value must be enclosed within single
quotations.

When we initialize a character variable, we can do it two ways. One is
preferred, the other way is __bad__ programming practice.

The first way is to write

``` c
char letter1 = 'a';
```

This is good programming practice in that it allows a person reading your code
to understand that letter1 is being initialized with the letter 'a' to start off
with.

The second way, which should not be used when you are coding letter characters,
is to write

``` c
char letter2 = 97; /* in ASCII, 97 = 'a' */
```

This is considered by some to be extremely ___bad___ practice, if we are using
it to store a character, not a small number, in that if someone reads your code,
most readers are forced to look up what character corresponds with the number 97
in the encoding scheme. In the end, `letter1` and `letter2` store both the same
thing – the letter 'a', but the first method is clearer, easier to debug, and
much more straightforward.

One important thing to mention is that characters for numerals are represented
differently from their corresponding number, i.e. '1' is not equal to 1. In
short, any single entry that is enclosed within 'single quotes'.

There is one more kind of literal that needs to be explained in connection with
chars: the __string literal__. A string is a series of characters, usually
intended to be displayed. They are surrounded by double quotations (" ", not ' ').
An example of a string literal is the "Hello, World!\n" in the "Hello, World"
example.

The string literal is assigned to a character `array`, arrays are described
later. Example:

const char MY_CONSTANT_PEDANTIC_ITCH[] = "learn the usage context.\n";

``` c
printf("Square brackets after a variable name means it is a pointer to a string of memory blocks the size of the type of the array element.\n");
```

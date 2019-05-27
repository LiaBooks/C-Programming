<!--
author:   André Dietrich

email:    andre.dietrich@ovgu.de

version:  0.0.2

language: en

narrator: US English Female

comment:  Try to write a short comment about
          your course, multiline is also okay.


@run:     @Rextester.C

-->

# C-Programming

import:   https://raw.githubusercontent.com/liaTemplates/rextester/master/README.md


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

``` c
const char MY_CONSTANT_PEDANTIC_ITCH[] = "learn the usage context.\n";
printf("Square brackets after a variable name means it is a pointer to a string of memory blocks the size of the type of the array element.\n");
```


#### The `float` type

`float` is short for __floating point__. It stores inexact representations of
real numbers, both integer and non-integer values. It can be used with numbers
that are much greater than the greatest possible `int`. `float` literals must be
suffixed with `F` or `f`. Examples are: `3.1415926f`, `4.0f`, `6.022e+23f`.

It is important to note that floating-point numbers are inexact. Some numbers
like `0.1f` cannot be represented exactly as `float`s but will have a small
error. Very large and very small numbers will have less precision and arithmetic
operations are sometimes not associative or distributive because of a lack of
precision. Nonetheless, floating-point numbers are most commonly used for
approximating real numbers and operations on them are efficient on modern
microprocessors.[^2]
[Floating-point arithmetic](https://en.wikipedia.org/wiki/Floating-point_arithmetic)
is explained in more detail on Wikipedia.

`float` variables can be declared using the `float` keyword. A `float` is only
one machine word in size. Therefore, it is used when less precision than a
`double` provides is required.

[^2]: Representations of real numbers other than floating-point numbers exist
      but are not fundamental data types in C. Some C compilers support
      [fixed-point arithmetic](https://en.wikipedia.org/wiki/Fixed-point_arithmetic)
      data types, but these are not part of standard C. Libraries such as the
      [GNU Multiple Precision Arithmetic Library](https://en.wikipedia.org/wiki/GNU_Multiple_Precision_Arithmetic_Library)
      offer more data types for real numbers and very large numbers.


#### The `double` type

The `double` and `float` types are very similar. The `float` type allows you to
store single-precision floating point numbers, while the `double` keyword allows
you to store double-precision floating point numbers – real numbers, in other
words. Its size is typically two machine words, or 8 bytes on most machines.
Examples of `double` literals are `3.1415926535897932`, `4.0`, `6.022e+23`
(scientific notation). If you use 4 instead of 4.0, the 4 will be interpreted as
an `int`.

The distinction between floats and doubles was made because of the differing
sizes of the two types. When C was first used, space was at a minimum and so the
judicious use of a `float` instead of a `double` saved some memory. Nowadays,
with memory more freely available, you rarely need to conserve memory like this –
it may be better to use doubles consistently. Indeed, some C implementations use
doubles instead of floats when you declare a `float` variable.

If you want to use a `double` variable, use the `double` keyword.


### `sizeof`

If you have any doubts as to the amount of memory actually used by any variable
(and this goes for types we'll discuss later, also), you can use the `sizeof`
operator to find out for sure. (For completeness, it is important to mention
that `sizeof` is a
[unary operator](https://en.wikipedia.org/wiki/Unary_operation), not a
function.) Its syntax is:

``` c
sizeof object
sizeof(type)
```

The two expressions above return the size of the object and type specified, in
bytes. The return type is `size_t` (defined in the header `<stddef.h>`) which is
an unsigned value. Here's an example usage:

``` c
size_t size;
int i;
size = sizeof(i);
```

size will be set to 4, assuming `CHAR_BIT` is defined as 8, and an integer is 32
bits wide. The value of `sizeof`'s result is the number of bytes.

Note that when `sizeof` is applied to a `char`, the result is 1; that is:

``` c
sizeof(char)
```

always returns 1.


### Data type modifiers

One can alter the data storage of any data type by preceding it with certain
modifiers.

long and short are modifiers that make it possible for a data type to use either
more or less memory. The int keyword need not follow the short and long
keywords. This is most commonly the case. A short can be used where the values
fall within a lesser range than that of an int, typically -32768 to 32767. A
long can be used to contain an extended range of values. It is not guaranteed
that a short uses less memory than an int, nor is it guaranteed that a long
takes up more memory than an int. It is only guaranteed that sizeof(short) <=
sizeof(int) <= sizeof(long). Typically a short is 2 bytes, an int is 4 bytes,
and a long either 4 or 8 bytes. Modern C compilers also provide long long which
is typically an 8 byte integer.

In all of the types described above, one bit is used to indicate the sign
(positive or negative) of a value. If you decide that a variable will never hold
a negative value, you may use the unsigned modifier to use that one bit for
storing other data, effectively doubling the range of values while mandating
that those values be positive. The unsigned specifier also may be used without a
trailing int, in which case the size defaults to that of an int. There is also a
signed modifier which is the opposite, but it is not necessary, except for
certain uses of char, and seldom used since all types (except char) are signed
by default.

The long modifier can also be used with double to create a long double type.
This floating-point type may (but is not required to) have greater precision
than the double type.

To use a modifier, just declare a variable with the data type and relevant modifiers:

``` c
unsigned short int usi;  /* fully qualified -- unsigned short int */
short si;                /* short int */
unsigned long uli;       /* unsigned long int */
```


### `const` qualifier

When the `const` qualifier is used, the declared variable must be initialized at
declaration. It is then not allowed to be changed.

While the idea of a variable that never changes may not seem useful, there are
good reasons to use `const`. For one thing, many compilers can perform some
small optimizations on data when it knows that data will never change. For
example, if you need the value of π in your calculations, you can declare a
`const` variable of pi, so a program or another function written by someone else
cannot change the value of pi.

Note that a Standard conforming compiler must issue a warning if an attempt is
made to change a `const` variable - but after doing so the compiler is free to
ignore the `const` qualifier.


### Magic numbers

When you write C programs, you may be tempted to write code that will depend on
certain numbers. For example, you may be writing a program for a grocery store.
This complex program has thousands upon thousands of lines of code. The
programmer decides to represent the cost of a can of corn, currently 99 cents,
as a literal throughout the code. Now, assume the cost of a can of corn changes
to 89 cents. The programmer must now go in and manually change each entry of 99
cents to 89. While this is not that big of a problem, considering the "global
find-replace" function of many text editors, consider another problem: the cost
of a can of green beans is also initially 99 cents. To reliably change the
price, you have to look at every occurrence of the number 99.

C possesses certain functionality to avoid this. This functionality is
approximately equivalent, though one method can be useful in one circumstance,
over another.


#### Using the `const` keyword

The `const` keyword helps eradicate __magic numbers__. By declaring a variable
`const` corn at the beginning of a block, a programmer can simply change that
`const` and not have to worry about setting the value elsewhere.

There is also another method for avoiding magic numbers. It is much more
flexible than `const`, and also much more problematic in many ways. It also
involves the preprocessor, as opposed to the compiler. Behold...


#### `#define`

When you write programs, you can create what is known as a macro, so when the
computer is reading your code, it will replace all instances of a word with the
specified expression.

Here's an example. If you write

``` c
#define PRICE_OF_CORN 0.99
```

when you want to, for example, print the price of corn, you use the word
`PRICE_OF_CORN` instead of the number 0.99 – the preprocessor will replace all
instances of `PRICE_OF_CORN` with 0.99, which the compiler will interpret as the
literal double 0.99. The preprocessor performs substitution, that is,
`PRICE_OF_CORN` is replaced by 0.99 so this means there is no need for a
semicolon.

It is important to note that `#define` has basically the same functionality as the
"find-and-replace" function in a lot of text editors/word processors.

For some purposes, `#define` can be harmfully used, and it is usually preferable
to use `const` if `#define` is unnecessary. It is possible, for instance, to
`#define`, say, a macro DOG as the number 3, but if you try to print the macro,
thinking that DOG represents a string that you can show on the screen, the
program will have an error. `#define` also has no regard for type. It disregards
the structure of your program, replacing the text everywhere (in effect,
disregarding scope), which could be advantageous in some circumstances, but can
be the source of problematic bugs.

You will see further instances of the `#define` directive later in the text. It
is good convention to write `#defined` words in all capitals, so a programmer
will know that this is not a variable that you have declared but a `#defined`
macro. It is not necessary to end a preprocessor directive such as `#define`
with a semicolon; in fact, some compilers may warn you about unnecessary tokens
in your code if you do.


### Scope

In the Basic Concepts section, the concept of scope was introduced. It is
important to revisit the distinction between local types and global types, and
how to declare variables of each. To declare a local variable, you place the
declaration at the beginning (i.e. before any non-declarative statements) of the
block to which the variable is deemed to be local. To declare a global variable,
declare the variable outside of any block. If a variable is global, it can be
read, and written, from anywhere in your program.

Global variables are not considered good programming practice, and should be
avoided whenever possible. They inhibit code readability, create naming
conflicts, waste memory, and can create difficult-to-trace bugs. Excessive usage
of globals is usually a sign of laziness or poor design. However, if there is a
situation where local variables may create more obtuse and unreadable code,
there's no shame in using globals.


### Other Modifiers

Included here, for completeness, are more of the modifiers that standard C
provides. For the beginning programmer, `static` and `extern` may be useful.
`volatile` is more of interest to advanced programmers. `register` and `auto`
are largely deprecated and are generally not of interest to either beginning or
advanced programmers.


#### static

`static` is sometimes a useful keyword. It is a common misbelief that the only
purpose is to make a variable stay in memory.

When you declare a function or global variable as static, you cannot access the
function or variable through the `extern` (see below) keyword from other files
in your project. This is called _static linkage_.

When you declare a local variable as static, it is created just like any other
variable. However, when the variable goes out of scope (i.e. the block it was
local to is finished) the variable stays in memory, retaining its value. The
variable stays in memory until the program ends. While this behaviour resembles
that of global variables, static variables still obey scope rules and therefore
cannot be accessed outside of their scope. This is called
_static storage duration_.

Variables declared static are initialized to zero (or for pointers,
`NULL`[^3][^4]) by default. They can be initialized explicitly on declaration to
any constant value. The initialization is made just once, at compile time.

You can use `static` in (at least) two different ways. Consider this code, and
imagine it is in a file called `jfile.c`:

``` c
#include <stdio.h>

static int j = 0;

void up(void)
{
  /* k is set to 0 when the program starts. The line is then "ignored"
   * for the rest of the program (i.e. k is not set to 0 every time up()
   * is called)
   */
  static int k = 0;
  j++;
  k++;
  printf("up() called.   k= %2d, j= %2d\n", k , j);
}

void down(void)
{
  static int k = 0;
  j--;
  k--;
  printf("down() called. k= %2d, j= %2d\n", k , j);
}

int main(void)
{
  int i;

  /* call the up function 3 times, then the down function 2 times */
  for (i = 0; i < 3; i++)
    up();
  for (i = 0; i < 2; i++)
    down();

  return 0;
}
```
@run

The `j` variable is accessible by both up and down and retains its value. The
`k` variables also retain their value, but they are two different variables, one
in each of their scopes. Static variables are a good way to implement
encapsulation, a term from the object-oriented way of thinking that effectively
means not allowing changes to be made to a variable except through function
calls.

Running the program above will produce the following output:

``` bash
up() called.   k=  1, j=  1
up() called.   k=  2, j=  2
up() called.   k=  3, j=  3
down() called. k= -1, j=  2
down() called. k= -2, j=  1
```

__Features of static variables:__

1. Keyword used        - `static`
2. Storage             - Memory
3. Default value       - Zero
4. Scope               - Local to the block in which it is declared
5. Lifetime            - Value persists between different function calls
6. Keyword optionality - Mandatory to use the keyword

[^3]: [\[1\]](http://c-faq.com/null/macro.html)
      - What is `NULL` and how is it defined?
[^4]: [\[2\]](http://c-faq.com/null/nullor0.html)
      - `NULL` or `0`, which should you use?


#### `extern`

`extern` is used when a file needs to access a variable in another file that it
may not have `#included` directly. Therefore, `extern` does not actually carve
out space for a new variable, it just provides the compiler with sufficient
information to access the remote variable.

__Features of extern variable:__

1. Keyword used        - extern
2. Storage             - Memory
3. Default value       - Zero
4. Scope               - Global (all over the program)
5. Lifetime            - Value persists till the program's execution comes to an end
6. Keyword optionality - Optional if declared outside all the functions


#### `volatile`

`volatile` is a special type of modifier which informs the compiler that the
value of the variable may be changed by external entities other than the program
itself. This is necessary for certain programs compiled with optimizations – if
a variable were not defined `volatile` then the compiler may assume that certain
operations involving the variable are safe to optimize away when in fact they
aren't. volatile is particularly relevant when working with embedded systems
(where a program may not have complete control of a variable) and multi-threaded
applications.


#### `auto`

`auto` is a modifier which specifies an "automatic" variable that is
automatically created when in scope and destroyed when out of scope. If you
think this sounds like pretty much what you've been doing all along when you
declare a variable, you're right: all declared items within a block are
implicitly "automatic". For this reason, the auto keyword is more like the
answer to a trivia question than a useful modifier, and there are lots of very
competent programmers that are unaware of its existence.

__Features of automatic variables:__

1. Keyword used        - `auto`
2. Storage             - Memory
3. Default value       - Garbage value (random value)
4. Scope               - Local to the block in which it is defined
5. Lifetime            - Value persists while the control remains within the block
6. Keyword optionality - Optional


#### `register`

`register` is a hint to the compiler to attempt to optimize the storage of the
given variable by storing it in a register of the computer's CPU when the
program is run. Most optimizing compilers do this anyway, so use of this keyword
is often unnecessary. In fact, ANSI C states that a compiler can ignore this
keyword if it so desires – and many do. Microsoft Visual C++ is an example of an
implementation that completely ignores the register keyword.

__Features of `register` variables:__

1. Keyword used        - `register`
2. Storage             - CPU registers (values can be retrieved faster than from memory)
3. Default value       - Garbage value
4. Scope               - Local to the block in which it is defined
5. Lifetime            - Value persists while the control remains within the block
6. Keyword optionality - Mandatory to use the keyword


### Concepts

* [Variables](https://en.wikibooks.org/wiki/Computer_Programming/Variables)
* [Types](https://en.wikibooks.org/wiki/Computer_Programming/Types)
* [Data Structures](https://en.wikibooks.org/wiki/Data_Structures)
* [Arrays](https://en.wikibooks.org/wiki/Data_Structures/Arrays)


### In this section

* C variables
  * [C arrays](https://en.wikibooks.org/wiki/C_Programming/Arrays)


## Simple input and output

When you take time to consider it, a computer would be pretty useless without
some way to talk to the people who use it. Just like we need information in
order to accomplish tasks, so do computers. And just as we supply information to
others so that they can do tasks, so do computers.

These supplies and returns of information to a computer are called __input__ and
__output__. 'Input' is information supplied to a computer or program. 'Output'
is information provided by a computer or program. Frequently, computer
programmers will lump the discussion in the more general term _input/output_ or
simply, __I/O__.

In C, there are many different ways for a program to communicate with the user.
Amazingly, the most simple methods usually taught to beginning programmers may
also be the most powerful. In the Hello, World! example at the beginning of this
text, we were introduced to a Standard Library file `stdio.h`, and one of its
functions, `printf()`. Here we discuss more of the functions that `stdio.h`
gives us.

### Output using `printf()`

Recall from the beginning of this text the demonstration program duplicated
below:

``` c
#include <stdio.h>

int main(void)
{
  printf("Hello, World!");
  return 0;
}
```
@run

If you compile and run this program, you will see the sentence below show up on
your screen:

``` bash
Hello, World!
```

This amazing accomplishment was achieved by using the function `printf()`. A
function is like a "black box" that does something for you without exposing the
internals inside. We can write functions ourselves in C, but we will cover that
later.

You have seen that to use `printf()` one puts text, surrounded by quotes, in
between the parentheses. We call the text surrounded by quotes a
__literal string__ (or just a string), and we call that string an argument to
`printf`.

As a note of explanation, it is sometimes convenient to include the open and
closing parentheses after a function name to remind us that it is, indeed, a
function. However usually when the name of the function we are talking about is
understood, it is not necessary.

As you can see in the example above, using `printf()` can be as simple as typing
in some text, surrounded by double quotes (note that these are double quotes and
not two single quotes). So, for example, you can print any string by placing it
as an argument to the printf() function:


```c
printf("This sentence will print out exactly as you see it...");
```

And once it is contained in a proper main() function, it will show:

``` bash
This sentence will print out exactly as you see it...
```


#### Printing numbers and escape sequences

##### Placeholder codes

The `printf()` function is a powerful function, and is probably the most-used
function in C programs.

For example, let us look at a problem. Say we want to calculate: 19 + 31. Let's
use C to get the answer.

We start writing

``` c
#include "stdio.h" // this is important, since printf
                   // can't be used without this header

int main(void)
{
  printf("19+31 is");
```

But here we are stuck! `printf()` only prints strings! Thankfully, `printf` has
methods for printing numbers. What we do is put a placeholder format code in the
string. We write:

``` c
printf("19+31 is '''%d'''", 19+31);
```

The placeholder `%d` literally "holds the place" for the actual number that is
the result of adding 19 to 31.

These placeholders are called format specifiers. Many other format specifiers
work with `printf()`. If we have a floating-point number, we can use `%f` to
print out a floating-point number, decimal point and all. Other format
specifiers are:

* `%d` - `int` (same as `%i`)
* `%ld` - `long int` (same as `%li`)
* `%f` - `float`
* `%lf` - `double`[^1]
* `%c` - `char`
* `%s` - `string`
* `%x` - hexadecimal

A complete listing of all the format specifiers for `printf()` is on Wikipedia.

[^1]: Actually `%f` prints doubles as well, but the use of %f for input is
      different. For more details, see the
      [Wikipedia article on C data types](https://en.wikipedia.org/wiki/C_data_types).


##### Tabs and newlines

What if, we want to achieve some output that will look like:

```
   1905
  312 +
  -----
```

`printf()` will not put line breaks in at the end of each statement: we must do
this ourselves. But how?

What we can do is use the newline __escape character__. An escape character is a
special character that we can write but will do something special onscreen, such
as make a beep, write a tab, and so on. To write a newline we write `\n`. All
escape characters start with a backslash.

So to achieve the output above, we write

``` c
printf(" 1905\n312 +\n-----\n");
```

or to be a bit more clear, we can break this long `printf` statement over
several lines. So our program will be

``` c
#include <stdio.h>

int main(void)
{
    printf(" 1905\n");
    printf("312 +\n");
    printf("-----\n");
    printf("%d", 1905+312);
    return 0;
}
```
@run

There are
[other escape characters](https://en.wikibooks.org/wiki/C_Programming/Strings#backslash_escapes)
we can use. Another common one is to use `\t` to write a tab. You can use `\a`
to ring the computer's bell, but you should not use this very much in your
programs, as excessive use of sound is not very friendly to the user.


### Other output methods

#### `puts()`

The `puts()` function is a very simple way to send a string to the screen when
you have no placeholders or variables to be concerned about. It works very much
like the `printf()` function we saw in the `"Hello, World!"` example:

``` c
puts("Print this string."");
```

will print to the screen:

``` bash
Print this string.
```

followed by the newline character (as discussed above). (The `puts` function
appends a newline character to its output.)


### Input using `scanf()`

The `scanf()` function is the input method equivalent to the `printf()` output
function - simple yet powerful. In its simplest invocation, the `scanf` format
string holds a single placeholder representing the type of value that will be
entered by the user. These placeholders are mostly the same as the `printf()`
function - `%d` for integers, `%f` for floats, and `%lf` for doubles.

There is, however, one variation to `scanf()` as compared to `printf()`. The
`scanf()` function requires the memory address of the variable to which you want
to save the input value. While _pointers_ (variables storing memory addresses)
can be used here, this is a concept that won't be approached until later in the
text. Instead, the simple technique is to use the __address-of__ operator, `&`.
For now it may be best to consider this "magic" before we discuss
[pointers](https://en.wikipedia.org/wiki/Pointer_%28computer_programming%29).

A typical application might be like this:

``` c
#include "stdio.h"

int main(void)
{
  int a;

  printf("Please input an integer value: ");
  scanf("%d", &a);
  printf("You entered: %d\n", a);

  return 0;
}
```
@run

If you were to describe the effect of the `scanf()` function call above, it might
read as: "Read in an integer from the user and store it at the address of
variable a ".

If you are trying to input a string using `scanf`, you should __not__ include
the `&` operator. The code below will produce a runtime error and the program
will likely crash.

``` c
scanf("%s", &a);
```

The correct usage would be:

``` c
scanf("%s", a);
```

This is because, whenever you use a format specifier for a string (`%s`), the
variable that you use to store the value will be an array and, the array names
(in this case - a) themselves point out to their base address and hence, the
__address of__ operator is not required.

(Although, this is vulnerable to
[Buffer overflow](https://en.wikipedia.org/wiki/Buffer_overflow). `fgets()` is
preferred to `scanf()`).

__Note on inputs:__ When data is typed at a keyboard, the information does not
go straight to the program that is running. It is first stored in what is known
as a __buffer__ - a small amount of memory reserved for the input source.
Sometimes there will be data left in the buffer when the program wants to read
from the input source, and the `scanf()` function will read this data instead of
waiting for the user to type something. Some may suggest you use the function
`fflush(stdin)`, which may work as desired on some computers, but isn't
considered good practice, as you will see later. Doing this has the downfall
that if you take your code to a different computer with a different compiler,
your code may not work properly.


## Operators and type casting


### Operators and Assignments

C has a wide range of operators that make simple math easy to handle. The list
of operators grouped into precedence levels is as follows:


#### Primary expressions

_Identifiers_ are names of things in C, and consist of either a letter or an
underscore ( `_` ) optionally followed by letters, digits, or underscores. An
identifier (or variable name) is a primary expression, provided that it has been
declared as designating an object (in which case it is an lvalue [a value that
can be used as the left side of an assignment expression]) or a function (in
which case it is a function designator).

A _constant_ is a primary expression. Its type depends on its form and value.
The types of constants are character constants (e.g. `' '` is a space), integer
constants (e.g. `2`), floating-point constants (e.g. `0.5`), and enumerated
constants that have been previously defined via `enum`.

A _string literal_ is a primary expression. It consists of a string of
characters within double quotes ( `"` ).

A parenthesized expression is a primary expression. It consists of an expression
within parentheses ( `( )` ). Its type and value are those of the
non-parenthesized expression within the parentheses.

In C11, an expression that starts with `_Generic` followed by (, an initial
_expression_, a list of values of the form type: expression where type is either
a named type or the keyword default, and ) constitute a primary expression. The
value is the expression that follows the type of the initial expression or the
default if not found.


#### Postfix operators

First, a primary expression is also a postfix expression. The following
expressions are also postfix expressions:

A postfix expression followed by a left square bracket (`[`), an expression, and
a right square bracket (`]`) in sequence constitutes an invocation of the
_array subscript_ operator. One of the expressions shall have type "pointer to
object type" and the other shall have an integer type; the result type is type.
Successive array subscript operators designate an element of a multidimensional
array.

A postfix expression followed by parentheses or an optional parenthesized
argument list indicates an invocation of the _function call_ operator. The value
of the function call operator is the return value of the function called with
the provided arguments. The parameters to the function are copied on the stack
__by value__ (or at least the compiler acts as if that is what happens; if the
programmer wanted the parameter to be copied by reference, then it is easier to
pass the address of the area to be modified by value, then the called function
can access the area through the respective pointer). The trend for compilers is
to pass the parameters from right to left onto the stack, but this is not
universal.

A postfix expression followed by a dot (`.`) followed by an identifier selects a
member from a structure or union; a postfix expression followed by an arrow (`->`)
followed by an identifier selects a member from a structure or union who is
pointed to by the pointer on the left-hand side of the expression.

A postfix expression followed by the increment or decrement operators (`++` or `--`
respectively) indicates that the variable is to be incremented or decremented as
a side effect. The value of the expression is the value of the postfix
expression before the increment or decrement. These operators only work on
integers and pointers.


#### Unary expressions

First, a postfix expression is a unary expression. The following expressions are
all unary expressions:

The increment or decrement operators followed by a unary expression is a unary
expression. The value of the expression is the value of the unary expression
_after_ the increment or decrement. These operators only work on integers and
pointers.

The following operators followed by a cast expression are unary expressions:

| Operator | Meaning                                              |
|:--------:|------------------------------------------------------|
|   `&`    | Address-of; value is the location of the operand     |
|   `*`    | Contents-of; value is what is stored at the location |
|   `-`    | Negation                                             |
|   `+`    | Value-of operator                                    |
|   `!`    | Logical negation ((`!E`) is equivalent to (`0==E`))  |
|   `~`    | Bit-wise complement                                  |

The keyword `sizeof` followed by a unary expression is a unary expression. The
value is the size of the type of the expression in bytes. The expression is not
evaluated.

The keyword `sizeof` followed by a parenthesized type name is a unary
expression. The value is the size of the type in bytes.


#### Cast operators

A cast expression is a unary expression.

A parenthesized type name followed by any expression, including literals, is a
cast expression. The parenthesized type name has the effect of forcing the cast
expression into the type specified by the type name in parentheses. For
arithmetic types, this either does not change the value of the expression, or
truncates the value of the expression if the expression is an integer and the
new type is smaller than the previous type.

An example of casting a float as an int:

``` c
float pi = 3.141592;
int truncated_pi = (int) pi; // truncated_pi == 3
```

An example of casting a char as an int:

```c
char my_char = 'A';
int my_int = (int) my_char; // On machines which use ASCII as the character set, my_int == 65
```


#### Multiplicative and additive operators

In C, simple math is very easy to handle. The following operators exist: `+`
(addition), `-` (subtraction), `*` (multiplication), / (division), and `%`
(modulus); You likely know all of them from your math classes - except, perhaps,
modulus. It returns the remainder of a division (e.g. `5 % 2 = 1`). (Modulus is
not defined for floating-point numbers, but the `math.h` library has an `fmod`
function.)

Care must be taken with the modulus, because it's not the equivalent of the
mathematical modulus: `(-5) % 2` is not `1`, but `-1`. Division of integers will
return an integer, and the division of a negative integer by a positive integer
will round towards zero instead of rounding down (e.g. `(-5) / 3 = -1` instead
of `-2`). However, it is always true that for all integer a and nonzero integer
`b`, `((a / b) * b) + (a % b) == a`.

There is no inline operator to do exponentiation (e.g. `5 ^ 2` is __not__ `25`
[it is `7`; `^` is the exclusive-or operator], and `5 ** 2` is an error), but
there is a power function.

The mathematical order of operations does apply. For example `(2 + 3) * 2 = 10`
while `2 + 3 * 2 = 8`. Multiplicative operators have precedence over additive
operators.

``` c
#include <stdio.h>

int main(void)
{
int i = 0, j = 0;

  // while i is less than 5 AND j is less than 5, loop
  while( (i < 5) && (j < 5) )
  {
    // postfix increment, i++
    //     the value of i is read and then incremented
    printf("i: %d\t", i++);

    // prefix increment, ++j
    //      the value of j is incremented and then read
    printf("j: %d\n", ++j);
  }

  printf("At the end they have both equal values:\ni: %d\tj: %d\n", i, j);

  getchar(); // pause
  return 0;
}
```
@run

will display the following:

``` bash
i: 0    j: 1
i: 1    j: 2
i: 2    j: 3
i: 3    j: 4
i: 4    j: 5
At the end they have both equal values:
i: 5    j: 5
```


#### The shift operators (which may be used to rotate bits)

Shift functions are often used in low-level I/O hardware interfacing. Shift and
rotate functions are heavily used in cryptography and software floating point
emulation. Other than that, shifts can be used in place of division or
multiplication by a power of two. Many processors have dedicated function blocks
to make these operations fast -- see
[Microprocessor Design/Shift and Rotate Blocks](https://en.wikibooks.org/wiki/X86_Assembly/Shift_and_Rotate).
On processors which have such blocks, most C compilers compile shift and rotate
operators to a single assembly-language instruction -- see
[X86 Assembly/Shift and Rotate](https://en.wikibooks.org/wiki/X86_Assembly/Shift_and_Rotate).


##### shift left

The `<<` operator shifts the binary representation to the left, dropping the
most significant bits and appending it with zero bits. The result is equivalent
to multiplying the integer by a power of two.


##### unsigned shift right

The unsigned shift right operator, also sometimes called the logical right shift
operator. It shifts the binary representation to the right, dropping the least
significant bits and prepending it with zeros. The `>>` operator is equivalent
to division by a power of two for unsigned integers.


##### signed shift right

The signed shift right operator, also sometimes called the arithmetic right
shift operator. It shifts the binary representation to the right, dropping the
least significant bit, but prepending it with copies of the original sign bit.
The `>>` operator is not equivalent to division for signed integers.

In C, the behavior of the `>>` operator depends on the data type it acts on.
Therefore, a signed and an unsigned right shift looks exactly the same, but
produces a different result in some cases.


##### rotate right

Contrary to popular belief, it is possible to write C code that compiles down to the "rotate" assembly language instruction (on CPUs that have such an instruction).

Most compilers recognize this idiom:

``` c
unsigned int x;
unsigned int y;
/* ... */
y = (x >> shift) | (x << (32 - shift));
```

and compile it to a single 32 bit rotate instruction. [^1] [^2]

On some systems, this may be `#define`ed as a macro or defined as an inline
function called something like `rightrotate32` or `rotr32` or `ror32` in a
standard header file like `bitops.h`. [^3]


[^1]: [GCC: "Optimize common rotate constructs"](http://gcc.gnu.org/ml/gcc-patches/2007-11/msg01112.html)

[^2]: ["Cleanups in ROTL/ROTR DAG combiner code"](http://www.mail-archive.com/llvm-commits@cs.uiuc.edu/msg17216.html)
      mentions that this code supports the "rotate" instruction in the CellSPU

[^3]: ["replace private copy of bit rotation routines"](http://archive.is/20130415063059/kerneltrap.org/mailarchive/linux-kernel/2008/4/15/1440064) --
      recommends including `"bitops.h"` and using its `rol32` and `ror32` rather
      than copy-and-paste into a new program.


##### rotate left

Most compilers recognize this idiom:

``` c
unsigned int x;
unsigned int y;
/* ... */
y = (x << shift) | (x >> (32 - shift));
```

and compile it to a single 32 bit rotate instruction.

On some systems, this may be `#define`ed as a macro or defined as an inline
function called something like `leftrotate32` or `rotl32` in a header file like
`"bitops.h"`.


#### Relational and equality operators

The relational binary operators `<` (less than), `>` (greater than), `<=` (less
than or equal), and `>=` (greater than or equal) operators return a value of 1
if the result of the operation is true, 0 if false.

The equality binary operators `==` (equals) and `!=` (not equals) operators are
similar to the relational operators except that their precedence is lower.


#### Bitwise operators

The bitwise operators are `&` (and), `^` (exclusive or) and `|` (inclusive or).
The `&` operator has higher precedence than `^`, which has higher precedence
than `|`.

The values being operated upon must be integral; the result is integral.

One use for the bitwise operators is to emulate bit flags. These flags can be
set with OR, tested with AND, flipped with XOR, and cleared with AND NOT. For
example:

``` c
/* This code is a sample for bitwise operations.  */
#define BITFLAG1    (1)
#define BITFLAG2    (2)
#define BITFLAG3    (4) /* They are powers of 2 */

unsigned bitbucket = 0U;    /* Clear all */
bitbucket |= BITFLAG1;      /* Set bit flag 1 */
bitbucket &= ~BITFLAG2;     /* Clear bit flag 2 */
bitbucket ^= BITFLAG3;      /* Flip the state of bit flag 3 from off to on or
                               vice versa */
if (bitbucket & BITFLAG3) {
  // bit flag 3 is set
} else {
  // bit flag 3 is not set
}
```


#### Logical operators

The logical operators are `&&` (and), and `||` (or). Both of these operators
produce 1 if the relationship is true and 0 for false. Both of these operators
short-circuit; if the result of the expression can be determined from the first
operand, the second is ignored. The && operator has higher precedence than the `||`
operator.

`&&` is used to evaluate expressions left to right, and returns a 1 if both
statements are true, 0 if either of them are false. If the first expression is
false, the second is not evaluated.

``` c
int x = 7;
int y = 5;
if(x == 7 && y == 5) {
  ...
}
```

Here, the `&&` operator checks the left-most expression, then the expression to
its right. If there were more than two expressions chained (e.g. `x && y && z`),
the operator would check `x` first, then `y` (if `x` is nonzero), then continue
rightwards to `z` if neither `x` or `y` is zero. Since both statements return
true, the `&&` operator returns true, and the code block is executed.

``` c
if(x == 5 && y == 5) {
  ...
}
```

The && operator checks in the same way as before, and finds that the first
expression is false. The `&&` operator stops evaluating as soon as it finds a
statement to be false, and returns a false.


`||` is used to evaluate expressions left to right, and returns a 1 if either of
the expressions are true, 0 if both are false. If the first expression is true,
the second expression is not evaluated.

``` c
/* Use the same variables as before. */
if(x == 2 || y == 5) { // the || statement checks both expressions, finds that the latter is true, and returns true
  ...
}
```

The `||` operator here checks the left-most expression, finds it false, but
continues to evaluate the next expression. It finds that the next expression
returns true, stops, and returns a 1. Much how the `&&` operator ceases when it
finds an expression that returns false, the `||` operator ceases when it finds
an expression that returns true.

It is worth noting that C does not have Boolean values (true and false) commonly
found in other languages. It instead interprets a 0 as false, and any nonzero
value as true.


#### Conditional operators

The ternary ?: operator is the conditional operator. The expression (`x ? y : z`)
has the value of `y` if `x` is nonzero, `z` otherwise.

Example:

``` c
int x = 0;
int y;
y = (x ? 10 : 6); /* The parentheses are technically not necessary as assignment
                     has a lower precedence than the conditional operator, but
                     it's there for clarity.  */
```

The expression x evaluates to 0. The ternary operator then looks for the
"if-false" value, which in this case, is 6. It returns that, so `y` is equal to
six. Had `x` been a non-zero, then the expression would have returned a 10.


#### Assignment operators

The assignment operators are `=`, `*=`, `/=`, `%=`, `+=`, `-=`, `<<=`, `>>=`, `&=`, `^=`,
and `|=`. The `=` operator stores the value of the right operand into the
location determined by the left operand, which must be an
[lvalue](https://en.wikibooks.org/w/index.php?title=Lvalue&action=edit&redlink=1)
(a value that has an address, and therefore can be assigned to).

For the others, `x op= y` is shorthand for `x = x op (y)`. Hence, the following
expressions are the same:

1. `x += y`     -->     `x = x+y`
2. `x -= y`     -->     `x = x-y`
3. `x *= y`     -->     `x = x*y`
4. `x /= y`     -->     `x = x/y`
5. `x %= y`     -->     `x = x%y`

The value of the assignment expression is the value of the left operand after
the assignment. Thus, assignments can be chained; e.g. the expression
`a = b = c = 0;` would assign the value zero to all three variables.


#### Comma operator

The operator with the least precedence is the comma operator. The value of the
expression `x`, `y` will evaluate both `x` and `y`, but provides the value of `y`.

This operator is useful for including multiple actions in one statement (e.g.
within a for loop conditional).

Here is a small example of the comma operator:

``` c
int i, x;      /* Declares two ints, i and x, in one declaration.
                  Technically, this is not the comma operator. */

/* this loop initializes x and i to 0, then runs the loop */
for (x = 0, i = 0; i <= 6; i++) {
  printf("x = %d, and i = %d\n", x, i);
}
```


## Arrays and strings

Arrays in C act to store related data under a single variable name with an
index, also known as a subscript. It is easiest to think of an array as simply a
list or ordered grouping for variables of the same type. As such, arrays often
help a programmer organize collections of data efficiently and intuitively.

Later we will consider the concept of a pointer, fundamental to C, which extends
the nature of the array (array can be termed as a constant pointer). For now, we
will consider just their declaration and their use.

### Arrays

C arrays are declared in the following form:

``` c
type name[number of elements];
```

For example, if we want an array of six integers (or whole numbers), we write in
C:

``` c
int numbers[6];
```

For a six character array called letters,

``` c
char letters[6];
```

and so on.

You can also initialize as you declare. Just put the initial elements in curly
brackets separated by commas as the initial value:

``` c
type name[number of elements]={comma-separated values}
```

For example, if we want to initialize an array with six integers, with 0, 0, 1,
0, 0, 0 as the initial values:

``` c
int point[6]={0,0,1,0,0,0};
```

Though when the array is initialized as in this case, the array dimension may be
omitted, and the array will be automatically sized to hold the initial data:

``` c
int point[]={0,0,1,0,0,0};
```

This is very useful in that the size of the array can be controlled by simply
adding or removing initializer elements from the definition without the need to
adjust the dimension.

If the dimension is specified, but not all elements in the array are
initialized, the remaining elements will contain a value of 0. This is very
useful, especially when we have very large arrays.

``` c
int numbers[2000]={245};
```

The above example sets the first value of the array to 245, and the rest to 0.

If we want to access a variable stored in an array, for example with the above
declaration, the following code will store a 1 in the variable `x`

``` c
int x;
x = point[2];
```

Arrays in C are indexed starting at 0, as opposed to starting at 1. The first
element of the array above is `point[0]`. The index to the last value in the array
is the array size minus one. In the example above the subscripts run from 0
through 5. C does not guarantee bounds checking on array accesses. The compiler
may not complain about the following (though the best compilers do):

``` c
char y;
int z = 9;
char point[6] = { 1, 2, 3, 4, 5, 6 };
//examples of accessing outside the array. A compile error is not always raised
y = point[15];
y = point[-4];
y = point[z];
```

During program execution, an out of bounds array access does not always cause a
run time error. Your program may happily continue after retrieving a value from
`point[-1]`. To alleviate indexing problems, the `sizeof()` expression is
commonly used when coding loops that process arrays.

Many people use a macro that in turn uses `sizeof()` to find the number of
elements in an array, a macro variously named "`lengthof()`",[^1]
"`MY_ARRAY_SIZE()`" or "`NUM_ELEM()`",[^2] "`SIZEOF_STATIC_ARRAY()`",[^3] etc.

``` c
int ix;
short anArray[]= { 3, 6, 9, 12, 15 };

for (ix=0; ix< (sizeof(anArray)/sizeof(short)); ++ix) {
  DoSomethingWith("%d", anArray[ix] );
}
```

Notice in the above example, the size of the array was not explicitly specified.
The compiler knows to size it at 5 because of the five values in the initializer
list. Adding an additional value to the list will cause it to be sized to six,
and because of the sizeof expression in the for loop, the code automatically
adjusts to this change. Good programming practice is to declare a variable
_size_, and store the number of elements in the array in it.

``` c
size = sizeof(anArray)/sizeof(short)
```

C also supports multi dimensional arrays (or, rather, arrays of arrays). The
simplest type is a two dimensional array. This creates a rectangular array -
each row has the same number of columns. To get a char array with 3 rows and 5
columns we write in C

``` c
char two_d[3][5];
```

To access/modify a value in this array we need two subscripts:

``` c
char ch;
ch = two_d[2][4];
```

or

``` c
two_d[0][0] = 'x';
```

Similarly, a multi-dimensional array can be initialized like this:

``` c
int two_d[2][3] = {{ 5, 2, 1 },
                   { 6, 7, 8 }};
```

The amount of columns must be explicitly stated; however, the compiler will find
the appropriate amount of rows based on the initializer list.

There are also weird notations possible:

``` c
int a[100];
int i = 0;
if (a[i]==i[a])
{
  printf("Hello world!\n");
}
```

`a[i]` and `i[a]` refer to the same location. (This is explained later in the
next Chapter.)

[^1]: Pádraig Brady.
      ["C and C++ notes"](http://www.pixelbeat.org/programming/gcc/c_c++_notes.html).

[^2]: [C Programming/Pointers and arrays](https://en.wikibooks.org/wiki/C_Programming/Pointers_and_arrays)

[^3]: [MINC/Reference/MINC1-volumeio-programmers-reference](https://en.wikibooks.org/wiki/MINC/Reference/MINC1-volumeio-programmers-reference)

### Strings

C has no string handling facilities built in; consequently, strings are defined
as arrays of characters. C allows a character array to be represented by a
character string rather than a list of characters, with the null terminating
character automatically added to the end. For example, to store the string
"Merkkijono", we would write

``` c
char string[11] = "Merkkijono";
```

or

``` c
char string[11] = {'M', 'e', 'r', 'k', 'k', 'i', 'j', 'o', 'n', 'o', '\0'};
```

> String "Merkkijono" stored in memory
>
> ``````````
>   0   1   2   3   4   5   6   7   8   9   10
> +---+---+---+---+---+---+---+---+---+---+----+
> | M | e | r | k | k | i | j | o | n | o | \0 |
> +---+---+---+---+---+---+---+---+---+---+----+
> ``````````

In the first example, the string will have a null character automatically
appended to the end by the compiler; by convention, library functions expect
strings to be terminated by a null character. The latter declaration indicates
individual elements, and as such the null terminator needs to be added manually.

Strings do not always have to be linked to an explicit variable. As you have
seen already, a string of characters can be created directly as an unnamed
string that is used directly (as with the `printf` functions.)

To create an extra long string, you will have to split the string into multiple
sections, by closing the first section with a quote, and recommencing the string
on the next line (also starting and ending in a quote):

``` c
char string[58] = "This is a very, very long "
                "string that requires two lines.";
```

While strings may also span multiple lines by putting the backslash character at
the end of the line, this method is deprecated.

There is a useful library of string handling routines which you can use by
including another header file.

``` c
#include <string.h>  //new header file
```

This standard string library will allow various tasks to be performed on
strings, and is discussed in the Strings chapter.


## Program flow control

Very few programs follow exactly one control path and have each instruction
stated explicitly. In order to program effectively, it is necessary to
understand how one can alter the steps taken by a program due to user input or
other conditions, how some steps can be executed many times with few lines of
code, and how programs can appear to demonstrate a rudimentary grasp of logic. C
constructs known as conditionals and loops grant this power.

From this point forward, it is necessary to understand what is usually meant by
the word block. A block is a group of code statements that are associated and
intended to be executed as a unit. In C, the beginning of a block of code is
denoted with `{` (left curly), and the end of a block is denoted with `}`. It is
not necessary to place a semicolon after the end of a block. Blocks can be
empty, as in `{}`. Blocks can also be nested; i.e. there can be blocks of code
within larger blocks.


### Conditionals

There is likely no meaningful program written in which a computer does not
demonstrate basic decision-making skills. It can actually be argued that there
is no meaningful human activity in which some sort of decision-making,
instinctual or otherwise, does not take place. For example, when driving a car
and approaching a traffic light, one does not think, "I will continue driving
through the intersection." Rather, one thinks, "I will stop if the light is red,
go if the light is green, and if yellow go only if I am traveling at a certain
speed a certain distance from the intersection." These kinds of processes can be
simulated in C using conditionals.

A conditional is a statement that instructs the computer to execute a certain
block of code or alter certain data only if a specific condition has been met.
The most common conditional is the If-Else statement, with conditional
expressions and Switch-Case statements typically used as more shorthanded
methods.

Before one can understand conditional statements, it is first necessary to
understand how C expresses logical relations. C treats logic as being
arithmetic. The value 0 (zero) represents false, and ___all other values___
represent true. If you chose some particular value to represent true and then
compare values against it, sooner or later your code will fail when your assumed
value (often 1) turns out to be incorrect. Code written by people uncomfortable
with the C language can often be identified by the usage of `#define` to make a
"TRUE" value. [^1]

Because logic is arithmetic in C, arithmetic operators and logical operators are
one and the same. Nevertheless, there are a number of operators that are
typically associated with logic:

[^1]: [C FAQ](http://www.c-faq.com/bool/bool2.html)


#### Relational and Equivalence Expressions

|Expression| Explained                                              |
|:--------:|--------------------------------------------------------|
| `a < b`  | 1 if `a` is less than `b`, 0 otherwise.                |
| `a > b`  | 1 if `a` is greater than `b`, 0 otherwise.             |
| `a <= b` | 1 if `a` is less than or equal to `b`, 0 otherwise.    |
| `a >= b` | 1 if `a` is greater than or equal to `b`, 0 otherwise. |
| `a == b` | 1 if `a` is equal to `b`, 0 otherwise.                 |
| `a != b` | 1 if `a` is not equal to `b`, 0 otherwise.             |

New programmers should take special note of the fact that the "equal to"
operator is `==,` not `=`. This is the cause of numerous coding mistakes and is
often a difficult-to-find bug, as the expression (`a = b`) sets a equal to b and
subsequently evaluates to b; but the expression (`a == b`), which is usually
intended, checks if a is equal to b. It needs to be pointed out that, if you
confuse `=` with `==`, your mistake will often not be brought to your attention
by the compiler. A statement such as `if (c = 20) {}` is considered perfectly
valid by the language, but will always assign 20 to c and evaluate as true. A
simple technique to avoid this kind of bug (in many, not all cases) is to put
the constant first. This will cause the compiler to issue an error, if `==` got
misspelled with `=`.

Note that C does not have a dedicated boolean type as many other languages do. 0
means false and anything else true. So the following are equivalent:

``` c
if (foo()) {
  // do something
}
``` c

and

``` c
if (foo() != 0) {
  // do something
}
```

Often `#define TRUE 1` and `#define FALSE 0` are used to work around the lack of
a boolean type. This is bad practice, since it makes assumptions that do not
hold. It is a better idea to indicate what you are actually expecting as a
result from a function call, as there are many different ways of indicating
error conditions, depending on the situation.

``` c
if (strstr("foo", bar) >= 0) {
  // bar contains "foo"
}
```

Here, `strstr` returns the index where the substring foo is found and -1 if it
was not found. Note that this would fail with the TRUE definition mentioned in
the previous paragraph. It would also not produce the expected results if we
omitted the `>= 0`.

One other thing to note is that the relational expressions do not evaluate as
they would in mathematical texts. That is, an expression `myMin < value < myMax`
does not evaluate as you probably think it might. Mathematically, this would
test whether or not value is between `myMin` and `myMax`. But in C, what happens
is that value is first compared with `myMin`. This produces either a 0 or a 1.
It is this value that is compared against `myMax`. Example:

``` c
int value = 20;
/* ... */
if (0 < value < 10) { // don't do this! it always evaluates to "true"!
  // do some stuff ...
}
```

Because value is greater than 0, the first comparison produces a `value` of 1.
Now 1 is compared to be less than 10, which is true, so the statements in the if
are executed. This probably is not what the programmer expected. The appropriate
code would be

``` c
int value = 20;
/* ... */
if (0 < value && value < 10) {   // the && means "and"
  // do some stuff ...
}
```


#### Logical Expressions

|Expression| Explained                                              |
|:--------:|--------------------------------------------------------|
| `a||b` | when EITHER `a` or `b` is true (or both), the result is 1, otherwise the result is 0. |
| `a&&b` | when BOTH `a` and `b` are true, the result is 1, otherwise the result is 0. |
|  `!a`  | when `a` is true, the result is 0, when `a` is 0, the result is 1. |


Here's an example of a larger logical expression. In the statement:

``` c
  e = ((a && b) || (c > d));
```

`e` is set equal to 1 if `a` and `b` are non-zero, or if `c` is greater than
`d`. In all other cases, `e` is set to 0.

C uses short circuit evaluation of logical expressions. That is to say, once it
is able to determine the truth of a logical expression, it does no further
evaluation. This is often useful as in the following:

``` c
int myArray[12];
....
if (i < 12 && myArray[i] > 3) {
....
```

In the snippet of code, the comparison of `i` with 12 is done first. If it
evaluates to 0 (false), `i` would be out of bounds as an index to `myArray`. In
this case, the program never attempts to access `myArray[i]` since the truth of
the expression is known to be false. Hence we need not worry here about trying
to access an out-of-bounds array element if it is already known that i is
greater than or equal to zero. A similar thing happens with expressions
involving the or `||` operator.

``` c
while (doThis() || doThat()) ...
```

`doThat()` is never called if `doThis()` returns a non-zero (true) value.


#### The If-Else statement

If-Else provides a way to instruct the computer to execute a block of code only
if certain conditions have been met. The syntax of an If-Else construct is:

``` c
if (/* condition goes here */) {
  /* if the condition is non-zero (true), this code will execute */
} else {
  /* if the condition is 0 (false), this code will execute */
}
```

The first block of code executes if the condition in parentheses directly after
the if evaluates to non-zero (true); otherwise, the second block executes.

The else and following block of code are completely optional. If there is no
need to execute code if a condition is not true, leave it out.

Also, keep in mind that an if can directly follow an else statement. While this
can occasionally be useful, chaining more than two or three if-elses in this
fashion is considered bad programming practice. We can get around this with the
Switch-Case construct described later.

Two other general syntax notes need to be made that you will also see in other
control constructs: First, note that there is no semicolon after if or else.
There could be, but the block (code enclosed in `{` and `}`) takes the place of
that. Second, if you only intend to execute one statement as a result of an if
or else, curly braces are not needed. However, many programmers believe that
inserting curly braces anyway in this case is good coding practice.

The following code sets `a` variable `c` equal to the greater of two variables
`a` and `b`, or 0 if `a` and `b` are equal.

``` c
if (a > b) {
  c = a;
} else if (b > a) {
  c = b;
} else {
  c = 0;
}
```

Consider this question: why can't you just forget about else and write the code
like:

``` c
 if (a > b) {
   c = a;
 }

 if (a < b) {
   c = b;
 }

 if (a == b) {
   c = 0;
 }
```

There are several answers to this. Most importantly, if your conditionals are
not mutually exclusive, two cases could execute instead of only one. If the code
was different and the value of `a` or `b` changes somehow (e.g.: you reset the
lesser of `a` and `b` to 0 after the comparison) during one of the blocks? You
could end up with multiple if statements being invoked, which is not your
intent. Also, evaluating if conditionals takes processor time. If you use else
to handle these situations, in the case above assuming (`a > b`) is non-zero
(true), the program is spared the expense of evaluating additional if
statements. The bottom line is that it is usually best to insert an else clause
for all cases in which a conditional will not evaluate to non-zero (true).


##### The conditional expression

A conditional expression is a way to set values conditionally in a more
shorthand fashion than If-Else. The syntax is:

``` c
(/* logical expression goes here */) ? (/* if non-zero (true) */) : (/* if 0 (false) */)
```

The logical expression is evaluated. If it is non-zero (true), the overall
conditional expression evaluates to the expression placed between the `?` and `:`,
otherwise, it evaluates to the expression after the `:`. Therefore, the above
example (changing its function slightly such that `c` is set to `b` when `a` and
`b` are equal) becomes:

``` c
c = (a > b) ? a : b;
```

Conditional expressions can sometimes clarify the intent of the code. Nesting
the conditional operator should usually be avoided. It's best to use conditional
expressions only when the expressions for a and b are simple. Also, contrary to
a common beginner belief, conditional expressions do not make for faster code.
As tempting as it is to assume that fewer lines of code result in faster
execution times, there is no such correlation.


#### The Switch-Case statement

Say you write a program where the user inputs a number 1-5 (corresponding to
student grades, A(represented as 1)-D(4) and F(5)), stores it in a variable
__grade__ and the program responds by printing to the screen the associated
letter grade. If you implemented this using If-Else, your code would look
something like this:

``` c
if (grade == 1) {
  printf("A\n");
} else if (grade == 2) {
  printf("B\n");
} else if /* etc. etc. */
```

Having a long chain of if-else-if-else-if-else can be a pain, both for the
programmer and anyone reading the code. Fortunately, there's a solution: the
Switch-Case construct, of which the basic syntax is:

``` c
switch (/* integer or enum goes here */) {
case /* potential value of the aforementioned int or enum */:
  /* code */
case /* a different potential value */:
  /* different code */
/* insert additional cases as needed */
default:
  /* more code */
}
```

The Switch-Case construct takes a variable, usually an int or an `enum`, placed
after switch, and compares it to the value following the case keyword. If the
variable is equal to the value specified after `case`, the construct
"activates", or begins executing the code after the case statement. Once the
construct has "activated", there will be no further evaluation of cases.

Switch-Case is syntactically "weird" in that no braces are required for code
associated with a case.

__Very important:__ Typically, the last statement for each `case` is a `break`
statement. This causes program execution to jump to the statement following the
closing bracket of the switch statement, which is what one would normally want
to happen. However if the break statement is omitted, program execution
continues with the first line of the next case, if any. This is called a
fall-through. When a programmer desires this action, a comment should be placed
at the end of the block of statements indicating the desire to fall through.
Otherwise another programmer maintaining the code could consider the omission of
the 'break' to be an error, and inadvertently 'correct' the problem. Here's an
example:

``` c
 switch (someVariable) {
 case 1:
   printf("This code handles case 1\n");
   break;
 case 2:
   printf("This prints when someVariable is 2, along with...\n");
   /* FALL THROUGH */
 case 3:
   printf("This prints when someVariable is either 2 or 3.\n" );
   break;
 }
```

If a default case is specified, the associated statements are executed if none
of the other cases match. A default case is optional. Here's a switch statement
that corresponds to the sequence of if - else if statements above.

Back to our example above. Here's what it would look like as Switch-Case:

``` c
switch (grade) {
case 1:
  printf("A\n");
  break;
case 2:
  printf("B\n");
  break;
case 3:
  printf("C\n");
  break;
case 4:
  printf("D\n");
  break;
default:
  printf("F\n");
  break;
}
```

A set of statements to execute can be grouped with more than one value of the
variable as in the following example. (the fall-through comment is not necessary
here because the intended behavior is obvious)

``` c
switch (something) {
case 2:
case 3:
case 4:
  /* some statements to execute for 2, 3 or 4 */
  break;
case 1:
default:
  /* some statements to execute for 1 or other than 2,3,and 4 */
  break;
}
```

Switch-Case constructs are particularly useful when used in conjunction with
user defined `enum` data types. Some compilers are capable of warning about an
unhandled `enum` value, which may be helpful for avoiding bugs.


### Loops

Often in computer programming, it is necessary to perform a certain action a
certain number of times or until a certain condition is met. It is impractical
and tedious to simply type a certain statement or group of statements a large
number of times, not to mention that this approach is too inflexible and
unintuitive to be counted on to stop when a certain event has happened. As a
real-world analogy, someone asks a dishwasher at a restaurant what he did all
night. He will respond, "I washed dishes all night long." He is not likely to
respond, "I washed a dish, then washed a dish, then washed a dish, then...". The
constructs that enable computers to perform certain repetitive tasks are called
loops.


#### While loops

A while loop is the most basic type of loop. It will run as long as the
condition is non-zero (true). For example, if you try the following, the program
will appear to lock up and you will have to manually close the program down. A
situation where the conditions for exiting the loop will never become true is
called an infinite loop.

``` c
int a = 1;
while (42) {
  a = a * 2;
}
```

Here is another example of a while loop. It prints out all the powers of two
less than 100.

``` c
int a = 1;
while (a < 100) {
  printf("a is %d \n", a);
  a = a * 2;
}
```

The flow of all loops can also be controlled by `break` and `continue` statements. A
`break` statement will immediately exit the enclosing loop. A `continue` statement
will skip the remainder of the block and start at the controlling conditional
statement again. For example:

``` c
int a = 1;
while (42) { // loops until the break statement in the loop is executed
  printf("a is %d ", a);
  a = a * 2;
  if (a > 100) {
    break;
  } else if (a == 64) {
    continue;  // Immediately restarts at while, skips next step
  }
  printf("a is not 64\n");
}
```

In this example, the computer prints the value of a as usual, and prints a
notice that a is not 64 (unless it was skipped by the continue statement).

Similar to If above, braces for the block of code associated with a While loop
can be omitted if the code consists of only one statement, for example:

``` c
int a = 1;
while (a < 100)
  a = a * 2;
```

This will merely increase a until a is not less than 100.

When the computer reaches the end of the while loop, it always goes back to the
while statement at the top of the loop, where it re-evaluates the controlling
condition. If that condition is "true" at that instant -- even if it was
temporarily 0 for a few statements inside the loop -- then the computer begins
executing the statements inside the loop again; otherwise the computer exits the
loop. The computer does not "continuously check" the controlling condition of a
while loop during the execution of that loop. It only "peeks" at the controlling
condition each time it reaches the while at the top of the loop.

It is very important to note, once the controlling condition of a While loop
becomes 0 (false), the loop will not terminate until the block of code is
finished and it is time to reevaluate the conditional. If you need to terminate
a While loop immediately upon reaching a certain condition, consider using
break.

A common idiom is to write:

``` c
int i = 5;
while (i--) {
  printf("java and c# can't do this\n");
}
```

This executes the code in the while loop 5 times, with i having values that
range from 4 down to 0 (inside the loop). Conveniently, these are the values

needed to access every item of an array containing 5 elements.


#### For loops

For loops generally look something like this:

``` c
for (initialization; test; increment) {
  /* code */
}
```

The _initialization_ statement is executed exactly once - before the first
evaluation of the test condition. Typically, it is used to assign an initial
value to some variable, although this is not strictly necessary. The
_initialization_ statement can also be used to declare and initialize variables
used in the loop.

The test expression is evaluated each time before the code in the `for` loop
executes. If this expression evaluates as 0 (false) when it is checked (i.e. if
the expression is not true), the loop is not (re)entered and execution continues
normally at the code immediately following the FOR-loop. If the expression is
non-zero (true), the code within the braces of the loop is executed.

After each iteration of the loop, the increment statement is executed. This
often is used to increment the loop index for the loop, the variable initialized
in the initialization expression and tested in the test expression. Following
this statement execution, control returns to the top of the loop, where the test
action occurs. If a `continue` statement is executed within the for loop, the
increment statement would be the next one executed.

Each of these parts of the for statement is optional and may be omitted. Because
of the free-form nature of the for statement, some fairly fancy things can be
done with it. Often a for loop is used to loop through items in an array,
processing each item at a time.

``` c
int myArray[12];
int ix;
for (ix = 0; ix < 12; ix++) {
  myArray[ix] = 5 * ix + 3;
}
```

The above for loop initializes each of the 12 elements of `myArray`. The loop
index can start from any value. In the following case it starts from 1.

``` c
for (ix = 1; ix <= 10; ix++) {
  printf("%d ", ix);
}
```

which will print

``` bash
1 2 3 4 5 6 7 8 9 10
```

You will most often use loop indexes that start from 0, since arrays are indexed
at zero, but you will sometimes use other values to initialize a loop index as
well.

The increment action can do other things, such as decrement. So this kind of
loop is common:

``` c
for (i = 5; i > 0; i--) {
  printf("%d ", i);
}
```

which yields

``` bash
5 4 3 2 1
```

Here's an example where the test condition is simply a variable. If the variable
has a value of 0 or NULL, the loop exits, otherwise the statements in the body
of the loop are executed.

``` c
for (t = list_head; t; t = NextItem(t)) {
  /* body of loop */
}
```

A WHILE loop can be used to do the same thing as a FOR loop, however a FOR loop
is a more condensed way to perform a set number of repetitions since all of the
necessary information is in a one line statement.

A FOR loop can also be given no conditions, for example:

``` c
for (;;) {
  /* block of statements */
}
```

This is called an infinite loop since it will loop forever unless there is a
break statement within the statements of the for loop. The empty test condition
effectively evaluates as true.

It is also common to use the comma operator in for loops to execute multiple
statements.

``` c
int i, j, n = 10;
for (i = 0, j = 0; i <= n; i++, j += 2) {
  printf("i = %d , j = %d \n", i, j);
}
```

Special care should be taken when designing or refactoring the conditional part,
especially whether using `<` or `<=` , whether start and stop should be
corrected by 1, and in case of prefix- and postfix-notations. ( On a 100 yards
promenade with a tree every 10 yards there are 11 trees. )

``` c
int i, n = 10;
for (i = 0; i < n; i++)
  printf("%d ", i); // processed n times => 0 1 2 3 ... (n-1)
printf("\n");
for (i = 0; i <= n; i++)
  printf("%d ", i); // processed (n+1) times => 0 1 2 3 ... n
printf("\n");
for (i = n; i--;)
  printf("%d ", i); // processed n times => (n-1) ...3 2 1 0
printf("\n");
for (i = n; --i;)
  printf("%d ", i); // processed (n-1) times => (n-1) ...4 3 2 1

printf("\n");
```

#### Do-While loops

A DO-WHILE loop is a post-check while loop, which means that it checks the
condition after each run. As a result, even if the condition is zero (false), it
will run at least once. It follows the form of:

``` c
do {
  /* do stuff */
} while (condition);
```

Note the terminating semicolon. This is required for correct syntax. Since this
is also a type of while loop, `break` and `continue` statements within the loop
function accordingly. A `continue` statement causes a jump to the test of the
condition and a `break` statement exits the loop.

It is worth noting that Do-While and While are functionally almost identical,
with one important difference: Do-While loops are always guaranteed to execute
at least once, but While loops will not execute at all if their condition is 0
(false) on the first evaluation.


#### One last thing: `goto`

`goto` is a very simple and traditional control mechanism. It is a statement
used to immediately and unconditionally jump to another line of code. To use
`goto`, you must place a label at a point in your program. A label consists of a
name followed by a colon (`:`) on a line by itself. Then, you can type
`goto label;` at the desired point in your program. The code will then continue
executing beginning with label. This looks like:

``` c
MyLabel:
  /* some code */
  goto MyLabel;
```

The ability to transfer the flow of control enabled by gotos is so powerful
that, in addition to the simple if, all other control constructs can be written
using gotos instead. Here, we can let "S" and "T" be any arbitrary statements:

``` c
if (''cond'') {
  S;
} else {
  T;
}
/* ... */
```

The same statement could be accomplished using two gotos and two labels:

``` c
if (''cond'') goto Label1;
  T;
  goto Label2;
Label1:
  S;
Label2:
  /* ... */
```

Here, the first `goto` is conditional on the value of "cond". The second `goto`
is unconditional. We can perform the same translation on a loop:

``` c
while (''cond1'') {
  S;
  if (''cond2'')
    break;
  T;
}
/* ... */
```

Which can be written as:

``` c
Start:
  if (!''cond1'') goto End;
  S;
  if (''cond2'') goto End;
  T;
  goto Start;
End:
  /* ... */
```

As these cases demonstrate, often the structure of what your program is doing
can usually be expressed without using gotos. Undisciplined use of gotos can
create unreadable, unmaintainable code when more idiomatic alternatives (such as
if-elses, or for loops) can better express your structure. Theoretically, the
goto construct does not ever have to be used, but there are cases when it can
increase readability, avoid code duplication, or make control variables
unnecessary. You should consider first mastering the idiomatic solutions, and
use `goto` only when necessary. Keep in mind that many, if not most, C style
guidelines strictly forbid use of `goto`, with the only common exceptions being
the following examples.

One use of `goto` is to break out of a deeply nested loop. Since break will not
work (it can only escape one loop), `goto` can be used to jump completely
outside the loop. Breaking outside of deeply nested loops without the use of the
`goto` is always possible, but often involves the creation and testing of extra
variables that may make the resulting code far less readable than it would be
with `goto`. The use of `goto` makes it easy to undo actions in an orderly
fashion, typically to avoid failing to free memory that had been allocated.

Another accepted use is the creation of a state machine. This is a fairly
advanced topic though, and not commonly needed.


### Examples

``` c
#include <errno.h>
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
  int years;

  printf("Enter your age in years : ");
  fflush(stdout);
  errno = 0;
  if (scanf("%d", &years) != 1 || errno)
    return EXIT_FAILURE;
  printf("Your age in days is %d\n", years * 365);
  return 0;
}
```
@run


## Procedures and functions

In C programming, all executable code resides within a function. A function is a
named block of code that performs a task and then returns control to a caller.
Note that other programming languages may distinguish between a "function",
"subroutine", "subprogram", "procedure", or "method" -- in C, these are all
functions.

A function is often executed (called) several times, from several different
places, during a single execution of the program. After finishing a subroutine,
the program will branch back (return) to the point after the call.

Functions are a powerful programming tool.

As a basic example, suppose you are writing a program that calculates the
distance of a given (x,y) point to the x-axis and to the y-axis. You will need
to compute the absolute value of the whole numbers x and y. We could write it
like this (assuming we don't have a predefined function for absolute value in
any library):

``` c
#include <stdio.h>

/*this is the function to compute the absolute value of a whole number.*/
int abs(int x)
{
  if (x>=0) return x;
  else return -x;
}

/*this is the program that uses twice the function defined above.*/
int main()
{
  int x, y;

  printf("Type the coordinates of a point in 2-plane, say P = (x,y). First x=");
  scanf("%d", &x);
  printf("Second y=");
  scanf("%d", &y);

  printf("The distance of the P point to the x-axis is %d. \n Its distance to the y-axis is %d. \n", abs(y), abs(x));

  return 0;
}
```
@run

The following example illustrate the usage of a function as a procedure.
Consider you are making a program that tells students if they are approved in
the discipline or not. We can create a function and call it as many times as we
need instead of repeating the same code.

``` c
#include<stdio.h>

/*here is where the 'check' function is being defined.*/
void check(int x)
{
  if (x<60)
    printf("Sorry! You will need to try this course again.\n");
  else
    printf("Enjoy your vacations! You are approved.\n");
}

/*here the program actually starts, and use the check function three times.*/
int main()
{
  int a, b, c;

  printf("Type your grade in Mathematics (whole number). \n");
  scanf("%d", &a);
  check(a);

  printf("Type your grade in Science (whole number). \n");
  scanf("%d", &b);
  check(b);

  printf("Type your grade in Programming (whole number). \n");
  scanf("%d", &c);
  check(c);

  /* this program should be replaced by something more meaningful.*/
  return 0;
}
```

Notice that in the program above, there is no outcome value for the 'check'
function. It only executes a procedure.

This is precisely what functions are for.


### More on functions

A function is like a black box. It takes in input, does something with it, then
spits out an answer.

Note that a function may not take any inputs at all, or it may not return
anything at all. In the above example, if we were to make a function of that
loop, we may not need any inputs, and we aren't returning anything at all (Text
output doesn't count - when we speak of returning we mean to say meaningful data
that the program can use).

We have some terminology to refer to functions:

* A function, call it f, that uses another function g, is said to call g. For
  example, f calls g to print the squares of ten numbers.
* A function's inputs are known as its arguments
* A function g that gives some kind of answer back to f is said to return that
  answer. For example, g returns the sum of its arguments.


#### Writing functions in C

It's always good to learn by example. Let's write a function that will return
the square of a number.

``` c
int square(int x)
{
  int square_of_x;
  square_of_x = x * x;
  return square_of_x;
}
```

To understand how to write such a function like this, it may help to look at
what this function does as a whole. It takes in an int, x, and squares it,
storing it in the variable `square_of_x`. Now this value is returned.

The first int at the beginning of the function declaration is the type of data
that the function returns. In this case when we square an integer we get an
integer, and we are returning this integer, and so we write int as the return
type.

Next is the name of the function. It is good practice to use meaningful and
descriptive names for functions you may write. It may help to name the function
after what it is written to do. In this case we name the function "square",
because that's what it does - it squares a number.

Next is the function's first and only argument, an int, which will be referred
to in the function as x. This is the function's input.

In between the braces is the actual guts of the function. It declares an integer
variable called square_of_x that will be used to hold the value of the square of
x. Note that the variable square_of_x can only be used within this function, and
not outside. We'll learn more about this sort of thing later, and we will see
that this property is very useful.

We then assign `x` multiplied by `x`, or `x` squared, to the variable
`square_of_x`, which is what this function is all about. Following this is a
return statement. We want to return the value of the square of x, so we must say
that this function returns the contents of the variable `square_of_x`.

Our brace to close, and we have finished the declaration.

Written in a more concise manner, this code performs exactly the same function
as the above:

``` c
int square(int x)
{
  return x * x;
}
```

Note this should look familiar - you have been writing functions already, in
fact - main is a function that is always written.


##### In general

In general, if we want to declare a function, we write

``` c
type name(type1 arg1, type2 arg2, ...)
{
 // code ...
}
```

We've previously said that a function can take no arguments, or can return
nothing, or both. What do we write if we want the function to return nothing? We
use C's void keyword. void basically means "nothing" - so if we want to write a
function that returns nothing, for example, we write

``` c
void sayhello(int number_of_times)
{
  int i;
  for(i=1; i <= number_of_times; i++) {
     printf("Hello!\n");
  }
}
```

Notice that there is no return statement in the function above. Since there's
none, we write void as the return type. (Actually, one can use the return
keyword in a procedure to return to the caller before the end of the procedure,
but one cannot return a value as if it were a function.)

What about a function that takes no arguments? If we want to do this, we can
write for example

``` c
float calculate_number(void)
{
  float to_return=1;
  int i;
  for(i=0; i < 100; i++) {
     to_return += 1;
     to_return = 1/to_return;
  }
  return to_return;
}
```

Notice this function doesn't take any inputs, but merely returns a number
calculated by this function.

Naturally, you can combine both void return and void in arguments together to
get a valid function, also.


##### Recursion

Here's a simple function that does an infinite loop. It prints a line and calls
itself, which again prints a line and calls itself again, and this continues
until the stack overflows and the program crashes. A function calling itself is
called recursion, and normally you will have a conditional that would stop the
recursion after a small, finite number of steps.

``` c
      // don't run this!
void infinite_recursion()
{
    printf("Infinite loop!\n");
    infinite_recursion();
}
```

A simple check can be done like this. Note that `++depth` is used so the
increment will take place before the value is passed into the function.
Alternatively you can increment on a separate line before the recursion call. If
you say `print_me(3,0)`; the function will print the line Recursion 3 times.

``` c
void print_me(int j, int depth)
{
  if(depth < j) {
    printf("Recursion! depth = %d j = %d\n",depth,j); //j keeps its value
    print_me(j, ++depth);
  }
}
```

Recursion is most often used for jobs such as directory tree scans, seeking for
the end of a linked list, parsing a tree structure in a database and factorising
numbers (and finding primes) among other things.


##### Static functions

If a function is to be called only from within the file in which it is declared,
it is appropriate to declare it as a static function. When a function is
declared static, the compiler will know to compile an object file in a way that
prevents the function from being called from code in other files.

Example:

``` c
static int compare( int a, int b )
{
    return (a+4 < b)? a : b;
}
```


### Using C functions

We can now write functions, but how do we use them? When we write main, we place
the function outside the braces that encompass main.

When we want to use that function, say, using our calculate_number function
above, we can write something like

``` c
float f;
f = calculate_number();
```

If a function takes in arguments, we can write something like

``` c
int square_of_10;
square_of_10 = square(10);
```

If a function doesn't return anything, we can just say

``` c
say_hello();
```

since we don't need a variable to catch its return value.


### Functions from the C Standard Library

While the C language doesn't itself contain functions, it is usually linked with
the C Standard Library. To use this library, you need to add an `#include`
directive at the top of the C file, which may be one of the following from
C89/C90 (the functions available are):

[__`<assert.h>`__](https://en.wikipedia.org/wiki/Assert.h)
* `assert(int)`

[__`<ctype.h>`__](https://en.wikipedia.org/wiki/Ctype.h)
* `isalnum`, `isalpha`, `isblank`
* `iscntrl`, `isdigit`, `isgraph`
* `islower`, `isprint`, `ispunct`
* `isspace`, `isupper`, `isxdigit`
* `tolower`, `toupper`

[__`<errno.h>`__](https://en.wikipedia.org/wiki/Errno.h)
* (errno)

[__`<float.h>`__](https://en.wikipedia.org/wiki/Float.h)
* (constants)

[__`<limits.h>`__](https://en.wikipedia.org/wiki/Limits.h)
* (constants only)

[__`<locale.h>`__](https://en.wikipedia.org/wiki/Locale.h)
* `struct lconv* localeconv(void);`
* `char* setlocale(int, const char*);`

[__`<math.h>`__](https://en.wikipedia.org/wiki/Math.h)
* `sin`, `cos`, `tan`
* `asin`, `acos`, `atan`, `atan2`
* `sinh`, `cosh`, `tanh`
* `ceil`
* `exp`
* `fabs`
* `floor`
* `fmod`
* `frexp`
* `ldexp`
* `log`, `log10`
* `modf`
* `pow`
* `sqrt`

[__`<setjmp.h>`__](https://en.wikipedia.org/wiki/Setjmp.h)
* `int setjmp(jmp_buf env)`
* `void longjmp(jmp_buf env, int value)`

[__`<signal.h>`__](https://en.wikipedia.org/wiki/Signal.h)
* `int raise(int sig).`
* `void* signal(int sig, void (*func)(int))`

[__`<stdarg.h>`__](https://en.wikipedia.org/wiki/Stdarg.h)
* `va_start (va_list, ap)`
* `va_arg (ap, (type))`
* `va_end (ap)`
* `va_copy (va_list, va_list)`

[__`<stddef.h>`__](https://en.wikipedia.org/wiki/Stddef.h)
* offsetof macro

[__`<stdio.h>`__](https://en.wikipedia.org/wiki/Stdio.h)
* `fread`, `fwrite`
* `getc`, `putc`
* `getchar`, `putchar`, `fputchar`
* `gets`, `puts`
* `printf`, `vprintf`
* `fprintf`, `vfprintf`
* `sprintf`, `snprintf`, `vsprintf`, `vsnprintf`
* `perror`
* `scanf`, `vscanf`
* `fscanf`, `vfscanf`
* `sscanf`, `vsscanf`
* `setbuf`, `setvbuf`
* `tmpnam`
* `ungetc`
* [`printf`](https://en.wikibooks.org/wiki/C_Programming/Procedures_and_functions/printf)
* [full list](http://www.utas.edu.au/infosys/info/documentation/C/CStdLib.html#ctype.h)

[__`<stdlib.h>`__](https://en.wikipedia.org/wiki/Stdlib.h)
* `atof(char*)`, `atoi(char*)`, `atol(char*)`
* `strtod(char * str, char ** endptr )`, `strtol(char *str, char **endptr)`,
  `strtoul(char *str, char **endptr)`
* `rand()`, `srand()`
* `malloc(size_t)`, `calloc (size_t elements, size_t elementSize)`,
  `realloc(void*, int)`
* `free (void*)`
* `exit(int)`, `abort()`
* `atexit(void (*func)())`
* `getenv`
* `system`
* `qsort(void *, size_t number, size_t size, int (*sortfunc)(void*, void*))`
* `abs`, `labs`
* `div`, `ldiv`

[__`<string.h>`__](https://en.wikipedia.org/wiki/String.h)
* `memcpy`, `memmove`
* `memchr`, `memcmp`, `memset`
* `strcat`, `strncat`, `strchr`, `strrchr`
* `strcmp`, `strncmp`, `strccoll`
* `strcpy`, `strncpy`
* `strerror`
* `strlen`
* `strspn`, `strcspn`
* `strpbrk`
* `strstr`
* `strtok`
* `strxfrm`

[__`<time.h>`__](https://en.wikipedia.org/wiki/Time.h)
* `asctime (struct tm* tmptr)`
* `clock_t clock()`
* `char* ctime(const time_t* timer)`
* `double difftime(time_t timer2, time_t timer1)`
* `struct tm* gmtime(const time_t* timer)`
* `struct tm* gmtime_r(const time_t* timer, struct tm* result)`
* `struct tm* localtime(const time_t* timer)`
* `time_t mktime(struct tm* ptm)`
* `time_t time(time_t* timer)`
* `char * strptime(const char* buf, const char* format, struct tm* tptr)`
* `time_t timegm(struct tm *brokentime)`


### Variable-length argument lists

Functions with variable-length argument lists are functions that can
take a varying number of arguments. An example in the C standard library
is the `printf` function, which can take any number of arguments
depending on how the programmer wants to use it.

C programmers rarely find the need to write new functions with
variable-length arguments. If they want to pass a bunch of things to a
function, they typically define a structure to hold all those things --
perhaps a linked list, or an array -- and call that function with the
data in the arguments.

However, you may occasionally find the need to write a new function that
supports a variable-length argument list. To create a function that can
accept a variable-length argument list, you must first include the
standard library header `stdarg.h`. Next, declare the function as you
would normally. Next, add as the last argument an ellipsis ("..."). This
indicates to the compiler that a variable list of arguments is to
follow. For example, the following function declaration is for a
function that returns the average of a list of numbers:

``` c
  float average (int n_args, ...);
```

Note that because of the way variable-length arguments work, we must
somehow, in the arguments, specify the number of elements in the
variable-length part of the arguments. In the `average` function here,
it's done through an argument called `n_args.` In the `printf` function,
it's done with the format codes that you specify in that first string in
the arguments you provide.

Now that the function has been declared as using variable-length
arguments, we must next write the code that does the actual work in the
function. To access the numbers stored in the variable-length argument
list for our `average` function, we must first declare a variable for
the list itself:

``` c
  va_list myList;
```

The `va_list` type is a type declared in the `stdarg.h` header that
basically allows you to keep track of your list. To start actually using
`myList`, however, we must first assign it a value. After all, simply
declaring it by itself wouldn't do anything. To do this, we must call
`va_start`, which is actually a macro defined in `stdarg.h.` In the
arguments to `va_start`, you must provide the `va_list` variable you
plan on using, as well as the name of the last variable appearing before
the ellipsis in your function declaration:

``` c
#include <stdarg.h>
float average (int n_args, ...)
{
    va_list myList;
    va_start (myList, n_args);
    va_end (myList);
}
```

Now that `myList` has been prepped for usage, we can finally start accessing the
variables stored in it. To do so, use the `va_arg` macro, which pops off the
next argument on the list. In the arguments to `va_arg`, provide the `va_list`
variable you're using, as well as the primitive data type (e.g. `int`, `char`)
that the variable you're accessing should be:

``` c
#include <stdarg.h>
float average (int n_args, ...)
{
    va_list myList;
    va_start (myList, n_args);

    int myNumber = va_arg (myList, int);
    va_end (myList);
}
```

By popping `n_args` integers off of the variable-length argument list, we can
manage to find the average of the numbers:

``` c
#include <stdarg.h>
float average (int n_args, ...)
{
    va_list myList;
    va_start (myList, n_args);

    int numbersAdded = 0;
    int sum = 0;

    while (numbersAdded < n_args) {
        int number = va_arg (myList, int); // Get next number from list
        sum += number;
        numbersAdded += 1;
    }
    va_end (myList);

    float avg = (float)(sum) / (float)(numbersAdded); // Find the average
    return avg;
}
```

By calling `average(2, 10, 20)`, we get the average of 10 and 20, which is 15.


## Standard libraries

The __C standard library__ is a standardized collection of
[header files](https://en.wikipedia.org/wiki/header_file) and library routines
used to implement common operations, such as input/output and character string
handling. Unlike other languages (such as COBOL, Fortran, and PL/I) C does not
include builtin keywords for these tasks, so nearly all C programs rely on the
standard library to operate.


### History

The C programming language previously did not provide any elementary functions,
such as I/O operations. Over time, user communities of C shared ideas and
implementations to provide those functions. These ideas became common, and were
eventually incorporated into the definition of the standardized C programming
language in 1989. These are now called the __C standard libraries__.

Both Unix and C were created at AT&T's Bell Laboratories in the late 1960s and
early 1970s. During the 1970s the C programming language became increasingly
popular, with many universities and organizations beginning to create their own
variations of the language for their own projects. By the start of the 1980s
compatibility problems between the various C implementations became apparent. In
1983 the American National Standards Institute (ANSI) formed a committee to
establish a standard specification of C known as "ANSI C". This work culminated
in the creation of the so-called __C89__ standard in 1989. Part of the resulting
standard was a set of software libraries called the __ANSI C standard library__.

Later revisions of the C standard have added several new required header files
to the library. Support for these new extensions varies between implementations.

The headers `<iso646.h>`, `<wchar.h>`, and `<wctype.h>` were added with
Normative Addendum 1 (hereafter abbreviated as __NA1__), an addition to the C
Standard ratified in 1995.

The headers `<complex.h>`, `<fenv.h>`, `<inttypes.h>`, `<stdbool.h>`,
`<stdint.h>`, and `<tgmath.h>` were added with C99, a revision to the C Standard
published in 1999.

> __Note:__
>
> The [C++](https://en.wikibooks.org/wiki/C%2B%2B) programming language includes
> the functions of the ANSI C 89 standard library, but has made several
> modifications, such as placing all identifiers into the std namespace and
> changing the names of the header files from `<xxx.h>` to `<cxxx>` (however,
> the C-style names are still available, although deprecated).


### Design

The declaration of each function is kept in a header file, while the actual
implementation of functions are separated into a library file. The naming and
scope of headers have become common but the organization of libraries still
remains diverse. The standard library is usually shipped along with a compiler.
Since C compilers often provide extra functions that are not specified in ANSI
C, a standard library with a particular compiler is mostly incompatible with
standard libraries of other compilers.


Much of the C standard library has been shown to have been well-designed. A few
parts, with the benefit of hindsight, are regarded as mistakes. The string input
functions `gets()` (and the use of `scanf()` to read string input) are the
source of many buffer overflows, and most programming guides recommend avoiding
this usage. Another oddity is `strtok()`, a function that is designed as a
primitive [lexical analyser](https://en.wikipedia.org/wiki/lexical_analysis) but
is highly "fragile" and difficult to use.


### ANSI Standard

The ANSI C standard library consists of 24 C header files which can be included
into a programmer's project with a single directive. Each header file contains
one or more function declarations, data type definitions and macros. The
contents of these header files follows.

In comparison to some other languages (for example Java) the standard library is
minuscule. The library provides a basic set of mathematical functions, string
manipulation, type conversions, and file and console-based I/O. It does not
include a standard set of "container types" like the C++ Standard Template
Library, let alone the complete graphical user interface (GUI) toolkits,
networking tools, and profusion of other functions that Java provides as
standard. The main advantage of the small standard library is that providing a
working ANSI C environment is much easier than it is with other languages, and
consequently porting C to a new platform is relatively easy.

Many other libraries have been developed to supply equivalent functions to that
provided by other languages in their standard library. For instance, the GNOME
desktop environment project has developed the GTK+ graphics toolkit and GLib, a
library of container data structures, and there are many other well-known
examples. The variety of libraries available has meant that some superior
toolkits have proven themselves through history. The considerable downside is
that they often do not work particularly well together, programmers are often
familiar with different sets of libraries, and a different set of them may be
available on any particular platform.


#### ANSI C library header files

* [`<assert.h>`](https://en.wikipedia.org/wiki/Assert.h)
  Contains the assert macro, used to assist with detecting logical errors and
  other types of bug in debugging versions of a program.

* [`<complex.h>`](https://en.wikipedia.org/wiki/Complex.h)
  A set of functions for manipulating complex numbers. (New with __C99__)

* [`<ctype.h>`](https://en.wikipedia.org/wiki/Ctype.h)
  This header file contains functions used to classify characters by their types
  or to convert between upper and lower case in a way that is independent of the
  used character set (typically ASCII or one of its extensions, although
  implementations utilizing `EBCDIC` are also known).

* [`<errno.h>`](https://en.wikipedia.org/wiki/Errno.h)
  For testing error codes reported by library functions.

* [`<fenv.h>`](https://en.wikipedia.org/wiki/Fenv.h)
  For controlling floating-point environment. (New with __C99__)

* [`<float.h>`](https://en.wikipedia.org/wiki/Float.h)
  Contains defined constants specifying the implementation-specific properties
  of the floating-point library, such as the minimum difference between two
  different floating-point numbers (`_EPSILON`), the maximum number of digits of
  accuracy (`_DIG`) and the range of numbers which can be represented (`_MIN`,
  `_MAX`).

* [`<inttypes.h>`](https://en.wikipedia.org/wiki/Inttypes.h)
  For precise conversion between integer types. (New with __C99__)

* [`<iso646.h>`](https://en.wikipedia.org/wiki/Iso646.h)
  For programming in ISO 646 variant character sets. (New with __NA1__)

* [`<limits.h>`](https://en.wikipedia.org/wiki/Limits.h)
  Contains defined constants specifying the implementation-specific properties
  of the integer types, such as the range of numbers which can be represented
  (`_MIN`, `_MAX`).

* [`<locale.h>`](https://en.wikipedia.org/wiki/Locale.h)
  For `setlocale()` and related constants. This is used to choose an appropriate locale.

* [`<math.h>`](https://en.wikipedia.org/wiki/Math.h)
  For computing common mathematical functions -- see Further math or
  [C++ Programming/Code/Standard C Library/Math](https://en.wikibooks.org/wiki/C%2B%2B_Programming/Code/Standard_C_Library/Math)
  for details.

* [`<setjmp.h>`](https://en.wikipedia.org/wiki/Setjmp.h)
  `setjmp` and `longjmp`, which are used for non-local exits

* [`<signal.h>`](https://en.wikipedia.org/wiki/Signal.h)
   For controlling various exceptional conditions

* [`<stdarg.h>`](https://en.wikipedia.org/wiki/Stdarg.h)
  For accessing a varying number of arguments passed to functions.

* [`<stdbool.h>`](https://en.wikipedia.org/wiki/Stdbool.h)
  For a boolean data type. (New with __C99__)

* [`<stdint.h>`](https://en.wikipedia.org/wiki/Stdint.h)
  For defining various integer types. (New with __C99__)

* [`<stddef.h>`](https://en.wikipedia.org/wiki/Stddef.h)
  For defining several useful types and macros.

* [`<stdio.h>`](https://en.wikipedia.org/wiki/Stdio.h)
  Provides the core input and output capabilities of the C language. This file
  includes the venerable `printf` function.

* [`<stdlib.h>`](https://en.wikipedia.org/wiki/Stdlib.h)
  For performing a variety of operations, including conversion, pseudo-random
  numbers, memory allocation, process control, environment, signalling,
  searching, and sorting.

* [`<string.h>`](https://en.wikipedia.org/wiki/String.h)
  For manipulating several kinds of strings.

* [`<tgmath.h>`](https://en.wikipedia.org/wiki/Tgmath.h)
  For type-generic mathematical functions. (New with __C99__)

* [`<time.h>`](https://en.wikipedia.org/wiki/Time.h)
  For converting between various time and date formats.

* [`<wchar.h>`](https://en.wikipedia.org/wiki/wchar.h)
  For manipulating wide streams and several kinds of strings using wide
  characters - key to supporting a range of languages. (New with __NA1__)

* [`<wctype.h>`](https://en.wikipedia.org/wiki/Wctype.h)
  For classifying wide characters. (New with __NA1__)


### Common support libraries

While not standardized, C programs may depend on a runtime library of routines
which contain code the compiler uses at runtime. The code that initializes the
process for the operating system, for example, before calling main(), is
implemented in the C Run-Time Library for a given vendor's compiler. The
Run-Time Library code might help with other language feature implementations,
like handling uncaught exceptions or implementing floating point code.

The C standard library only documents that the specific routines mentioned in
this article are available, and how they behave. Because the compiler
implementation might depend on these additional implementation-level functions
to be available, it is likely the vendor-specific routines are packaged with the
C Standard Library in the same module, because they're both likely to be needed
by any program built with their toolset.

Though often confused with the C Standard Library because of this packaging, the
C Runtime Library is not a standardized part of the language and is
vendor-specific.


### Compiler built-in functions

Some compilers (for example, [GCC](https://en.wikipedia.org/wiki/GCC)) provide
built-in versions of many of the functions in the C standard library; that is,
the implementations of the functions are written into the compiled object file,
and the program calls the built-in versions instead of the functions in the C
library shared object file. This reduces function call overhead, especially if
function calls are replaced with inline variants, and allows other forms of
optimization (as the compiler knows the control-flow characteristics of the
built-in variants), but may cause confusion when debugging (for example, the
built-in versions cannot be replaced with instrumented variants).


### POSIX standard library

POSIX, (along with the Single Unix Specification), specifies a number of
routines that should be available over and above those in the C standard library
proper; these are often implemented alongside the C standard library functions,
with varying degrees of closeness. For example, glibc implements functions such
as fork within libc.so, but before NPTL was merged into glibc it constituted a
separate library with its own linker flag. Often, this POSIX-specified function
will be regarded as part of the library; the C library proper may be identified
as the ANSI or ISO C library.

The following libraries are recognized by POSIX:

* __c__

  This option shall make available all interfaces referenced in the System
  Interfaces volume of POSIX.1-2008, with the possible exception of those
  interfaces listed as residing in `<aio.h>`, `<arpa/inet.h>`, `<complex.h>`,
  `<fenv.h>`, `<math.h>`, `<mqueue.h>`, `<netdb.h>`, `<net/if.h>`,
  `<netinet/in.h>`, `<pthread.h>`, `<sched.h>`, `<semaphore.h>`, `<spawn.h>`,
  `<sys/socket.h>`, `pthread_kill()`, and` pthread_sigmask()` in `<signal.h>`,
  `<trace.h>`, interfaces marked as optional in `<sys/mman.h>`, interfaces
  marked as ADV (Advisory Information) in `<fcntl.h>`, and interfaces beginning
  with the prefix `clock_` or `time_` in `<time.h>`. This option shall not be
  required to be present to cause a search of this library.

* __l__

  This option shall make available all interfaces required by the C-language
  output of lex that are not made available through the -l c option. (The flex
  program, a clone of lex, uses fl instead of l.)

* __pthread__

  This option shall make available all interfaces referenced in `<pthread.h>`
  and `pthread_kill()` and `pthread_sigmask()` referenced in `<signal.h>`. An
  implementation may search this library in the absence of this option.

* __m__ 	

  This option shall make available all interfaces referenced in `<math.h>`,
  `<complex.h>`, and `<fenv.h>`. An implementation may search this library in
  the absence of this option.

* __rt__ 	

  This option shall make available all interfaces referenced in `<aio.h>`,
  `<mqueue.h>`, `<sched.h>`, `<semaphore.h>`, and `<spawn.h>`, interfaces marked
  as optional in `<sys/mman.h>`, interfaces marked as ADV (Advisory Information)
  in `<fcntl.h>`, and interfaces beginning with the prefix `clock_` and `time_`
  in `<time.h>`. An implementation may search this library in the absence of
  this option.

* __trace__ 	

  This option shall make available all interfaces referenced in `<trace.h>`. An
  implementation may search this library in the absence of this option.

* __xnet__ 	

  This option shall make available all interfaces referenced in `<arpa/inet.h>`,
  `<netdb.h>`, `<net/if.h>`, `<netinet/in.h>`, and `<sys/socket.h>`. An
  implementation may search this library in the absence of this option.

* __y__ 	

  This option shall make available all interfaces required by the C-language
  output of yacc that are not made available through the -l c option. (Some
  clones of yacc, including bison and byacc, include the entire library in the
  generated file, so it is not necessary to use -l y.)


## Beginning exercises

### Variables

#### Naming

1. Can a variable name start with a number?

       [(X)] no
       [( )] yes

2. Can a variable name start with a typographical symbol(e.g. `#`, `*`, `_`)?

       [(X)] no
       [( )] yes

3. Give an example of a C variable name that would not work. Why doesn't it work?

       [[2nd]]
       <script>
         let variable = `@input`;
         variable.match(/[A-Za-z_][A-Za-z0-9_]*/)[0] != variable;
       </script>


#### Data Types

1. List at least three data types in C
   * On your computer, how much memory does each require?
   * Which ones can be used in place of another? Why?
     * Are there any limitations on these uses?
     * If so, what are they?
     * Is it necessary to do anything special to use the alternative?

2. Can the name we use for a data type (e.g. 'int', 'float') be used as a
   variable?


#### Assignment

1. How would you assign the value 3.14 to a variable called `pi`?
2. Is it possible to assign an `int` to a `double`?

   1. Is the reverse possible?


#### Referencing

1. A common mistake for new students is reversing the assignment statement.
   Suppose you want to assign the value stored in the variable "pi" to another
   variable, say "pi2":

   * What is the correct statement?
   * What is the reverse? Is this a valid C statement
     (even if it gives incorrect results)?
   * What if you wanted to assign a constant value (like 3.1415) to "pi2":

     a. What would the correct statement look like?

     b. Would the reverse be a valid or invalid C statement?

**A Beginner’s Guide to FreeBasic**

 Copyright (c) Ebben Feagan and Richard Clark.

 Permission is granted to copy, distribute and/or modify this document
under the terms of the GNU Free Documentation License, Version 1.2 or
any later version published by the Free Software Foundation; with no
Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts. A
copy of the license is included in the section entitled "GNU Free
Documentation License".

The source code was compiled under version .17b of the FreeBasic
compiler and tested under Windows 2000 Professional and Ubuntu Linux
6.06. Later compiler versions may require changes to the source code to
compile successfully and results may differ under different operating
systems. All source code is released under version 2 of the Gnu Public
License (HTTP://www.gnu.org/copyleft/gpl.html). The source code is
provided AS IS,WITHOUT ANY WARRANTY; without even the implied warranty
of MERCHANTABILITY or Fitness FOR A PARTICULAR PURPOSE.

Microsoft Windows®, Visual Basic® and QuickBasic® are registered
trademarks and are copyright © Microsoft Corporation. Ubuntu is a
registered trademark of Canonical Limited.

To all the members of the FreeBasic community, especially the
developers.

### **Acknowledgments** 

Writing a book is difficult business, especially a book on programming.
It is impossible to know how to do everything in a particular language,
and everyone learns something from the programming community. I have
learned a multitude of things from the FreeBasic community and I want to
send my thanks to all of those who have taken the time to post answers
and examples to questions.

I would also like to say a big thanks to the developers of FreeBasic.
Without your continual hard work in development, we wouldn’t have what I
consider the premier OpenSource BASIC language for today.

The PDF version of this book was created Using Open Office 2.0.2,

HTTP://www.openoffice.org/.

About the Book 
===============

FBeginner is a concise, hands-on beginner’s guide to FreeBasic and is
aimed at the novice programmer. The book assumes no prior programming
knowledge. The goal of the book is to create a solid foundation in the
basics of programming in FreeBasic that the programmer can build and
expand upon.

FreeBasic is a cross-platform compiler, however this book concentrates
on using FreeBasic under the 32-bit Microsoft Windows™ and GNU/Linux
operating systems.

However, other than the installation and setup portions of this book,
most of the code should run under any of the supported platforms.

All of the source code presented in this book is original code, and can
be downloaded from the Clark Productions website located at
HTTP://rdc.ascii-world.com/ orhttp://freebasic.hmcsoft.org/.

Conventions Used in the Book 
=============================

The various styles used in the book along with their meaning, are listed
below. The basic paragraph format is the font you see here with each
paragraph indented.

Information that is supplemental to the topic being discussed will be
presented in the format below.

These colored boxes have additional, supplemental or historical
information associated with the current topic being discussed.

Source code is listed in a fixed font with borders to delimit the code
segment. You should always type in the programs. Most are small and can
be entered into the editor in just a couple of minutes. The physical act
of typing in the programs will help you learn the vocabulary and
structure of FreeBasic. You do not type in the line numbers; they are
only for referencing the code in the text. The file name for the program
is located after the code segment.

Option Explicit

Cls

Print "Hello World From FreeBasic!"

Sleep

End

##### Listing 1: helloworld.bas 

Following each listing is an analysis paragraph which explains how the
program works It is marked by the word Analysis: in bold with a fixed
font. Even though many of the keywords you will see may have not be
discussed in detail in the text, seeing these keywords in action will
help you become familiar with the vocabulary of FreeBasic.

Analysis: This will mark the beginning of an analysis section. The code
will be discussed using the line numbers referenced in the listing. You
do not type the numbers in the editor.

The output of a program is listed in a fixed font and enclosed in a gray
box as shown below. This output is given so you can compare the results
to see if you have entered the program correctly.

Hello World from FreeBasic!

##### Output 1: program.bas 

A potential problem is shown with a Caution paragraph. It is formatted
similarly to the Analysis paragraph.

Caution This style will alert you to potential problems and offer some
remedies or tips to avoid them.

If we look at the fact, we shall find that the great inventions of the
age are not, with us at least, always produced in universities.

Charles Babbage

Chapter 1 A Brief Introduction to FreeBASIC 
============================================

FreeBASIC is a 32-bit BASIC compiler that outputs native code for
Microsoft Windows, Linux and DOS via DJGPP. FreeBASIC is also Open
Source, which means anyone may freely view and edit the source to suit
their needs. Quickbasic Compatibility is FreeBASIC's call to fame, for
it is the most compatible compiler available.

Differences from QuickBASIC 
----------------------------

-   Default (DEF\#\#\#) type of not explicitly declared variables

<!-- -->

-   FreeBASIC: INTEGER
-   QuickBASIC: Single

<!-- -->

-   INTEGER's size

<!-- -->

-   FreeBASIC: 32-bit, use SHORT type for 16-bit integers
-   QuickBASIC: 16-bit

<!-- -->

-   **Function calling**

<!-- -->

-   FreeBASIC: All functions must have been declared, even with CALL.
-   QuickBASIC: With CALL it is possible to invoke prototype-less
    functions.

<!-- -->

-   Arrays not declared

<!-- -->

-   FreeBASIC: All functions must be explicitly declared.
-   QuickBASIC: Arrays are automagically created with up to 10 indexes.

<!-- -->

-   Variables with the same names as keywords

<!-- -->

-   FreeBASIC: Not allowed, even with suffixes.
-   QuickBASIC: Allowed if no suffix is used (IE, dim LEFT as integer).

<!-- -->

-   Alignment / Padding of TYPE fields

<!-- -->

-   FreeBASIC: Same as in C, use FIELD=constant to change.
-   QuickBASIC: Never done.

<!-- -->

-   Fixed-Length strings

<!-- -->

-   FreeBASIC: Real length is the given len plus one (null char), even
    on Type fields Strings are filled with nulls, so strings can't
    contain null characters.
-   QuickBASIC: Strings are filled with white spaces

Key Features of FreeBASIC 
--------------------------

-   **Built-in Graphics library**

<!-- -->

-   Completely compatible with old QB Graphics commands, but it builds
    on this to offer much more.
-   Support for high resolutions and any color depth, and any number of
    off screen pages.
-   All drawing functions can operate on screen as well as on off screen
    surfaces(GET/PUT buffers) of any size.
-   Advanced sprites handling, with clipping, transparency, alpha and
    custom blending.
-   Direct access to screen memory.
-   BMP loading/saving capabilities.
-   OpenGL support: init an OpenGL mode with a single command, then use
    GL instructions directly.
-   Keyboard, mouse and joystick handling functions.
-   The Graphics library is fast: MMX optimized routines are used if MMX
    is available.
-   Small footprint: when using Graphics commands, your EXEs will grow
    in size by a minimum of 30/40K only.
-   Stand-aloness: generated EXEs will depend only upon system libs, no
    external libraries required.
-   As all of FB, also gfxlib is completely multi platform: underneath
    it uses DirectX or GDI (if DX is not available) under Win32, direct
    VGA/ModeX/VESA access under DOS, or raw Xlib under Linux.

<!-- -->

-   Create OBJ's, LIB's, DLL's, and console or GUI EXE's

<!-- -->

-   You are in no way locked to an IDE or editor of any kind.
-   You can create static and dynamic libraries adding just one
    command-line option (-lib or -dll).

<!-- -->

-   **Debugging support**

<!-- -->

-   Full debugging support with GDB (the GNU debugger) or Insight (the
    GDBGUI front end)
-   Array bounds checking (only enabled by the -exx command-line option)
-   Null pointers checking (same as above)

<!-- -->

-   **Function overloading**

<!-- -->

-   DECLARE SUB Test OVERLOAD (a AS DOUBLE)
-   DECLARE SUB Test (a AS SINGLE)
-   DECLARE SUB Test (a AS INTEGER, b AS INTEGER = 1234)
-   DECLARE SUB Test (a AS BYTE, b AS SHORT)

<!-- -->

-   **Inline Assembly**

<!-- -->

-   Intel syntax.
-   Reference variables directly by name with no "trick code" needed.

<!-- -->

-   **Most of the known C libraries can be used directly, without
    wrappers**

<!-- -->

-   GTK+ 2.0: cross-platform GUI Toolkit (over 1MB of headers, including
    support for Glade, libart and glGtk)
-   libxml and libxslt: defacto standard XML and XSL libraries
-   GSL - GNU Scientific library: complex numbers, vectors and matrices,
    FFT linear algebra, statistics, sorting, differential equations, and
    a dozen other sub-libraries with mathematical routines
-   GMP - GNU Multiple Precision Arithmetic Library: known as the
    fastest bignum library
-   SDL - Simple Direct Media Layer: multimedia library for audio, user
    input, 3Dand 2D gfx (including the sub-libraries such as SDL\_Net,
    SDL\_TTF, etc)
-   OpenGL: portable library for developing interactive 2D and 3D
    graphics games and applications (including support for frameworks
    such as GLUT and GLFW)
-   Allegro: game programming library (graphics, sounds, player input,
    etc)
-   GD, DevIL, FreeImage, GRX and other graphic-related libraries
-   OpenAL, Fmod, BASS: 2D and 3D sound systems, including support for
    mod,
-   mp3, ogg, etc
-   ODE and Newton - dynamics engines: libraries for simulating rigid
    body dynamics
-   CGI-util and Fast CGI: web development
-   DirectX and the Windows API - the most complete headers set between
    the Basic compilers available, including support for the Unicode
    functions
-   DispHelper - COM IDispatch interfaces made easy
-   And many more!

<!-- -->

-   Support for numeric (integer or floating-point) and strings types
-   DECLARE SUB Test(a AS DOUBLE = 12.345, BYVAL b AS BYTE = 255, BYVAL
    sAS STRING = "abc")
-   **Unicode support**

<!-- -->

-   Besides ASCII files with Unicode escape sequences (\\u), FreeBASIC
    can parse UTF-8, UTF-16LE, UTF-16BE, UTF-32LE and UTF-32BE source
    (.bas) or header(.bi) files, they can freely mixed with other
    sources/headers in the same project (also with other ASCII files).
-   Literal strings can be typed in the original non-latin alphabet,
    just use an text-editor that supports some of the Unicode formats
    listed above.
-   The WSTRING type holds wide-characters, all string functions (like
    LEFT,TRIM, etc) will work with wide-strings too.

<!-- -->

-   **Unlimited number of symbols**

<!-- -->

-   Being a 32-bit application, FreeBASIC can compile source code files
    up to 2GB long.
-   The number of symbols (variables, constants, et cetera) is only
    limited by the total memory available during compile time. You can,
    for example, include OpenGL, SDL, BASS, and GTK simultaneously in
    your source code.

<!-- -->

Chapter 2 Numeric Data Types 
=============================

When starting out with a new programming language, one of the first
things you should learn is the language’s data types. Virtually every
program manipulates data, and to correctly manipulate that data you must
thoroughly understand the available data types Data type errors rank
second to syntax errors but they are a lot more troublesome. The
compiler can catch syntax errors and some data type errors, but most
data type errors occur when the program is running, and often only when
using certain types of data These kind of intermittent errors are
difficult to find and difficult to fix. Knowing the kind, size and
limits of the data types will help keep these kinds of errors to a
minimum.

FreeBasic has all the standard numeric data types that you would expect
for a Basic compiler, as well as pointers which you usually only find in
lower-level languages such as C. Table 3.1 lists all the numeric data
types that FreeBasic supports. In the list below, you will notice that
Integer and Long are grouped together. This is because a Long is just an
alias for Integer. They are exactly the same data type.

  --------------- -------------------------------- ----------------------------------
  Numeric Data    Types Size                       Limits

  Byte            8-bit signed, 1 byte             -128 to 127

  Double          64-bit, floating point, 8bytes   -2.2E-308 to +1.7E+308
                                                   

  Integer         (Long) 32-bit, signed, 4 bytes   -2,147,483,648 to
                                                   
                                                   2,147,483,647

  LongInt          64-bit, signed, 8 bytes         -9,223,372,036,854 775, 808
                                                   
                                                   to
                                                   
                                                   9,223,372,036,854,775,807

  Short 16-bit,   signed, 2 bytes                  -32,768 to 32,767

  Single          32-bit, floating point, 4bytes   1.1 E-38 to 3.43 E+38

  UByte           8-bit, unsigned, 1 byte          0 to 255

  UInteger        32-bit, unsigned , 4 bytes       0 to 4,294,967,295

  ULongInt        64-bit, unsigned, 8 bytes        0 to 18,446,744,073,709,551,61 5

  Ushort          16-bit, unsigned, 2 bytes        0 to 65365

  Pointer         32-bit, memory address, 4bytes   Must be initialized at runtime
  --------------- -------------------------------- ----------------------------------

Table 2.1: FreeBasic Numeric Data Types

Signed Versus Unsigned Data Types 
----------------------------------

Signed data types, as the name implies, can be negative, zero or
positive. Unsigned types can only be zero or positive, which give them a
greater positive range than their signed counterparts. If your data will
never be negative, using the unsigned data types will allow you to store
larger numbers in the same size variable.

The Floating Point Data Type 
-----------------------------

The floating point data types, Single and Double are able to store
numbers with decimal digits. Keep in mind that floating-point numbers
are subject to rounding errors, which can accumulate over long
calculations. You should carry more than the number of decimal digits
than you need to ensure the greatest accuracy.

Pointer Data Types 
-------------------

Pointer data types are unlike the other data types in that they store a
memory address and not data. Since pointers are handled differently than
regular data types, a separate chapter has been devoted to the subject
and will not be examined in this chapter

Numeric Variables 
------------------

The numeric data types define what numbers you can work with in your
program, but you must create variables to actually hold the numbers. A
variable is a name composed of letters, numbers or the underscore
character such as MyInteger, orMyInteger2. There are rules for variable
naming though, that you must keep in mind.

-   Variable names must start with a letter or the underscore character.
    It is not recommended however, to use the underscore character, as
    this is generally used to indicate a system variable, and it is best
    to avoid it in case there may be a conflict with existing system
    variable names.

-   Most punctuation marks have a special meaning in FreeBasic and
    cannot be used in a variable name. While the period can be used, it
    is also used as a deference operator in Types, and so should not be
    used to avoid confusion or potential problems with future versions
    of the compiler.

-   Numbers can be used in a variable name, but cannot be the first
    character. MyVar1 is legal, but 1MyVar will generate a compiler
    error.

The compiler creates variables in two ways. The first method, which
isn't recommended and has been moved to the QB compatibility mode, is to
let the compiler create variables on their first use. When the compiler
first encounters a name in a program that is not a reserved word or
keyword, it creates a variable using that name with the default data
type. In most cases, the default data type is an integer. You can change
the default variable type by using the DEF\#\#\# directive, which will
be covered later in this chapter. To enable these features, you must
compile your program with either“-lang qb” or “-lang deprecated”. The
problem with the first-use method is that it is very easy to introduce
hard-to-find bugs in your program.

The term “bug” for a software error has a long, and somewhat disputed
history. The term predates modern computers and was used to describe
industrial or electrical defects. Its use in relation to software errors
is credited to Grace Hopper, a pioneer in the field of software design.
According to the story, a moth was discovered between two electrical
relays in a Mark II computer. Hopper made a note of it in her journal,
along with the moth, and the term became associated with software errors
after the incident.

The moth is now on display at the Smithsonian. [^1]

The Dim Statement 
------------------

The second, and preferred method is to explicitly declare variables in
your program using the Dim statement. The Dim statement instructs the
compiler to set aside some memory for a variable of a particular data
type. For example, the statement Dim

myInteger as Integer instructs the compiler to set aside 4 byes of
storage for the variable myInteger. Whenever you manipulate myInteger in
a program, the compiler will manipulate the data at the memory location
set aside for myInteger. Just as with variable names, there are some
rules for the use of Dim as well.

1.  Dim myVar As Integer. This will create a single integer-type
    variable.
2.  Dim As Integer myVar, myVar2. This will create two integer-type
    variables.
3.  Dim myVar As Double, myVar2 As Integer. This will create a
    double-type variable and an integer-type variable.
4.  Dim myVar as Integer = 5. This will create an integer-type variable
    and set the value of the variable to 5.
5.  Dim myVar As Double = 5.5, myVar2 As Integer = 5. This will create a
    double-type variable and set the value to 5.5, and an integer-type
    variable and set the value to 5.
6.  Dim Shared as Integer myInt. This will create a shared
    (global)variable myInt accessible anywhere within your program.

<!-- -->

Caution Dim myVar, myVar2 As Double. This may look like it creates two
double-type variables, however myVar will not be defined and will result
in compilation errors Use rule 2 if you want to create multiple
variables of the same type.

Shared Variables 
-----------------

As you can see in rule 6 above, using the Dim Shared version of Dim
creates a shared variable. This means that any variable you create as
Shared can be accessed anywhere within the program’s current module. To
put it another way, the scope of a shared variable is module level
scope. Scope refers to the visibility of a variable, whereyou can access
a particular variable within a program. There are different levels of
scopeand each are discussed in detail later in this book.

The number of variables in your program (as well as the program itself)
is limited onlyby your available memory, up to 2 gigabytes.

Static Variables 
-----------------

Static variables are used within subroutines and functions and retain
their values between calls to the subroutine or functions. The following
program demonstrates using astatic variable as a counter within a
subroutine.

1.  sub StaticSub()
2.  Dimension a static variable
3.  Static cnt As Integer4
4.  
5.  'Increment the count6
6.  cnt += 17
7.  Print "In StaticSub";cnt;" time(s)."
8.  
9.  END Sub
10. 
11. 'Dimension working variable
12. 
13. DIM i As Integer
14. 
15. 'Call sub 10 times
16. 
17. FOR i = 1 To 1015
18. StaticSub
19. 
20. NEXT
21. 
22. SLEEP
23. 
24. END

Listing 2.1: static.bas

Analysis: In line 1 the subroutine StaticSub is defined. A subroutine is
code that is

executed only when called by the subroutine name which, in this case, is
StaticSub. Line3 dimensions a static variable cnt, which is incremented
when the subroutine is called in

line 6. Line 7 prints out the current value of cnt to the console
screen.

In line 10 a working varible that will be used in the For-Next is
declared. Lines 14through 16 define the For-Next loop which will call
StaticSub 10 times. Line 18 waits for akey press and line 19 ends the
program.

Running the program in FBIde, you should get the following output.

In StaticSub 1 time(s).

In StaticSub 2 time(s).

In StaticSub 3 time(s).

In StaticSub 4 time(s).

In StaticSub 5 time(s).

In StaticSub 6 time(s).

In StaticSub 7 time(s).

In StaticSub 8 time(s).

In StaticSub 9 time(s).

In StaticSub 10 time(s).

Output 2.1: Output of static.bas

As you can see from the output, the value of cnt is preserved between
calls to the subroutine. Static variables can only be defined within a
subroutine or function. Variables declared outside of a subroutine or
function, that is at the module level, will maintain

their values and are static by default.

Common Variables 
-----------------

Variables declared as Common can be shared between multiple code
modules, that is between multiple bas files in the same program. Common
variables will be discussed in detail later in this book.

Extern and Import Variables 
----------------------------

Extern and Import are used when creating DLL's and like Common, are
designed to share variables in different modules. Extern and Import will
be discussed in detail in the chapter on creating DLLs with FreeBasic.

Data Type Suffixes 
-------------------

You can use QuickBasic style data type suffixes in FreeBasic, although
this feature was implemented mainly to support QuickBasic legacy code
and is only available when compiling with the “-lang qb” or “-lang
deprecated” compiler options. Table 3.2 lists the data type suffixes.

Data Type Suffix

Byte b

Short s

Integer %

Long &, l

Ulong ul

LongInt ll

UlongInt ull

Single !

Double \#

String \$

Table 2.2: Supported Data Type Suffixes

Changing The Default Data Type 
-------------------------------

As already mentioned, the default data type for an undeclared variable
is an integer. The default data type can be changed for a range of
variables by using one of the DEF statements. Table 3.3 lists all the
DEF statements available in FreeBasic.

  ----------------- ---------------------------------------------------------------------------------------------
  Statement         Comment
  DEF BYTE a-b      Sets the default data type to byte for undeclared variables starting with letter range.
  DEF DBL a-b       Sets the default data type to double for undeclared variables starting with letter range.
  DEF INT a-b        Sets the default data type to integer for undeclared variables starting with letter range.
  DEF LNG a-b       Sets the default data type to long for undeclared variables starting with letter range.
  DEF LNGINT a-b    Sets the default data type to longint for undeclared variables starting with letter range.
  DEF SHORT a-b     Sets the default data type to short for undeclared variables starting with letter range.
  DEF SNG a-b       Sets the default data type to single for undeclared variables starting with letter range.
  DEF STR a-b       Sets the default data type to string for undeclared variables starting with letter range.
  DEF UBYTE a-b     Sets the default data type to ubyte for undeclared variables starting with letter range.
  DEF UINT a-b      Sets the default data type to uinteger for undeclared variables starting with letter range.
  DEF ULNGINT a-b   Sets the default data type to ulongint for undeclared variables starting with letter range.
  DEF USHORT a-b    Sets the default data type to ushort for undeclared variables starting with letter range.
  ----------------- ---------------------------------------------------------------------------------------------

Table 2.3: FreeBasic DEF Statements

The DEF statement will affect all variables that start with a letter in
the given range. So if you add DEFDBL m-n to your program, any variable
starting with m or n, will default to a double-type. All other variables
that start with different numbers will default to an integer-type. A Dim
statement will override any DEF statement, so if you declare an integer
variable starting with m, it will be an integer, even though the DEFDBL
is in effect.

Using Different Number Formats 
-------------------------------

Besides decimal numbers, FreeBasic is able to recognize numbers in
hexadecimal,

binary and octal formats. Table 3.4 lists the number base and format to
use.

Number Base Format

Decimal myVar = 254

Hexadecimal myVar = &HFE

Binary myVar = &B11111110

Octal myVar = &O376

Exponential Numbers myVar = 243E10

Table 2.4: Format of Number Bases

### Hexadecimal Numbers 

Hexadecimal is a base 16 numbering scheme and have digits in the range
of 0 to F.

Hexadecimal numbers are commonly used as constant values in the Windows
API and many third party libraries as it is a compact way to represent a
large value. To indicate a hexadecimal number, use the &H prefix.

### Binary Numbers 

Binary is a base 2 numbering scheme and have digits in the range of 0
and 1.

Binary is the language of the computer. Although we can enter numbers
and letters into the computer, it all must be translated into binary
before the computer can understand it. To indicate a binary number, use
the &B prefix.

### Octal Numbers 

Octal is a base eight numbering scheme and have digits in the range of 0
to 7.

Octal numbers were very popular in early computer systems, but aren’t
used much today except in some specialized applications. To indicate an
octal number, use the &O prefix.

### Exponential Numbers 

You can use exponential numbers in your program by adding the E suffix
followed by the power. To use the number 105, you would write the number
as 10E05. You can directly set a double or single type variable using
the exponent format. You can also use negative exponents such as 10E-5,
which when printed to the screen would like 1.e004.

Which Data Type To Use? 
------------------------

There are a number of different data types available, so how do you
choose the right data type for any given application? The rule of thumb
is to use the largest datatype you need to hold the expected range of
values. This may seem like stating the obvious, but many programs fail
because the programmer did not fully understand the range of data in
their program. When you crate a program, you should map out not only the
logic of the program, but the data associated with each block of logic.
When you map out the data ahead of time, you are less likely to run into
data-type errors.

For example, if you were working with ASCII codes, which range from 0 to
255, an ubyte would be a good choice since the range of an ubyte is the
same as the range of ASCII codes, and you are only using 1 byte of
memory. There is another consideration though, the “natural” data size
of the computer. On a 32-bit system, the natural data size is 4 bytes,
or an integer. This means that the computer is optimized to handle an
integer,

and does so more efficiently, even though you are “wasting” 3 bytes of
memory by using an integer for an ASCII code.

In most cases an integer is a good general-purpose choice for integer
data. The range is quite large, it handles both negative and positive
numbers and you benefit from using the computer’s natural data type. For
floating point data, a double is a good choice since, like the integer,
it has a good range of values and better precision than a single.

For large integer data you should use a uinteger for positive data or a
longint for large negative and positive numbers. These are only
suggestions; what data type you end up using will be dictated by the
needs of your program.

These “rules of thumb” apply to single variable declarations where a few
wasted bytes are not critical. However, as you will see in the chapter
on arrays, choosing the rightsized data type is critical in large arrays
where a few wasted bytes can add up to a large amount of wasted memory.

Option Explicit 
----------------

You may notice when looking at other people's source code, the compiler
directive Option Explicit has been used at the top of each program. A
compiler directive is code that instructs the compiler to do something.
In the case of Option Explicit, it instructs the compiler to make sure
that any variable being used has been properly Dim’ed. Although you can
write a program without using Option Explicit and explicitly Dim’ing
each variable, you run the risk of introducing nasty, hard-to-find bugs
as the following short program illustrates.

1.  Dim myInteger as Integer
2.  'set myInteger to a value
3.  myInteger = 5
4.  'Oops we misspelled the variable name
5.  Print "The output of myInteger is";myIntger
6.  'wait for a key press
7.  Sleep
8.  End

Listing 2.2: nooptionexplicit.bas

1.  Analysis: In line 1 myInteger is being declared to the compiler. The
    compiler will use this declaration to allocate space for the
    variable. In line 3 the variable is being initialized to a value, in
    this case 3. The Print statement in line 5 will print out the result
    to the console screen. Sleep, listed in line 7, will wait for a key
    press and the End keyword in line 8 will end the program. The End
    statement isn't mandatory at the end of a program but should be used
    especially if you want to return an exit code to the operating
    system.

After typing this program into FBIde and running the program, you should
see the following output.

The output of myInteger is 0

##### Output 2.2: nooptionexplicit.bas 

The output should be 5, but as you can see, the result isn’t what was
expected or wanted. Since Option Explicit wasn’t used in the program,
the compiler created a new variable when it encountered the misspelled
variable name, myIntger, in the print statement. If this was large and
complicated program, you can see how difficult it would be to track this
error down and fix it.

Now, add Option Explicit at the top of the program and run it again. You
should seethe following error message in the results pane of FBIde.

Variable not declared, found: 'myIntger'

Print "The output of myInteger is";myIntger

 \^

Output 2.3: Modified nooptionexplicit.bas

Here the compiler detected the misspelled variable name and informed us
of the problem. You should always use Option Explicit in your programs.
A few seconds of extra typing will save you hours of frustration.

A Note about Option Explicit 
-----------------------------

Recent versions of the FreeBASIC compiler do not allow OPTION commands
including OPTION EXPLICIT. From now on OPTION EXPLICIT is implied and
your programs will behave as if you used OPTION EXPLICIT. It is a good
rule of thumb to always implicitly declare your variables, so get in the
habit now. To compile a source file that uses OPTION EXPLICIT, either
use “-lang deprecated” or remove the OPTION EXPLICIT line from the
source file.

A Look Ahead 
-------------

When working with numeric data, there are times when it becomes
necessary to convert one data type to another. FreeBasic offers two
conversion methods, implicit and explicit, which you will see in the
next chapter.

Excercises 
-----------

1\) What data type would be the best to store the number 196? 

2\) What data type would be the best to store the number 2.134? 

3\) What data type is the best for general usage on 32-bit systems? 

4\) What is the difference between signed and unsigned data types? 

5\) What prefix would you use to designate a binary number? 

6\) What prefix would you use to designate a hexadecimal number? 

7\) What Alphabetic letters are allowed in a hexadecimal number? 

8\) What would the hexadecimal number 1AF be in decimal form? 

Chapter 3 Converting Numeric Data Types 
========================================

When you work with numbers there will come a time when you will need to
convert a variable from one data type to another data type. In FreeBasic
there are two types of data conversion. Implicit, where the compiler
will automatically convert the data types during an assignment or
calculation, and explicit using one of the predefined conversion
functions.

Implicit Data Conversion 
-------------------------

Implicit data conversion occurs either through an assignment statement,
or as the result of a calculation. Where implicit data conversion can
cause a problem is in the loss of precision that can result when
converting a large data type to a smaller data type.

While implicit data conversion eases the programming process somewhat,
you want to make sure that the results you are getting are what you
expect. You should always check the result of an implicit conversion to
make sure the range of values being converted is in the expected range.

The following short program illustrates the conversion that takes place
during an assignment statement.

1

Dim As Double my Dbl

2

Dim As Integer myInt

3

'Set my Dbl to a float value

4

my Dbl = 5.56

5

'Assign myInt the float, will be converted to int

6

myInt = my Dbl

7

Print "myInt ="; myInt

8

Sleep

9

End

10

Listing 3.1: assignations

Analysis: In lines 1 and 2 two variable are being declared, my Dbl, a
double-teletypewriter and myInt, an integer-type variable. Line 3 is a
comment which, as you can see,

starts with the ' (single quote) character. In line 4 the double-type
variable is being initialized to the floating-point value 5.56. In line
6 the double is being assigned to an integer variable, invoking the
implicit conversion. In line 7 the Print displays the result on the
console window. In line 8 the program waits for a key press with the
Sleep statement and in line 9 the End statement is used to end the
program.

Running the program will result in the following output.

myInt = 6

Output 3.1: assignations

In the program, the value of my Dbl which is a double-type variable, was
set to

5.56. When myInt was assigned this float value, the compiler converted
the value to an integer, and then rounded it up to 6. Maybe you were
just looking for the whole number portion of 5? In this case, your
result would be incorrect, although you may not know until later in the
program. This type of subtle bug is another one of those problems that
are hard to track down and fix.

Caution Even if the compiler is producing the correct result, there is
no guarantee that future versions of the compiler will. It may be
necessary to change the behavior of the compiler to add features or fix
a bug, and you may find yourself with a program that suddenly quits
working.

The next little program illustrates the implicit conversion that takes
place during a calculation. In this example, the two integer operands
are converted to double-types during the division calculation.

1

Dim As Double my Dbl

2

Dim As Integer myInt1, myInt2

3

'Assign values to myInt1, myInt2

4

myInt1 = 5

5

myInt2 = 3

6

my Dbl = myInt1 / myInt2

7

Print "my Dbl ="; my Dbl

8

Sleep

9

End

10

Listing 3.2: calcconv.bas

Analysis: Line 1 and 2 in the program are the alternate Dim statement
formats. You can use this format to declare multiple variables of the
same type. In line 4 and 5, the variables are initialized. In line 6 the
/ character is the division operator. The result of the division
operation will be implicitly converted to a double-type in the
assignment statement. Line 7 prints the newly converted value to the
screen and in lines 8 and 9, the program will wait for a key press and
then end.

Running the program produces the following output.

my Dbl = 1.66666666666667

Output 3.2: calconv.bas

The result is as expected since the double-type has a greater precision
than the integer-type. However, consider this program and its output,
which demonstrates the implicit rounding during calculations.

1

Dim As Double myDbl1, myDbl2

2

Dim As Integer myInt

3

'Assign values to myInt1, myInt2

4

myDbl1 = 5.6

5

myDbl2 = 3.1

6

myInt = myDbl1 / myDbl2

7

Print "myInt ="; myInt

8

Sleep

9

End

10

Listing 3.3: calcconv2.bas

Analysis: This program is similar to the program in Listing 4.2 except
the conversion process is from two double-type variables to an integer.
Lines 1 and 2 declare the working variables. Lines 4 and 5 set the
values of the two double-type variables. Inline 6 the double-type
division result is implicitly converted to an integer, resulting in
precision loss. Line 7 prints the result to the console window and lines
8 and 9 wait for akey press and end the program.

The output of the program:

myInt = 2

Output 3.3: calconv2.bas

In this example, the two double-type variables were converted to
integers and then the division operation was performed. Since 5.6 was
rounded up to 6 during the conversion, the result is 2 rather than 1.
This may not be a problem, but you should be aware that these types of
conversions occur when working with mixed precision types.

Explicit Data Conversion 
-------------------------

There is an alternative to implicit data conversion, explicit data
conversion whereyou use one of FreeBasic’s built-in conversion
functions. Since these functions are designed for conversion, they
return consistent results and are unlikely to change even if the
implicit rules of the compiler change. Even though it is more work, it
is always safer to explicitly convert data to the needed data type
before carrying out operations on that data.

### Numeric Data Conversion Functions 

Table 4.1 lists all the conversion functions. Keep in mind that these
functions do not check for overflow, so be sure that the value passed to
these functions is in the expected range.

Function Syntax Purpose Comment

Cast B = Cast(datatype,

expression)

Convert

expression to data-type listed.

Datatype is any of the available FreeBasic data-

types. Expression is a numeric value, variable or

expression.

CByte B =

CByte(expression)

Convert

expression to byte.

Expression must be in the range –128 to 127.

CDbl B = CDbl(expression) Convert

expression to double.

Expression must be in the range of -2.2E-308 to+1.7E+308.

Cint B = Cint(expression) Convert

expression to integer.

Expression must be in the range of –2,147,483,648 to2,147,483,647.

CLng B = CLng(expression) Convert

expression to long. Long is an alias for integer.

Expression must be in the range of –2,147,483,648 to2,147,483,647.

ClngInt B =

ClngInt(expression)

Convert

expression to long. int.

Expression must be in the range of –

9,223,372,036,854,775,808

to

9,223,372,036,854,775,807

CShort B =

CShort(expression)

Convert

expression to short.

Expression must be in the range of -32768 to 32767.

CUByte B =

CUByte(expression)

Convert

expression to unsigned byte.

Expression must be in the range of 0 to 255.

CUInt B = CUInt(expression) Convert

expression to unsigned integer.

Expression must be in the range of 0 to 4,294,967,296.

CULngInt B =

CULngInt(expression)

Convert

expression to long. unsigned integer.

Expression must be in the range of 0 to18,446,744,073,709,551,615

.

CUShort B =

CUShort(expression)

Convert

expression to unsigned short.

Expression must be in the range of 0 to 65535.

CSng B = SCng(expression) Convert

expression to single.

Expression must be in the range of 1.1 E-38 to 3.43E+38.

Table 3.1: FreeBasic Conversion Functions

When examining conversion functions it is important to understand how
the function rounds with both negative and positive numbers. The
FreeBasic conversion functions. round numbers up, making positive number
more positive and negative numbers more negative. The following program
illustrates the rounding with Cast and Cint, as well as demonstrating
that the conversion functions will work with expressions as well as
numbers.

1 Dim as Double myDouble1, myDouble2, myDouble3

2 Dim as Integer myInt

3

4'Set variable ranges

5myDouble1 = 143.5

6myDouble3 = 143.4

7myDouble2 = 143.5

8myInt = 12

9

10'Show cast in action

12Print "\*\* Cast \*\*"

13Print "Double1 ";myDouble1;" cast to integer ";Cast(Integer,
myDouble1)

14Print "Double2 ";myDouble2;" cast to integer ";Cast(Integer,
myDouble2)

15Print "Double3 ";myDouble3;" cast to integer ";Cast(Integer,
myDouble3)

16Print "Expression ";myDouble1;" + ";myInt;" cast to double ";

17Print Cast(Double, myDouble1 + myInt)

18Print

19

20'Show cint in action

21Print "\*\* CInt \*\*"

22Print "Double1 ";myDouble1;" cint to integer ";CInt(myDouble1)

23Print "Double2 ";myDouble2;" cast to integer ";CInt(myDouble2)

24Print "Double3 ";myDouble3;" cast to integer ";CInt(myDouble3)

25Print "Expression ";myDouble1;" + ";myInt;" cast to integer
";CInt(myDouble1 + myInt)

26Print "Expression ";myDouble2;" + ";myInt;" cast to integer
";CInt(myDouble2 + myInt)

27Print

28

29Sleep

30 End

31

32

Listing 3.4: convert.bas

Analysis: This program demonstrates the built-in FreeBasic conversion
functions.

Lines 1 and 2 declare the working variables using the alternate format
of the Dim. Two tables of information are printed to the console in line
12 to 18 and lines 21 to 27. In lines13 to 16, the result of the Cast
function is printed directly to the screen, as is the Cint function in
lines 22 to 26. Normally the values would be saved in another variable
to be used in the program. Line 16 ends with a semi-colon. This
instructs the compiler not to

print a carriage return after the print statement, so that when the
value of Cast is printed in line 17, the value will appear on the same
line as the data printed in line 16. The program is closed in the usual
way using Sleep and End.

Running the program will produce the output shown below.

\*\* Cast \*\*

Double1 143.5 cast to integer 144

Double2 143.5

cast to integer 144

Double3 143.4 cast to integer 143

Expression 143.5 + 12 cast to double 155.5

\*\* CInt \*\*

Double1 143.5 cint to integer 144

Double2 143.5

cast to integer 144

Double3 143.4 cast to integer 143

Expression 143.5 + 12 cast to integer 156

Expression 143.5

+ 12 cast to integer –132

Output 3.4: convert.bas

As you can see from the program, you can use both numbers and
expressions in the conversion functions. Keep in mind that if you pass
an expression to a conversion function, the evaluated expression must
not exceed the limit of the target data type, or an overflow will occur.
Looking at the output you can see that the rounding for middle values is
up or greater in magnitude. 143.5 rounds up, making the resulting number
more positive and –143.5, more negative.

### Using Conversion Functions in Macros 

One area where the conversion functions listed in Table 4.1 are useful
is in the

creation of macros. A macro is a small piece of executable code that the
compiler inserts into the program at designated areas. Macros are
defined using the \#Define compiler directive. \#Define has the format
\#Define name

symbol. When the compiler encounters

name within the program code, it is replaced with symbol.

The following program creates a macro that packs a screen row and column
number into the high and low bytes of a uinteger. The conversion
function Cint is used since you will not always know the data type being
passed to the macro, and you want to be sure that you are working with
known quantities.

'Macro created by v1ctor

\#define MAKDWORD(x,y) (cint(x) shl 16 or cint(y))

Dim myInt As Uinteger

Dim As Integer i, cnt

'Store row 5 column 5 in a single uinteger

myInt = MAKDWORD(5, 5)

'Set the width and height of the console window

Width 80, 25

'Print column headers

cnt = 1

For i = 1 To 80

 'Print columns as 12345678901...

If cnt = 10 Then

 cnt = 0

End If

Locate 1, i

'Convert to string so we don't get leading space

Print Str(cnt)

'Increment our counter

cnt += 1

Next

'Print row headers

cnt = 2

For i = 2 To 25

 'Row numbers will be like col numbers

If cnt = 10 Then

 cnt = 0

End If

Locate i, 1

'Convert to string so we don't get leading space

'We need the semicolon

so a line feed isn't printed

'on line 25 which would scroll screen.

Print Str(cnt);

'Increment our counter

cnt += 1

Next

'Print out string on saved location

Locate Hiword(myInt), Loword(myInt)

Print "We stored the screen location in a single uinteger!"

45

Sleep

46

End

47

48

Listing 3.5: makdword.bas

Analysis: In line 2 the \#define compiler directive is used to create a
macro. A macro is an snippet of executable code that the compiler will
insert into the code when it finds the macro name, MAKDWORD. In lines 4
and 5 the working variables are declared.

In line 8, the variable myInt is initialized with the macro previously
defined. The macro stores the screen locations, row 5 and column 5 in
the high and low word of the integer variable.

In line 11 the Width statement is used to set the console screen to 80
columns and

25 rows. The variable cnt, which will be used to print out the column
and row headers, is set to 1. Lines 14 through 24 prints out the column
headers using a For-Next loop. Line 19uses the Locate statement to set
the cursor position and line 36 prints out the value. The numbers will
range from 1 to 0 and then repeat.

In line 36 the Str function is used to convert the numeric value of cnt
to a string so that the Print statement will not insert a leading space.
Print inserts a leading space when printing numeric variables so they
can accommodate a leading negative sign. Lines 26through 39 print out
the row headers in the same fashion as the column headers.

In line 42 the two functions Hiword and Loword are used to retrieve the
high and low bytes of the integer variable, which contain the row and
column respectively. Line 45and 46 wait for a key press and end the
program in the usual fashion.

The macro is defined in line 2 takes two parameters, x and y. The
compiler will substitute MAKDWORD(x,y) with (cint(x) shl 16 or cint(y))
replacing x with the first

number and y with the second number. Cint is used within the macro so
that no matter

what values are passed through x and y, the macro will always be working
with integers.

The operators or and shl will be discussed later in the book.

The Locate statement expects a row number and column number to position
text on the screen. In line 42 we are using the two functions Hiword and
Loword to return the high (most significant) and low (least significant)
words of the integer myInt, which contain the row and column numbers
respectively.

Running the program will produce the following output.

12345678901234567890123456789012345678901234567890123456789012345678901234567890

2

3

4

5 We stored the screen location in a single uinteger!

6

Output 3.5: makdword.bas

\#Define is fully explored in the chapter on symbolic constants later in
the book.

Decimal Rounding Functions

FreeBasic has two built-in rounding functions for use with decimal
numbers. Table

4.2 lists the functions along with their explanations.

Function Syntax Comment

Int B = Int(expression) Returns an integer value less than or equal to
the input.

Fix B = Fix(expression) Returns the integer part of the input.

Table 3.2: FreeBasic Rounding Functions

As with the other conversion functions, this should be tested with both
negative and positive numbers to see how the function behaves. The
program intfix.bas listed below illustrates the results returned by the
functions as well as their use with calculations.

1

'Create some double variables

2

Dim As Double myDouble1 = 5.5,

myDouble2 = 5.9

3

'Show rounding on negative and positive values

4

Print "Doubles:", myDouble1, myDouble2

5

Print "Int:", Int(myDouble1), Int(myDouble2)

6

Print "Fix:", Fix(myDouble1), Fix(myDouble2)

7

Print

8

'Try some calculation expressions

9

myDouble1 = 15.78

10

myDouble2 = 22.12

11

Print "Expression:",myDouble1;" +";myDouble2;" = "; Str(myDouble1 +
myDouble2)

12

Print "Int:", Int(myDouble1 + myDouble2)

13

Print "Fix:", Fix(myDouble1 + myDouble2)

14

15

'Wait for key press

16

Sleep

17

End

18

Listing 3.6: intfix.bas

Analysis: Line 2 uses the alternative syntax for Dim to declare and
initialize the working variables. Line 4 through 6 display the results
of the conversion functions using both positive and negative numbers.
Line 9 and 10 set the values for the variables to be used in
calculations. Lines 12 through 14 display the results of the conversion
functions using calculations so FreeBasic resolves the calculations
before invoking the functions.

Lines 17 and 18 end the program in the usual way.

The result of running the program is shown in Output 4.6.

Doubles: 5.5

5.9

Int: 6

5

Fix: 5

5

Expression: 15.78

+ 22.12 = 6.34

Int: 6

Fix: 6

Output 3.6: basinfuls

Notice that in the output Int returns a –6 for the input –5.5, since 6
is less than –

5.5, and 5 for 5.9 since 5 is less than 6. Fix on the other hand
truncates the decimal and

returns the integer portion of the double. As you can see both functions
will also work with an expression, in this myDouble1 + myDouble2. Which
function you would use depends on what behavior you would need with
negative numbers, as they both return similar results with positive
numbers.

A Look Ahead 
-------------

In addition to the built-in conversion functions, there are a number of
functions

available in the C Runtime Library, which is the subject of the next
chapter.

Exercises 
----------

1\) How do you stop your program from printing a carriage return at the
end of a line? 

2\) What function would you use to convert an unknown value to a Double? 

3\) What function would you use to convert an unknown value to an
Integer? 

4\) What would be the result of the equation 5 / 2 if assigned to an
Integer? 

5\) How do the functions Int() and Fix() differ in their results? 

Chapter 4 Introduction to the C Runtime Library 
================================================

One of the original motivations for creating FreeBasic was to provide an
easy to use

wrapper for the C Runtime Library according to Andre Victor, the
language creator.

FreeBasic is as advanced as it is today because many of the functions
are wrappers forth runtime functions, which simplified the creation of
the language.

Since FreeBasic uses the C runtime library, you can use it as well in
your programs,

and there are a number of very useful conversion functions available.
The function definitions are contained in the header file crt.bi, and
you gain access to those functions by using the \#Include directive.

Caution Not all the functions listed in the various bi files in the CRT
folder

have been implemented in FreeBasic. If you get an error similar to the
following\[path/filename\].o:fake:(.text+0x16c): undefined reference to
\`rint', where path/filename is your program's path and filename, then
the function you are trying to use is not supported.

This is a linker error and indicates that the linker was not able to
find the referenced

function. There are also a number of functions and structures that will
only work in Windows and some that are GNU Extensions and will only work
on Linux.

The \#Include Directive 
------------------------

The syntax for the \#Include directive is \#Include \[Once\]
“filename.ext”.

Remember that a compiler directive instructs the compiler to do
something, and in this case, it instructs the compiler to include the
file “filename.ext” when compiling. When the compiler reads this
directive, it stops reading the current file and starts reading the
included file. If the included file also has an \#Include directive,
then that file is read in as

well. You can have up to 16 nested includes per program. To use the
runtime conversion functions in your own program you would add \#Include
Once “crt.bi” at the top of

your program.

The file extension bi stands for “basic include” and is usually
declaration statements and/or subroutines and functions. The crt.bi file
is located in the inc folder of

your FreeBasic installation. If a bi file is not located in the folder
where the program is being compiled, the compiler will look in the inc
folder for the file. If it can’t find the file, it will issue an error.
You can also include a path with the filename if you keep your include
files in a common folder besides the inc folder.

If you look at the contents of crt.bi you see that the file simply
includes other file sand references the library that contains the actual
function code.

1

\#ifndef \_\_CRT\_BI\_\_

2

\#define \_\_CRT\_BI\_\_

3

4

\#ifdef \_\_FB\_WIN32\_\_

5

\# inclib "msvcrt"

6

\#endif

7

8

\#include once "CRT/string.bi"

9

\#include once "CRT/math.bi"

10

\#include once "CRT/time.bi"

11

\#include once "CRT/wchar.bi"

12

\#include once "CRT/stdlib.bi"

13

\#include once "CRT/stdio.bi"

14

\#include once "CRT/io.bi"

15

\#include once "CRT/errno.bi"

16

17

\#endif ' \_\_CRT\_BI\_\_

Listing 4.1: crt.bi

Analysis: Crt.bi contains a number of compiler directives, the
statements that start with the \# character to control the compilation
process. In line the directive \#ifndef means “if not defined”. If the
symbol \_\_CRT\_BI\_\_ has not already been defined, then line2 will
define the symbol. The \#ifdef directive in line 4 means “if defined”.
If the compiler is running on a Win32 machine, the symbol
\_\_FB\_WIN32\_\_ will be defined which will include the library
"msvcrt" on line 5 with the \#inclib directive which means “include
library”. The \#endif on line 6 closes the opening \#ifdef on line 4.
Under Windows,

FreeBasic uses the Microsoft Runtime which is contained in the dynamic
link library (DLL)

msvcrt.dll.

Line 8 through 15 include each of the individual declaration files that
make up the C runtime library. The “\#include once” directive ensures
that the individual include files are only added once, even if another
module includes them. The \#endif on line 17 is used to close the
\#ifndef on line 1.

Notice that the \#Include directive use the Once modifier which tells
the compiler that this file should only be loaded once, even if a
subsequent file uses the same\#Include. This is to prevent duplicate
definition errors. It is always good practice to use the Once modifier
in your own includes.

Notice that the different files being included are located in the
inc/CRT folder. This is an example of setting the path for the \#Include
if they should be in a different folder.

Many of the third-party library bi files are in their own sub folders,
just to keep things a bit more organized. The conversion functions we
will be examining in this chapter are contained the file CRT/math.bi.

The \#Inclib directive above the include list tells the compiler what
library contains the functions. Library files are compiled subroutines,
functions and symbols that define the functionality of the library. Lib
files located in the lib folder of your FreeBasic installation.

They are usually named filename.a for static libraries and
filename.dll.a for dynamic link libraries. If you look in the lib folder
you will also see some filename.o files. Theseare object files. Object
files contain pre-parsed code that can be linked to an executable file
or to a library file.

Caution If you open one of the bi files in the inc folder, which you may
need to do from time to time to see what parameters a function requires
or to see the return type of

a function, be sure not to change anything in the file. You should
always open the files in read-only mode if your editor provides that
functionality.

The Declaration Statement 
--------------------------

If you look at math.bi you will see a number of Declaration statements.
A declaration statement is a function prototype that tells the compiler
that there is a function definition somewhere in the program code, or in
a library or an external dll. This forward reference is used so that the
compiler won’t complain if the function or sub is called before it finds
the actual code for the function. Once you understand how to interpret a
declaration statement, you will be able to use any function in the run
time library.

To understand the components of a declaration statement, here is the
declaration statement for the ceil function in math.bi. The ceil
function rounds a decimal value up to the nearest integer. That is, 1.5
would become 2.

Declare function ceil decline Alias "ceil" (byval as double) as double

You can break this declare down into the following functional sections.

•

Declare: This is the keyword for a declare statement.

•

Function: This can either be Function, to indicate that this procedure
returns a value, or Sub, which indicates that the procedure does not
return a value.

•

Ceil: This is the name of the function and the name that you would use
in your code. Do not use the name after Alias.

•

Cdecl: This is the function's method of passing arguments. When calling
an

external function, parameters must be pushed on the stack in the correct
order so that the function can pop the parameters off the stack
correctly. Cdecl stands for C Declare, and passes the arguments from
right to left using the C convention of parameter passing. The Pascal
calling convention pushes arguments from left tonight and is used when
calling functions created in the Pascal language. The Stdcall calling
convention pushes arguments from right to left and is used in Basic
libraries and Windows API.

•

Alias: This is an alternate name that is used by the linker when your
code is linked to other languages. You use an alias in case there is a
function in the target language that has the same name as your function.

•

(): The values inside the parenthesis are the parameters that the
function or sub expects. Ceil expects one parameter, a double-type
value. If the function expects multiple parameters, then commas will
separate them. A parameter can be any of the FreeBasic data types or a
composite type. Many of the runtime functions require pointers to other
data types or data structures.

•

By Val: The byval (by value) keyword indicates that the value being
passed to the function is a copy of the data, and not the actual data
itself. This is to prevent accidentally changing the actual data within
a function. You can also use ByRef(by reference) which passes the
address of the data to the function, and any changes in the parameter
are reflected in the actual data. By Val is the default behavior in
current versions of the compiler.

•

As \[data type\]: The As keyword after the parameter list indicates the
return type of the function. Subs do not have a return type so there
isn’t an As clause after the parameter list.

Notice that the ceil function returns a double and not an integer, even
though the conversion function rounds off the decimal portion. This is
to prevent integer overflow for very large numbers. Even though ceil,
and the other runtime conversion functions return a double you can
implicitly convert them to integers by simply assigning the return to an
integer variable or using the Cast function. Be sure to use an integer
data type with a large enough range for the result.

To use Ceil in your program you would write myDouble = Ceil(aDouble) or
myInt =

Ceil(aDouble). All declaration statements follow the same pattern as
Ceil.

DLLs created with Visual Basic 6tm and below are COM objects and not
standard DLLs. In order to use VB6 DLLs with FreeBasic you will need to
create a COM interface to access the DLL functions. Creating a COM
interface is a complicated topic and is beyond the scope of this book.

Runtime Conversion Functions 
-----------------------------

Table 5.1 lists some of the more useful conversion routines contained
within the

runtime library along with he syntax and some comments about the
function.

Function Syntax Comment

Ceil B = Ceil(double-type expression)

Ceil returns the nearest

integer greater than expression.

Floor B = Floor(double-type expression)

Floor returns the nearest

integer less than expression.

Modf B = Modf(double-type expression, double-type pointer)

Modf returns the fractions

part of expression and the integer part of expression in the double-type
pointer. The integer part of expression is rounded towards zero.

Table 4.1: Runtime Conversion Functions

It would require another book to examine all the functions in the
runtime library. Thereunto functions presented in this book were
selected because of their usefulness and to supplement FreeBasic’s
built-in functions.

Modf deserves special mention. A function can only return a single
value, the value defined in the As clause after the parameter list. This
does not mean however that you cannot return more than one value from a
function. Any additional values a function returns must be returned
through the parameter list. One way to do this is to use thereby keyword
on parameters. Any changes made to a byre parameter changes the actual
data. However, you cannot use byre on external libraries, due to
differences in

calling procedures, so pointers are used instead. There are two ways to
pass pointer data to a function; by explicitly declaring a pointer data
type which you will see in the chapter on pointers, or by using the
AddressOf operator which is explained here.

The AddressOf Operator @ 
-------------------------

When the compiler creates a variable, it allocates a portion of memory
equal to the size of the data type. For an integer it would allocate 4
bytes and for a double it would allocate 8 bytes. Each memory location
has an address associated with it so that the CPU can move data into and
out of the memory location. When the compiler allocates the memory, the
operating system returns an address for the memory location so that the
compiler can access that location. When you are working with variables
you are actually working with an addressable memory location in the
computer. You don't have to worry about the address since the compiler
handles all those details for you; you can just use the variable in your
program.

However, when you need to call a function like Modf that requires a
pointer to variable, then you need to know the address of the variable
so you can pass it to the function. Why can't you just use the variable
name, since it is an alias for the memory location? The answer is in the
declaration of Modf shown in listing 5.3.

declare function modf decline alias "modf" (byval as double, byval as
double ptr) as double

Listing 4.2: Modf Declaration

Notice that the second parameter is defined as byval and the data type
is a pointer(ptr) to a double-type variable. Remember that byval means
“make a copy of the contents of the parameter and use it in the
function.” If you were to simply use the variable name, you would be
passing the contents of the memory location, whatever is in the
variable,and not its address.

When you use a regular variable in your program, you are working with
the actual data in the memory location associated with the variable.
That is, a variable = data. If you define myInt as an integer and set it
equal to 5, when you print myInt to the screen you will see 5. The
pointer data type is unique in that what it contains isn't data, that is
a value like 134, rather it contains the address of a memory location. A
pointer = memory address. If you were to print a pointer to the screen
you would see a number that doesn't make much sense, since what you are
looking at isn't the data in the memory location,

but the address of the data in memory.

When you first create a pointer, it doesn't point to anything. This is
called a Null pointer. There are a number of ways to initialize the
pointer, but one method is to use the Address Of operator. If you create
a pointer variable such as myIntPtr you could initialize that pointer
with code like myIntPtr = @myInt. The @ is the AddressOf operator, and
this code snippet sets myIntPtr to the address of myInt. In other words,
an initialized pointer variable and the AddressOf operator both return
the same value, a memory address.

We can use this concept in the Modf function. Rather than creating a
pointer variable, we can create a double-type variable and then use this
variable with the Address Of operator for the return parameter. Remember
that you were able to use expressions with the built-in numeric
conversion functions. Using the AddressOf operator with a variable is an
expression which will be evaluated and the result, the variable address,
will be passed along to the function.

The following short program illustrates this concept.

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

'Need to include the runtime library

\#include "crt.bi"

'Set up some variables

Dim As Double myDouble, FracPart, IntPart

'Set the value we want to convert

myDouble = 12.56

'Call the function. Notice that we are using the addressof

'operator @ on IntPart.

FracPart = modf(myDouble, @IntPart)

'Get the result.

Print "myDouble = ";myDouble

Print "Fractional part:";FracPart

Print "Integer part:";IntPart

Sleep

End

Listing 4.3: addressof.bas

Analysis: In line 1 the crt.bi is included in this program so that all
the supported functions will be available to the program. In line 5 all
of the working variables are declared. In line 8, the variable to be
operated on is set to a decimal value. The Modf function is called in
line 11 using the AddressOf operator to retrieve the integer portion of
the return value. The fractional portion of the return value is loaded
into the FracPart variable. Line 13 through 15 print out the values
returned from the function. The program is closed in the usual way in
lines 17 and 18.

In line 5 we dimension the variables we will use: myDouble is the value
we want to convert, FracPart is the value returned by the function and
IntPart is the return value that will be passed through the second
parameter, the pointer. Notice in line 11 we are using the AddressOf
operator in conjunction with our regular double-type variable.

Here is the output of the program.

myDouble = 12.56

Fractional part: 0.560000000000001

Integer part: 12

Output 4.1: addressof.bas

The return value of the function, .56, is the fractional part and the
integer part 12,

is the value returned through the parameter. The series of zeros ending
in a 1 after the

.56 is the result of the precision conversion you will get with a double
value. Remember in the previous sections it was mentioned that double
and single data types are prone to rounding errors. Here you see why
this is true.

Caution When you are dealing with a pointer parameter, you must be sure
to pass the correct data type to the parameter. In the case of Modf, it
is expecting a double-type pointer which is 8 bytes. If you pass the
incorrect pointer type to a function, it may not do anything at all, or
it may try to write to 8 bytes of memory. If the function tries to write
to more memory than has been allocated you will see the infamous General
Protection Fault message and your program will be shut down. Always use
the proper pointer type with pointer parameters. General Protection
Fault is a Windows term and is equivalent to a Segmentation Fault on
Linux.

Testing the Runtime Conversion Functions 
-----------------------------------------

As you did with the other conversion functions, you should test these
functions with both positive and negative numbers to see how they
behave.

1

'Need to include the runtime library

2

\#include "crt.bi"

3

4

'Set up some variables

5

Dim As Double myDouble = 12.56, myDouble2 = 12.56

6

7

'Show the various conversion functions with

8

'positive and negative numbers.

9

Print "Ceil with";myDouble;" returns ";Ceil(myDouble)

10

Print "Ceil with ";myDouble2;" returns ";Ceil(myDouble2)

11

Print

12

Print "Floor with";myDouble;" returns ";Floor(myDouble)

13

Print "Floor with ";myDouble2;" returns ";Floor(myDouble2)

14

Print

15

16

'Wait for a key press

17

Sleep

18

End

19

20

Listing 4.4: crtfunc.bas

Analysis: Since these are C runtime functions, the crt.bi is included in
line 2. Line 5

shows the declaration of the working variables in the program, once
again using the alternate Dim syntax. Lines 9 through 14 print out the
return values of the functions with both positive and negative numbers.
Lines 17 and 18 close the program.

Line 2 in the program includes the crt.bi which is required for using
any of the run time functions. In line 5 the two working double-type
variables are dimensioned and initialized. As you can see, calling the
runtime functions is exactly the same as calling any of the FreeBasic
built-in functions. Running the program will produce the following

output.

Ceil with 12.56 returns 13

Ceil with 12.56

returns 12

Floor with 12.56 returns 12

Floor with 12.56

returns 13

Output 4.2: crtfunc.bas

As you can see in the output, Ceil returns the nearest integer greater
than the value. 13 is greater than 12 and -12 is less negative than
-12.56. Floor does just the opposite; it returns the nearest integer
less than the value. 12 is less than 12.56 and -13is more negative than
-12.56.

A Look Ahead 
-------------

Normally when you use numbers in your program, you are going to do some
sort of calculation with them. In the next chapter you will see
FreeBasic's arithmetic operators,

learn about operator precedence and explore the bits that make up a
number.

Exercises 
----------

1\) What is the extension of files that normally contain function
declarations for libraries? 

2\) What is the difference between the Ceil() and Floor() functions in
the C run time library? 

3\) What compiler directive is used to add additional files before
compilation? 

4\) What is a common cause of a Segmentation Fault or General Protection
Fault? 

Chapter 5 Arithmetic Operators 
===============================

Arithmetic Operators 
---------------------

The Table 6.1 lists all the arithmetic operators in FreeBasic. In the
table below, the operators will work on two or more expressions, where
expression is a number, variable or another expression. The square
brackets in the syntax column indicate optional additional expressions.

Function Syntax Comment

+ (Addition) B = expression +

expression \[ + expression…\]

Returns the sum of two or

more expressions.

Expression can be a number, variable or another

expression.

- (Subtraction) B = expression – expression\[ - expression…\]

Returns the difference

between two or more

expressions.

\* (Multiplication) B = expression \* expression\[ \* expression…\]

Returns the product of two or more expressions.

/ (Division) B = expression / expression\[ / expression…\]

Returns the division of two

or more expression. The result implicitly converted to the target data
type. That is,

if B is an integer, the result will be rounded, if B is a

double or single, the result will be a decimal number.

Note: If the second

expression evaluates to zero(0), then a runtime error will

occur.

\\ (Integer Division) B = expression \\ expression\[ \\ expression…\]

Returns the integer result of division of two or more

expressions. The result is implicitly converted to an integer.

Note: If the second

expression evaluates to zero(0), then a runtime error will

occur.

\^ (Exponentiation) B = expression\^value Returns the result of raising
expression to the power of value. That is 2\^2 = 2\*2.

MOD (Modulo) B = expression MOD Returns the remainder of

Function Syntax Comment

expression the implicit division of the expressions as an integer
result. If expression is a decimal value, expression is rounded before
the division.

- (Negation) B = - expression Returns the negated valueof expression.
This is the same as multiplying by –1. If expression is positive, B will
negative. If expression is negative, B will positive.

( ) (Parenthesis) B = expression operator

( expression \[operator expression \[ (…\])

Forces evaluation of

expression. Parenthesis can be nested, but must be

closed properly or a compile error will occur.

Table 5.1: Arithmetic Operators

You should be familiar with most of these operators from math class.
Integer division is used when you are not concerned about the remainder
of the division process.

The Mod operator has several uses including executing some code only at
certain times,

and for creating wrap-around functions such as are likely to occur when
a sprite reaches the edge of the screen and needs to wrap around to the
other side.

When using these operators together in single statement, you must b
aware of how FreeBasic evaluates the expression. For example, does 5 + 6
\* 3 equal 33 or does it equal 23? FreeBasic evaluates expressions based
on precedence rules, that is, rules that describe what gets evaluated
when. Table 6.2 lists the precedence rules for the arithmetic operators.
The order of precedence is the same order as the listing; that is the
top row has the highest precedence, while lower rows have lower
precedence.

Operator

( ) (Parenthesis)

\^ (Exponentiation)

- (Negation)

\*, / (Multiplication and division)

\\ (Integer division)

MOD (Modulus)

SHL, SHR (Shift bit left and shift bit right)

+, - (Addition and subtraction)

Table 5.2: Precedence of Arithmetic Operators

The SHL and SHR operators will be discussed in the next section, Bitwise
Operators. They are included here to show where they fall in the
precedence rules.

Looking at the table and the equation 5 + 6 \* 3 you can see that this
will evaluate to 23 not 33, since multiplication has a higher precedence
then addition. The compiler will read the expression from left to right,
pushing values onto an internal stack until it can resolve part or all
of the equation. For this equation 5 will be read and pushed, then the +
operator will be read and pushed onto the stack. Since the + operator
requires two operands, the compiler will read the next element of the
expression which will be the \*

operator. This operator also requires two operands, so \* will be pushed
onto the stack and the 3 will be read. Since \* takes priority over +,
the 6 and 3 will be multiplied, and that value will be stored on the
stack. At this point there is a 5, + and 18 on the stack. Since there is
only one operator left and two operands, the 5 and 18 will be added
together to make 23, which will be returned as the result of the
expression.

If you wanted to make sure that 5 + 6 gets evaluated first, then you
would use parenthesis to force the evaluation. You would write the
parenthesized expression as (5 +

6\) \* 3. Since the parenthesis have the highest precedence, the
expression they contain will be evaluated before the multiplication. The
evaluation process here is the same haste previous process. The ( is
treated as an operator and is pushed onto the stack. The 5,

+, and 6 are read followed by the ). The ) signals the end of the
parenthesis operation, soothe 5 and 6 are added together and pushed onto
the stack. The \* is read along with the 3.

The stack at this point contains an 11, \* and 3. The 11 and 3 are
multiplied together and33 is returned as the result of the evaluation.

You can also embed parenthesis within parenthesis. Each time the
compiler encounters a (, it begins a new parenthesis operation. When it
encounters a ), the last ( is used to evaluate the items contained
within the ( and ) and that result is either placed on the stack for
further evaluation or returned as a result. Each ( must be match to a )
or a compiler error will occur.

The following program demonstrates both implicit evaluation and force
devaluation.

1

Option Explicit

2

3

Dim As Integer myInt

4

5

'Let compiler evaluate expression according to precedence

6

myInt = 5 + 6 \* 3

7

Print "Expression 5 + 6 \* 3 = ";myInt

8

9

'Force evaluation

10

myInt = (5 + 6) \* 3

11

Print "Expression (5 + 6) \* 3 = ";myInt

12

13

'Wait for key press

14

Sleep

15

End

Listing 5.1: precedence.bas

Analysis: As always we open the program with Option Explicit in line 1
and declarethe working variables in line 3. In line 6 the compiler
evaluates the math expressionaccording to precedence rules and stores
the result in myInt, which is printed to theconsole window in line 7. In
line 10, parenthesis are used to force the evaluation of theexpression
which is printed to the console screen in line 11. Lines 14 and 15 close
theprogram in the usual way.

As you can see from the output below, using parenthesis allows you to
control theevaluation of the expression.

Expression 5 + 6 \* 3 = 23

Expression (5 + 6) \* 3 = 33

Output 5.1: precedence.bas

What about the case where tow operators are used that have the
sameprecedence level? How does FreeBasic evaluate the expression? To
find out, run thefollowing program.

1

Option Explicit

2

3

Dim As Integer myInt

4

5

'Expression 1

6

myInt = 3 + 5 4

7

8

Print "Expression 1: 3 + 5 4

is";myInt

9

10

'Expression 2

11

myInt = 3 5

+ 4

12

13

Print "Expression 2: 3 5

+ 4 is";myInt

14

15

'Expression 3

16

myInt = 6 \* 2 / 3

17

18

Print "Expression 3: 6 \* 2 / 3 is";myInt

19

20

'Expression 4

21

myInt = 6 / 2 \* 3

22

23

Print "Expression 4: 6 / 2 \* 3 is";myInt

24

25

26

Sleep

27

End

Listing 5.2: sameprecedence.bas

Analysis: In line 3 the working variable myInt is declared, since the
program usesthe Option Explicit directive in line 1. In line 6 the
expression has the + operator first andthe – second, while in line 11
the order has been reversed to test the evaluation order.

The results are printed in lines 8 and 13. Line 16 and 21 use the \* and
/ operators on thesame manner to test the order of evaluation and the
results are printed in lines 18 and

23\. 

Running the program produces the following result.

Expression 1: 3 + 5 4

is 4

Expression 2: 3 5

+ 4 is 2

Expression 3: 6 \* 2 / 3 is 4

Expression 4: 6 / 2 \* 3 is 9

Output 5.2: Output of sameprecedence.bas

As you can see from the output each expression has been evaluated from
left toright. In expression 1, 3 + 5 is 8 and subtracting 4 equals 4. In
expression 2, 3 – 5 isequal to -2, and adding 4 equals 2. In expression
3, 6 \* 2 is 12 and divide that by 3 andyou get 4. In expression 4, 6 /2
is 3 and multiplies by 3 results in 9. The program showsthat operators
that have the same precedence level are evaluated from left to right.

This is the case where parenthesis are very helpful in ensuring that the
evaluationorder is according to your program needs. When in doubt,
always use parenthesis toensure that the result is what you want in your
program.

Shortcut Arithmetic Operators 
------------------------------

FreeBasic has a number of shortcut arithmetic operators similar to those
found inthe C programming language. These operators have the same
precedence as their singlecounterparts. The following table lists the
shortcut operators.

Operator Syntax Comment

+= B += expression Add B to expression andassign to B.

-= B -= expression Subtract B to expressionand assign to B.

\*= B \*= expression Multiply B to expression andassign to B.

/= B /= expression Divide B by expression and

Operator Syntax Comment

assign to B.

\\= B \\= expression Integer divide B byexpression and assign to B.

Table 5.3: Shortcut Arithmetic Operators

Using these operators will cut down on the typing you have to do,
especially forstatements such as a = a + 1, which can be written as a +=
1.

Binary Number System 
---------------------

Computers use the binary, or base 2, numbering system to represent data.
Base 2digits are the numbers 0 and 1. A single binary 1 or 0 is called a
bit. Four bits is called anybble. Two nybbles, or 8 bits is called a
byte and 2 bytes make up a word. The size of adata type determines how
many bits are available to represent a particular number. A

byte has 8 bits, a short has 16 bits, an integer has 32 bits and a
longint has 64 bits.

You will notice that each data type is double the size of the previous
data type.

This is because the binary system uses powers of 2 to represent data. 20
is 1. 21 is 2. 22 is

4\. 23 is 8. 24 is 16, and so on. To find the value of a binary number,
you start from theright, which is position 0 and add the power of twos
going left if there is a 1 in the bitposition. If a nybble is 1101, then
the right-most position is 20, the next position left is 

skipped since it has a zero, followed by 22 and finally 23. Resolving
the power terms givesyou 1 + 4 + 8 which equals 13. The value ranges for
the different data types is a directresult of the number of bits in each
data type.

Being able to manipulate individual bits, bytes and words has a number
of uses.

For example, the messaging system of the Windows API use integers to
store both the idof a control and event the control received, as the
following code snippet shows.

1

Case WM\_COMMAND2

wmId = Loword( wParam )

3

wmEvent = Hiword( wParam )

Listing 5.3: Snippet from Windows Message Loop

In this snippet the id of the control is stored in the low word of
wParam, and theevent number is stored in the high word. Since a word is
2 bytes or 16 bits, you can store65535 ids in a single word, using an
unsigned data type, or 32767 ids for a signed datatype. This is a very
efficient way to manage data in your program.

The Sign Bit 
-------------

The sign bit, the leftmost bit, is used by the computer to determine if
a signed datatype is negative or positive using the Two's Complement
form of notation. To represent anegative number, the positive value of
the number is negated, that is all the 1's arechanged to 0 and the 0's
are changed to 1's, and 1 is added to that result. For example,

binary 5 is 0000 0101. Negating all the bits results in 1111 1010.
Adding 1 results in 11111011. Since the leftmost bit is 1, this is a
negative number.

We can confirm this by using the power of 2 notation which results in
the following:

-128 (27) + 64 (26) + 32 (25) + 16 (24) + 8 (23) + 0 + 2 (21) + 1 (20) =
- 5. Remember, ifa bit is zero, we add zero to the total. The following
program shows the binaryrepresentation of both positive 5 and negative
five.

Option Explicit

Dim As Byte myByte

Dim As String myBits

myByte = 5

'Get the binary form of number

myBits = Bin(myByte)

'Append some leading zeros so print line up

myBits = String(8 Len(

myBits), "0") & myBits

'Print out nybbles with a space between so is is easier to read

Print "myByte =";myByte;" which is binary ";

Print Mid(myBits, 1, 4) & " " & Mid(myBits, 5, 4)

myByte = 5

'Get the binary form of number

myBits = Bin(myByte)

'Append some leading zeros so print line up

myBits = String(8 Len(

myBits), "0") & myBits

'Print out nybbles with a space between so is is easier to read

Print "myByte =";myByte;" which is binary ";

Print Mid(myBits, 1, 4) & " " & Mid(myBits, 5, 4)

Sleep

End

Listing 5.4: signbit.bas

Analysis: Lines 3 and 4 declare the working variables, a byte that will
represent theactual number and a string that will represent the binary
value. In line 6 the myByte isset to 5. In line 8 the Bin function is
used to return a string that represents the binaryvalue of 5. Since Bin
does not return any leading 0's, the String function is used to padthe
string to a full 8 bits for display purposes.

The first parameter of the String function is the number of characters
to add andthe second parameter is the character to use to pad the
string. Since a byte is 8 bitslong, subtracting the length of myBits
from 8 will give the number of 0's to add to thestring, if the length of
myBits is less than 8. In line 12 the numeric value of myByte isprinted,
which is 5. A semi-colon is added to the end of print statement so that
Print willnot print out a carriage return.

In line 13 the binary string is printed in two groups of four, that is
each nybble, tomake the display easier to read. The Mid function used in
line 13 returns a portion of a

string. The first parameter of the Mid function is the string, the
second is the startposition and the third parameter is the number of
characters to copy. The first Midreturns the first four characters,
which is appended to a space using the & operator,

which in turn is appended to the last four characters.

Line 15 sets myByte to -5 and lines 17 through 22 format the output and
display itto the screen. The program is ended in the usual manner.

When you run the program the following output is displayed.

myByte = 5 which is binary 0000 0101

myByte =5

which is binary 1111 1011

Output 5.3: Output of signbit.bas

You can see that the output for -5 matches the Two's Complement form. We
canconfirm this by negating 1111 1011 which results in 0000 0100 and
adding 1 whichresults in 0000 0101, or positive 5.

Why is this important? Signed data types have a smaller range of values
thanunsigned data types because a bit is being used to represent the
sign of the number. Ifyou are needing to store a large number of data
values, such as ids, in a byte or integer,

the number of possible values you can store depends on whether it is
signed orunsigned. If the number of values needed exceed the range of a
signed data type, thenuse an unsigned data type.

A Look Ahead 
-------------

There are times when you need to manipulate individual bits and bytes of
avariable. FreeBasic has a rich set of bitwise operators and macros that
you will see in thenext chapter.

Chapter 6 Bitwise Operators 
============================

FreeBasic includes a number of operators that manipulate the bits of a
number.

The following table lists the bitwise operators in order of their
precedence. That is, thefirst row has the highest precedence while lower
rows have lower precedence.

Operator Syntax Truth Table Comments

Not (Bitwise negation) B = NOT expression NOT 0 = 1

NOT 1 = 0

Inverts operand bit;

turns a 1 into 0 and a 0

into 1.

And (Bitwiseconjunction)

B = expression ANDexpression

0 AND 0 = 0

1 AND 0 = 0

0 AND 1 = 0

1 AND 1 = 1

Result bit is 1 only ifboth operand bits are 1.

Or (Bitwisedisjunction)

B = expression ORexpression

0 OR 0 = 0

1 OR 0 = 1

0 OR 1 = 1

1 OR 1 = 1

Result bit is 1 if either

or both operand bits is1.

Xor (Bitwiseexclusion)

B = expression XORexpression

0 XOR 0 = 0

1 XOR 0 = 1

0 XOR 1 = 1

1 XOR 1 = 0

Result bit is 1 if operandbits are different.

Eqv (Bitwiseequivalence)

B = expression EQVexpression

0 EQV 0 = 1

1 EQV 0 = 0

0 EQV 1 = 0

1 EQV 1 = 1

Result bit is 1 if both

operand bits are 0 or 1.

Imp (Bitwiseimplication)

B = expression IMPexpression

0 IMP 0 = 1

1 IMP 0 = 0

0 IMP 1 = 1

1 IMP 1 = 1

Result bit is 0 if first bit

is 1 and second bit is 0,

otherwise result is 1.

Table 6.1: Bitwise Operators

The truth table column indicates the operation on the individual bits.
The order ofthe bits are not important except for the IMP operator which
tests the bits of the secondoperand using the bits from the first
operand.

The NOT Operator

You saw the NOT operator at work in the two's complement section. The
followingprogram performs the same two's complement operation.

1

Option Explicit

2

3

Dim As Byte myByte = 5

4

5

'5 in decimal and binary

6

Print "myByte:";myByte," Binary: ";Bin(myByte)

7

'Apply NOT operator

8

myByte = Not myByte

9

'Value after NOT operation

10

Print "NOT myByte: ";myByte," Binary: ";Bin(myByte)

11

'Add 1 after NOT operation

12

myByte = myByte + 1

13

'Print result = 5

in decimal and binary

14

Print "myByte + 1: ";myByte," Binary: ";Bin(myByte)

15

16

Sleep

17

End

Listing 6.1: not.bas

Analysis: In line 3 the working variable myByte is declared and
initialized using thealternate format of the Dim statement. Line 6
prints out the value of myByte in bothdecimal and binary. In line 8 the
NOT operator is used to negate all the bits in the integer.

The result of the operation is printed to the console window in line 10.
In line 12, 1 isadded to the result as required by the two's complement
method. The result of thisoperation id printed in line 14. The program
is closed in the usual way.

When the program is run, you should see the following output.

myByte: 5 Binary: 101

NOT myByte: 6

Binary: 11111010

myByte + 1: 5

Binary: 11111011

Output 6.1: Output of not.bas

 As you can see from the output, the final result of the program is -5
after applyingthe twos complement method to myByte. The 1 in the
leftmost position indicates that thenumber is negative. Bin doesn't add
the leading zeros in the first output line, but thethree digits shown
are the rightmost three digits.

The AND Operator 
-----------------

The AND operator can be used to test if an individual bit is 1 or 0 by
using a maskvalue to test for the bit position as the following program
illustrates.

1

Option Explicit

2

3

'Declare working variable and mask value

4

'The mask will test the 3rd bit position, i.e. 4

5

Dim As Byte myByte = 5, Mask = 4

6

'Print decimal and binary values

Print "Testing 3rd bit position (from right)"

Print "myByte:";myByte," Binary: ";Bin(myByte)

Print "Mask: ";Mask," Binary: ";Bin(Mask)

'Check to see if 3rd bit is set

If (myByte And Mask) = 4 Then

Print "3rd bit is 1"

Else

 Print "3rd bit is 0"

End If

Print

'The mask will test the 2nd bit position, i.e. 2

Mask = 2

'Print decimal and binary values

Print "Testing 2nd bit position (from right)"

Print "myByte:";myByte," Binary: ";Bin(myByte)

Print "Mask: ";Mask," Binary: ";Bin(Mask)

'Check to see if 2nd bit is set

If (myByte And Mask) = 4 Then

Print "2nd bit is 1"

Else

Print "2nd bit is 0"

End If

Sleep

End

Listing 6.2: and.bas

Analysis: In line 5 the working variables are declared and initialized.
The firstsection of the program is testing for the third bit position of
myByte, which is bit 22, or

decimal 4. Lines 8 through 10 print out the heading, decimal and binary
values for thevariables. The If statement in line 13 uses the AND
operator to test for a 1 in the 3rd bit

position, and since binary 5 contains a one in this position, the
program will execute thecode immediately following the Then keyword.

Line 21 sets the mask value to 2 to test for a 1 in the second bit
position, which is

21 or 2. Line 23 through 25 print out the header, decimal and binary
values of thevariables. :ine 28 uses the AND operator to test for a 1,
and since binary 5 has a 0 in thisposition, the program will execute the
code immediately following hr Else keyword.

Running the program produces the following output.

Testing 3rd bit position (from right)

myByte: 5 Binary: 101

Mask: 4 Binary: 100

3rd bit is 1

Testing 2nd bit position (from right)

myByte: 5 Binary: 101

Mask: 2 Binary: 10

2nd bit is 0

Listing 6.3: Output of and.bas

Looking at the binary values you can see how the bits line up and how
the ANDoperator can test for individual bits. 5 in binary has a bit set
in the 20 (1) and 22 (4)

position. Setting the mask value to 4 sets bit position 22 to 1 and all
other bit positions to

0\. The expression (myByte And Mask) will return an integer value that
will contain theAND values of the two operands. Since the mask has zeros
in every position except forthe 22 position, all of the other bits will
be masked out, that is 0, returning a 4. Since thereturn value of 4
matches the target value 4, the code following the Then clause
isexecuted. 

The second portion of the program test for the 21 position of myByte.
Since thisposition contains a 0 in myByte, the value returned from the
expression (myByte And

Mask) does not match the target value, so the code following the Else
clause if executed.

The OR Operator 
----------------

You can use the OR operator to set multiple values in a single variable.
TheWindows API uses this technique to set flags for objects such as the
styles of a window.

The following program illustrates this concept.

1

Option Explicit

2

3

'Declare working variable

4

Dim As Byte myByte, Mask

5

6

'Set the flags in the byte

7

myByte = 2

8

myByte = myByte Or 4

9

'Print decimal and binary values

10

Print "myByte set to 2 and 4"

11

Print "myByte:";myByte," Binary: ";Bin(myByte)

12

Print

13

'Set the mask to 2

14

mask = 2

15

Print "Testing for 2"

16

'Check for 2 value

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

33

34

35

36

37

38

39

40

41

42

43

44

If (myByte And Mask) = 2 Then

Print "myByte contains 2"

Else

 Print "myByte doesn't contains 2"

End If

Print

'Set the mask value to 4

Mask = 4

'Print decimal and binary values

Print "Testing for 4"

If (myByte And Mask) = 4 Then

 Print "myByte contains 4"

Else

 Print "myByte doesn't contain 4"

End If

Print

'Set the mask value to 8

Mask = 8

'Print decimal and binary values

Print "Testing for 8"

If (myByte And Mask) = 8 Then

 Print "myByte contains 8"

Else

Print "myByte doesn't contain 8"

End If

Sleep

End

Listing 6.4: or.bas

Analysis: Line 4 declares the working variables. In line 7, myByte is
set to 2 and inline 8, that value is combined with 4 using the OR
operator. Lines 10 and 11 print out thedecimal and binary values of
myByte. In line 14, the mask is set to 2 and in lines 18through 22 the
AND operator is used to test for 2 in myByte. Since myByte contains a 2,

the program will execute the code immediately following the Then clause.
Lines 24through 31 use the same procedure to test for the value of 4.
Since myByte contains a 4,

the program will print out the text “myByte contains a 4”. In lines 34
through 41, myByteis tested for 8, which is does not contains so the
code in line 40 will be executed.

When you run the program, you should get the following output.

myByte set to 2 and 4

myByte: 6 Binary: 110

Testing for 2

myByte contains 2

Testing for 4

myByte contains 4

Testing for 8

myByte doesn't contain 8

Output 6.2: Output of or.bas

As you can see from the output, you can pack multiple values into a
singlevariable. The number of values a variable can contain depends on
the size of data typeand the range of values. Using the OR and AND
combination is a technique that you willfind in wide-spread use,
especially in third-party libraries, as it provides an efficient wayto
pass multiple data items using a single variable.

The XOR Operator

One of the more useful aspects of the XOR operator is to flip bits
between twostates. XORing a value with 0 will return the original value,
and XORing with a 1 returnsthe opposite value. Suppose that you start
with a 1 bit and XOR with a 0 bit. Since thetwo inputs are different you
will get a 1. If the start value is 0 and you XOR with a 0, thenboth
values are the same and you will get a 0. In both cases the output is
the same asthe input. If you start with a 1 and XOR with a 1, you will
get a 0 since both inputs are thesame. If you start with a 0 and XOR
with a 1, you will get a 1 since the inputs aredifferent. Here the
inputs have been flipped to the opposite values. You can use
thistechnique with a mask value, XORing once to get a new value, and
then XORing againwith the same mask to get the original value.

One use of this technique is to display a sprite on the screen using XOR
and thenerasing the sprite by using another XOR at the same location.
The first XOR combines thebits of the background with the sprite bits to
display the image. Another XOR in the samelocation flips the bits back
to their original state, once again showing the background
andeffectively erasing the sprite image.

XOR can also be used to swap the values of two variables as demonstrated
in thefollowing program.

1

Option Explicit

2

3

Dim As Integer myInt1 = 5, myInt2 = 10

4

5

Print "myInt1 = ";myInt1;" myInt2 = ";myInt2

6

Print "Swapping values..."

7

myInt1 = myInt1 Xor myInt2

8

myInt2 = myInt1 Xor myInt2

9

myInt1 = myInt1 Xor myInt2

10

Print "myInt1 = ";myInt1;" myInt2 = ";myInt2

11

12

Sleep

13

End

Listing 6.5: xor.bas

Analysis: In line 3 the working variables are declared and initialized.
Line 5 printsout the initial variable values. Lines 7 through 9 carry
out the XOR operation. In line 7,

MyInt1 is XORed with myInt2 to get an intermediate value which is stored
in myInt1. Inline 8, the XOR operation returns the original value of
myInt1 which is stored in myInt2.

The third XOR operation in line 9 then returns the value of myInt2 from
the intermediatevalue that was stored in myInt1 in line 7. Line 10
prints out the swapped values and theprogram is then closed in the usual
way.

Running the program produces the following output.

myInt1 = 5 myInt2 = 10

Swapping values...

myInt1 = 10 myInt2 = 5

Output 6.3: Output of xor.bas

As you can see the program was able to swap the two values without using
atemporary variable because the XOR operator is able to flip the bits
between two distinct

states.

The EQV Operator

The EQV operator isn't used much as a bitwise operator, but it can be
used to seeif two expressions are equivalent as the following program
demonstrates.

Option Explicit

\#define False 0

\#define True NOT False

Dim As Integer myInt1 = 4, myInt2 = 2

Print "myInt1 = ";myInt1;" myInt2 = ";myInt2

Print

'Both statements are true so are equivalent.

PRINT "Statement (myInt1 &lt; 5) eqv (myInt2 &gt; 1) ";

If (myInt1 &lt; 5) Eqv (myInt2 &gt; 1) = True Then

Print "is equivalent."

Else

Print "is not equivalent."

End If

Print

'Both statements are false so are equivalent.

Print "Statement (myInt1 &gt; 5) eqv (myInt2 &lt; 1) ";

If (myInt1 &gt; 5) Eqv (myInt2 &lt; 1) = True Then

Print "is equivalent."

Else

Print "is not equivalent."

End If

Print

'One is true, the other false so statement

'is not equivalent.

Print "Statement (myInt1 &gt; 5) eqv (myInt2 &lt; 1) ";

If (myInt1 &gt; 3) Eqv (myInt2 &lt; 1) = True Then

Print "is equivalent."

Else

Print "is not equivalent."

End If

SLEEP

End

Listing 6.6: eqv.bas

Analysis: In lines 3 and 4, the values False and True are defined.
FreeBasic uses -1

to indicate a True result from a logical operation such as that
performed when executingan If statement. Since False is defined as 0,
NOT False flips all the bits to 1, including thesign bit, making -1.

In line 6 the working variables are declared and initialized. Lines 12
through 18 testthe first expression. The If statement in line 13 will
execute the first expression, (myInt1&lt; 5). Since 4 &lt; 5 this will
return True. The EQV operator has lower precedence then(myInt2 &gt; 1),
so this will be evaluated, and since 2 &gt; 1 then will also return
true. Thisleaves -1 EQV -1 to be evaluated. Since -1 is equivalent to
-1, the whole statement isTrue. In line 22, both of the expressions are
False. 0 EQV 0 is True, so this statement isalso True and will print out
the affirmative. In line 32, the first expression is True while
thesecond is False. Since -1 is not equivalent to 0, this statement will
evaluate to False andthe negative will be printed.

When the program is run, you will see the following output.

myInt1 = 4 myInt2 = 2

Statement (myInt1 &lt; 5) eqv (myInt2 &gt; 1) is equivalent.

Statement (myInt1 &gt; 5) eqv (myInt2 &lt; 1) is equivalent.

Statement (myInt1 &gt; 5) eqv (myInt2 &lt; 1) is not equivalent.

Listing 6.7: Output of eqv.bas

It is important to realize that you are not testing to see if the
expressions are Trueor False. You are only testing to see if the
expressions are equivalent to each other. To putit another way, you are
testing to see if two assertions are equivalent to each other.
Forexample, suppose you have two characters in a game and you want to
attack with bothcharacters, if they are at equivalent strength. You
could build an expression similar to theone in the listing and take
action based on the equivalence of the two characters.

The IMP Operator

Like the EQV operator, IMP is rarely used as a bitwise operator. It is
used in logicprogramming to test whether assertion A implies assertion
B. Looking at the truth tablewe can see that a True assertion implies a
True conclusion so True and True is also True. ATrue assertion however
cannot imply a False conclusion so True and False is False. A
Falsepremise can imply any conclusion so False with any conclusion is
always True. Unless youare building an expert system or natural language
interface, you will probably never needto use this operator.

Caution Exercise caution when using bitwise operators with arithmetic
operators,

as the result may not be what you expect. When used in logical
expressions, such as inan If statement, make sure the bitwise operators
operate on either the True or Falsevalues of complete expressions to
avoid evaluation problems.

Shortcut Bitwise Operators

The bitwise operators, like the arithmetic operators, can be written in
shorthandform. The following table lists the shortcut versions of the
bitwise operators.

Operator Syntax Comment

And= B And= C This is the same as B = B

And C.

Or= B Or= C This is the same as B = B Or

C.

Xor= B Xor= C This is the same as B = B

Xor C.

Eqv= B Eqv = C This is the same as B = B

Eqv C.

Operator Syntax Comment

Imp= B Imp= C This is the same as B = B

Imp C.

Table 6.2: Shortcut Bitwise Operators

The SHL and SHR Operators

SHL stands for shift left and SHR stands for shift right. As the names
imply, theseoperators shift the bits of a byte or integer-type variable
either left or right. The followingtable shows the syntax diagram of
both operators.

Operator Syntax Comments

SHL (Shift bits left) B = variable SHL

number

Shifts the bits of variable left number of

places.

SHR (Shift bits right) B = variable SHR

number

Shifts the bits of variable right number ofplaces.

Table 6.3: SHL and SHR Operators

Shifting left is the same as multiplying by 2 and shifting right is the
same asdividing by 2. You can see this by looking at the binary
representation of a number. Takethe byte value of 1 which is 0000 0001.
The 1 is in the 20 position. 20 equals 1. Shifting

the bit left, makes 0000 0010, putting the 1 bit in the 21 position,
which evaluates to 2.

This is the same as 1\*2. Shifting left again puts the bit at the 22
position, 0000 0100which evaluates to 4, or 2 \*2. Shifting the bit
right puts the 1 back in the 21 position,

0000 0010, which evaluates to 2, or 4/2. Shifting right again puts the 1
bit in the 20

position, 0000 0001, which is 1 or 2/2.

The shift operation can be used as a replacement for multiplication or
division ifyou are working with powers of 2, but it is primarily used to
pack data items intovariables, or to retrieve data items from variables.
You saw this demonstrated in the

MAKDWORD macro which was defined as \#define MAKDWORD(x,y) (cint(x) shl
16 or

cint(y)).

In this macro, the value of x is converted to an integer, and then
shifted left 16 bitsinto the high word. An integer is 4 bytes and can be
represented as 00000000 00000000

00000000 00000001 . Shifting 16 bits left makes 00000000 00000001
00000000

00000000\. Remember that a word is two bytes, so the 1 has been shifted
to the highword of the integer. You can then use the Hiword function to
retrieve this value. 

The following program shows the SHL and SHR operators.

1

Option Explicit

2

3

Dim As Uinteger myInt = 1, i

4

5

'Multiply by powers of 2

6

Print "Shifting left..."

7

Print "myInt = ";myInt

8

For i = 1 To 89

myInt = myInt Shl 110

Print "myInt = ";myInt

11

Next

12

Print

13

'Divide by powers of 2

14

Print "Shifting right..."

15

Print "myInt = ";myInt

16

For i = 1 To 817

myInt = myInt Shr 118

Print "myInt = ";myInt

19

Next

20

21

Sleep

22

End

Listing 6.8: shlr.bas

Analysis: Line declares the working variables, myInt which will be he
value that isshifted, and i for use in the For-Next loop. Line 8 through
11 shift myInt left 16 times, 1 bitposition each time, and prints the
result. Line 15 through 19 then shift the variable right16 times and
prints the result. The program is closed in the usual way.

Running the program produces the following output.

Shifting left...

myInt = 1

myInt = 2

myInt = 4

myInt = 8

myInt = 16

myInt = 32

myInt = 64

myInt = 128

myInt = 256

Shifting right...

myInt = 256

myInt = 128

myInt = 64

myInt = 32

myInt = 16

myInt = 8

myInt = 4

myInt = 2

myInt = 1

Output 6.4: Output of shlr.bas

As you can see from the output, shifting left multiplies the value by 2
and shiftingright divides the value by 2.

Bitwise Macros

FreeBasic has several built-in macros for retrieving and setting bit and
byte datafrom a variable. The following tables lists the macros, the
syntax and their definitions.

Macro Syntax Definition

Hiword B = Hiword(variable) \#define Hiword(x) (CUInt(x) shr 16)

Loword B = Loword(variable) \#define Loword(x) (CUInt(x) and 65535)

Hibyte B = Hibyte(variable) \#define Hibyte(x) ((CUint(x) and 65280)

shr 8)

Lobyte B = Lobyte(variable) \#define Lobyte( x ) ( CUint( x ) and 255 )

Bit B = Bit( variable, bit\_number)

\#define Bit( x, bit\_number ) (((x) and (1shl (bit\_number))) &gt; 0)

Bitset B = Bitset(variable,

bit\_number)

\#define Bitset( x, bit\_number ) ((x) or (1shl (bit\_number)))

Bitreset B = Bitreset(variable,

bit\_number)

\#define Bitreset( x, bit\_number ) ((x) andnot (1 shl (bit\_number)))

Table 6.4: Bitwise Macros

The Hiword macro returns the leftmost two bytes of an integer and the
Lowordmacro returns the the rightmost two bytes. The Hibyte macro
returns the leftmost eightbits of a an integer and the Lobyte returns
the rightmost eight bits.

The Bit macro returns a -1 if a bit at position bit\_number is a 1,
otherwise it returnsa 0. The Bitset macro sets the bit at position
bit\_number to 1 and returns the number,

and the Bitreset macro sets the bit at position bit\_number to 0 and
returns the number.

The rightmost bit is bit 0 following the binary numbering scheme.

Caution Bitwise operators will only work correctly on byte and
integer-type data. Asingle or double-type variable that is passed to a
bitwise operator will be implicitlyconverted to an integer, which may
result in precision loss.

These macros are useful when working with third party libraries such as
theWindows API, where several pieces of information are stored in a
single data type.

A Look Ahead 
-------------

In addition to the arithmetic and bitwise operators, FreeBasic has a set
ofmathematical functions which is the subject of the next chapter.

Chapter 7 Mathematical Functions 
=================================

FreeBasic has a number of mathematical functions which are listed in the
following

table.

Function Syntax Comments

ABS (Absolute Value) B = Abs(expression) Returns the unsigned value of
expression.

This is an overloaded function so

expression can resolve to an integer,

longint or double.

ACOS (ArcCosine) B =

Acos(expression)

Returns the ArcCosine of a double-typeexpression in radians. Expression
must bein the range of -1 to 1.

ASIN (ArcSine) B = Asin(expression) Returns the ArcSine of a
double-typeexpression in radians. Expression must bein the range of -1
to 1.

ATAN2 (ArcTangent ofRatio)

B =

Atan2(expressionV,

expressionH)

Returns the ArcTangent of of ratio ofdouble-type expression1 /
expression2 inradians. ExpressionV is the verticalcomponent and
expressionH is thehorizontal component, where bothexpressions are
double-type values.

ATAN (ArcTangent) B =

Atan(expression)

Returns the ArcTangent of a double-typeexpression in radians. Expression
must bein the range of -Pi/2 to Pi/2.

COS (Cosine) B = Cos(expression) Returns the Cosine of a
double-typeexpression in radians. Expression must bein the range of -1
to 1 and is the anglemeasured in radians.

EXP (E Exponent) B = Exp(expression) Returns e (approx 2.716) raised to
thepower of a double-type expression.

LOG (Logarithm) B = Log(expression) Returns the natural Logarithm (base
e) ofa double-type expression.

SGN (Sign) B = Sgn(expression) Returns the sign of a
double-typeexpression. If expression is greater than 0then Sgn returns a
1. If expression is 0,

then Sgn returns 0. If expression is lessthan 0, then Sgn return -1.

SIN (Sine) B = Sin(expression) Returns the Sine of a
double-typeexpression in radians. Expression must bein the range -1 to
1.

SQR (Square Root) B = Sqr(expression) Returns the square root of a
double-type

Function Syntax Comments

expression. Expression must be greaterthan or equal to 0.

TAN (Tangent) B = Tan(expression) Returns the Tangent of a
double-typeexpression in radians. Expression is theangle measured in
radians.

Table 7.1: Mathematical Functions

Trigonometric Functions 
------------------------

All of the trigonometric functions return the measured angle in radians
notdegrees. To convert degrees to radians you would use the formula
radian = degree \* PI /

180\. To convert radians to degrees you would use the formula degree =
radian \* 180 / PI.

PI is the ratio of the circumference of a circle to its diameter and can
be calculated usingthe Atn function with the formula PI = 4 \* Atn(1.0).
The following short program convertsan angle in degrees to an angle in
radians.

1

Option Explicit

2

3

'Calc the value of Pi

4

Const Pi = 4 \* Atn(1)

5

6

Dim As Double deg, rad

7

8

'Get the angle in degrees

9

Input "Enter an angle in degrees";deg

10

11

'Calculate the radian

12

rad = deg \* Pi / 180

13

14

'Print out the values

15

Print

16

Print "Pi:";Pi

17

Print "Degrees:";deg

18

Print "Radians:";rad

19

20

Sleep

21

End

Listing 7.1: degrad.bas

Analysis: In line 4 a symbolic constant is declared for PI using the Atn
function. Line

6 declares the working variables. In line 9, the user inputs the degrees
to convert toradians. Line 12 calculates the radian angle based on the
conversion formula listedabove. Lines 15 through 18 print out the
various values. The program is then ended inthe usual way.

Running the program will produce the following output.

Enter an angle in degrees? 90

Pi: 3.14159265358979

Degrees: 90

Radians: 1.5707963267949

Output 7.1: Output of degrad.bas

There are a number of on-line tutorials that you can access to brush up
on your trig. Aquick Google search on the term trigonometry brought up
hundreds of sites that offerbasic to advanced tutorials on the various
trig functions that FreeBasic supports. RandyKeeling has written two
basic tutorials on trigonometry in the Community Tutorialssection of the
FreeBasic wiki. At the time of this writing, the wiki was located
athttp://www.freebasic.net/wiki/wikka.php?wakka=FBWiki.

Absolute Value and the Sgn Function 
------------------------------------

You would use the Abs function when you are interested in the absolute
magnitudeof a number. The absolute value of a number is the distance
that number is from zero on

the real number line. 3 is three units from 0 so its absolute magnitude
is 3. -3 is alsothree units from 0 so its absolute magnitude is also 3.

The Sgn function, called the signum function in math, is related to the
Abs functionsince you can express the absolute value of a number by
using the Sgn function. Sgnreturns -1 for a negative number, 0 for 0 and
1 for a positive number. To calculate theabsolute value of a number you
would use the formula |a| = a \* Sgn(a), where thevertical lines
indicate absolute value. If we replace a with -3 in the formula, you get
|-3| =

-3 \* Sgn(-3), or |-3| = -3 \* -1. Since multiplying a negative with a
negative returns apositive, the result is |-3| = 3. Replacing a with 3,
the formula would evaluate to |3| = 3 \*

1, or |3| = 3.

One use of the Sgn function in programming is determining the relative
positionsof two points on the screen. If you have two points, A(5, 6,)
and B(3, 4), where the firstnumber is the row and the second number is
the column, you can determine the relativeposition by moving the origin
to point A and looking at the sign of point B. The origin (0,0) of the
screen is located in the upper left corner. To move the origin to point
A you needto subtract 5 from the row and 6 from the column of each point
giving A(0, 0) and B(-2,

-2). You can now use the Sgn function on the row and column components
of B.

.

If Sgn(B.row) = -1, then the row is above A.

.

If Sgn(B.row) = 0, then the row is in the same row as A.

.

If Sgn(B.row) = 1 then the row is below A.

.

If Sgn(B.column) = -1 then the column is to the left of A.

.

If Sgn(B.column) = 0 then the column is in the same column as A.

.

If Sgn(B.column) = -1 then the column is to the right of A.

Since B is located at row -2 and column -2 after adjusting the origin,
the Sgnfunction will return -1 for the row and -1 for the column. This
puts point B above and tothe left of of point A.

Logarithms

Logarithmshave a wide range of uses in mathematics, physics and biology.
Forexample, the decay rate of radioactive particles is logarithmic in
nature. Logarithms are away of expressing exponentiation. For the
following formula Ab = x can be expressed asLog(x) = b where the base of
the log is a. The two most commonly used logarithms arethe natural log,
which uses e (2.7182818284590452354...) as the base, and log base 10or
the common log. The Log function in FreeBasic uses the natural log, but
any log basecan be expressed by the formula logarithm = Log(number) /
Log(base)2.

One property of logarithms is that they can be used to multiply or
divide twonumbers together. This was a common use of logarithms before
the invention ofcalculators. The following program uses the logarithm
method to multiply two numberstogether.

1

Option Explicit

2

3

Const base10 = Log(10)

4

5

Dim As Double l1, l2, lt, al

6

7

'Calculate the log of 2.5 for base 10

8

l1 = Log(2.5) / base10

9

'Calculate the log of 5.6 for base 10

10

l2 = Log(5.6) / base10

11

12

'Add the logarithms

13

lt = l1 + l2

14

15

'Get the antilog, which is our base (10)

16

'raised to the sum of the log values

17

al = 10\^lt

18

19

'Print results

20

Print "2.5 \* 5.6 = ";2.5 \* 5.6

21

Print "Log method = ";al

22

23

Sleep

24

End

Listing 7.2: log.bas

2For an explanation of the natural log and e see
http://www.physics.uoguelph.ca/tutorials/LOG/logbase.html.

Analysis: Line 3 defines a symbolic constant, base10, that will be the
base of thelogarithm calculations. Using a constant in this manner
reduces the number ofcalculations the program must perform. Instead of
using two Log(10) function calls, onlyone is used in the constant
definition. Line 5 declares the working variables, l1 an l2which are the
two Logarithms of the numbers 2.5 and 5.6 and the sum of the logs, lt.
alwill be the antilog value.

Lines 8 and 10 calculate the base 10 log of the two numbers. In line 13
thelogs are added together. Line 17 calculates the antilog, which is the
base, in this case 10,

raised to the power of the sum of the logs. Line 20 prints the result
using themultiplication operator, and line 21 prints the result using
the log method.

The program is closed in the usual way in lines 23 and 24.

Running the program produces the following result.

2.5 \* 5.6 = 14

Log method = 14

Output 7.2: Output of log.bas

As you can see from the output, adding the logarithms of the two numbers
andthen calculating the antilog of the sum produces the same result as
multiplying the twonumbers.

The C Runtime Library Math Constants and Functions 
---------------------------------------------------

The C Runtime Library (CRT) has a number of math constants and functions
thatyou can use in your programs. To use these functions you would add
the line \#Include

Once “crt.bi” to your program. The following table lists the math
constants available in

math.bi.

### CRT Math Constants 

Constants

M\_E

M\_LOG2E

M\_LOG10E

M\_LN2

M\_LN10

M\_PI

Value

2.7182818284590452354

1.4426950408889634074

0.43429448190325182765

0.69314718055994530942

2.30258509299404568402

3.14159265358979323846

Comment

The base of natural

logarithms.

The logarithm to base 2 ofM\_E.

The logarithm to base 10 ofM\_E.

The natural logarithm of 2.

The natural logarithm of 10.

Pi, which is the ratio of a

Constants

M\_PI\_2

M\_PI\_4

M\_1\_PI

M\_2\_PI

M\_2\_SQRTPI

M\_SQRT2

M\_SQRT1\_2

Table 7.2: CRT Math Constants

Value

1.57079632679489661923

0.78539816339744830962

0.31830988618379067154

0.63661977236758134308

1.12837916709551257390

1.41421356237309504880

0.70710678118654752440

Comment

circle's circumference to its

diameter.

Pi divided by two.

Pi divided by four.

The reciprocal of pi, that is1/pi.

Two times the reciprocal ofpi.

Two times the reciprocal ofthe square root of pi.

The square root of two.

The reciprocal of the squareroot of two which is also the

square root of 1/2.

In the example programs the value of PI was calculated. However, as you
can see,

the value of PI is available in the CRT, so it is much more efficient to
use the defined

value M\_PI in your programs, rather than making the compiler perform a
calculation forthe value. The same reasoning applies to the base 10
logarithm calculation that was usedin log.bas. Instead of calculating
the base 10 log you can use the constant value M\_LN10.

The various versions of the PI constants are commonly used values in
calculationsas are the versions of the square root of 2. The square root
of 2, like PI, is an irrationalnumber and is the length of the
hypotenuse of a right triangle with sides that have a unitlength of 1.
The square root of 2 is related to PI with the formula
sqrt(2)=2sin(PI/4). Thefollowing program displays both the calculated
value of the square root of 2 and the CRTvalue for comparison.

1

Option Explicit

2

3

\#Include Once "crt.bi"

4

5

Dim As Double sqr2

6

7

sqr2 = 2 \* Sin(M\_PI/4)

8

9

Print "Calculated Square root of 2:";sqr2

10

Print "CRT value:"; M\_SQRT2

11

12

Sleep

13

End

Listing 7.3: sr2.bas

Analysis: Line 3 includes the CRT declaration file, crt.bi, which will
enable the

program to use the math constants and functions. The \#Include Once
directive ensures

that the file is only included once in the program, even if other
modules also include thefile. Line 5 declares the working variable which
will hold the result of the calculation inLine 7. Line 9 and 10 displays
the calculated value as well as the CRT defined value forcomparison. The
program is closed in the usual way.

When you run the program you should see the following output.

Calculated Square root of 2: 1.41421356237309

CRT value: 1.4142135623731

Output 7.3: Output of sr2.bas

As you can see from the output, the calculated value has a slightly
higher precisionthan the constant value, but the difference is too small
to really matter in most cases. Tosave the compiler a calculation, and
thereby speeding up your program, use the definedvalue in the CRT.

### Selected CRT Math Functions 

There are a number of math functions declared in the CRT. Table 8.3 list
three of

the functions.

Function Syntax Comment

Hypot B = Hypot(x as double, y asdouble)

Hypot returns thehypotenuse of sides x and y.

Log10 B = Log10(x as double) Log10 returns the base 10log of x.

Pow B = Pow(base as double,

power as double)

Pow returns base raised to

power.

Table 7.3: Selected CRT Math Functions

The log program in Listing 8.2 can be modified to use the CRT functions.

Option Explicit

\#Include Once "crt.bi"

Dim As Double l1, l2, lt, al

'Calculate the log of 2.5 for base 10

l1 = Log10(2.5)

'Calculate the log of 5.6 for base 10

l2 = Log10(5.6)

'Add the logarithms

lt = l1 + l2

'Get the antilog, which is our base (10)

'raised to the sum of the log values

al = Pow(10, lt)

'Print results

Print "2.5 \* 5.6 = ";2.5 \* 5.6

Print "Log method = ";al

Sleep

End

Listing 7.4: log2.bas

Analysis: Line 3 includes the crt.bi declaration file so that the
runtime functions will

be available to the program. Line 5 declares the working variables as in
the previousprogram. In lines 8 and 10, the previous calculation has
been replaced with the CRTfunction log10. Line 13 adds the logarithms,
which is the same as multiplying the twonumbers, and saves the result in
the variable lt. In line 17 the Pow function is used rather

than the exponentiation operator to calculate the antilog. Lines 20 and
21 print out theresults for comparison. The program is closed in the
usual way.

When you run the program you will see that the output is the same as in
theprevious version.

2.5 \* 5.6 = 14

Log method = 14

Output 7.4: Output of log2.bas

Using the CRT functions can make your program a bit more simple, and a
bit lesserror prone. Since FreeBasic uses the Microsoft runtime library
the functions are stableand reliable, and many include optimizations
that make the functions perform better thanyou could achieve by hand
coding.

A Look Ahead 
-------------

In addition to the standard numeric variables, FreeBasic also has the
pointer datatype, which is the subject of the next chapter.

Chapter 8 Pointer Data Type 
============================

The pointer data type is unique among the FreeBasic numeric data types.
Insteadof containing data, like the other numeric types, a pointer
contains the memory addressof data. On a 32-bit system, the pointer data
type is 4 bytes. FreeBasic uses pointers for anumber of functions such
as ImageCreate, and pointers are used heavily in externallibraries such
as the Windows API. Pointers are also quite fast, since the compiler
candirectly access the memory location that a pointer points to. A
proper understanding ofpointers is essential to effective programming in
FreeBasic.

For many beginning programmers, pointers seem like a strange and
mysteriousbeast. However, if you keep one rule in mind, you should not
have any problems usingpointers in your program. The rule is very
simple: a pointer contains an address, not data.

If you keep this simple rule in mind, you should have no problems using
pointers.

Pointers and Memory 
--------------------

You can think of the memory in your computer as a set of post office
boxes (P.O.

Box) at your local post office. When you go in to rent a P.O. Box, the
clerk will give you anumber, such as 100. This is the address of your
P.O. Box. You decide to write the numberdown an a slip of paper and put
it in your wallet. The next day you go to the post officeand pull out
the slip of paper. You locate box 100 and look inside the box and find a
nicestack of junk mail. Of course, you want to toss the junk mail, but
there isn't a trash canhandy, so you decide to just put the mail back in
the box and toss it later. Working withpointers in FreeBasic is very
similar to using a P.O. Box.

When you declare a pointer, it isn't pointing to anything which is
analogous to theblank slip of paper. In order to use a pointer, it must
be initialized to a memory address,

which is the same as writing down the number 100 on the slip of paper.
Once you havethe address, find the right P.O. Box, you can dereference
the pointer, open the mail box,

to add or retrieve data from the pointed-to memory location. As you can
see there arethree basic steps to using pointers.

1\. Declare a pointer variable. 

2\. Initialize the pointer to a memory address. 

3\. Dereference the pointer to manipulate the data at the pointed-to
memory location. 

This isn't really any different than using a standard variable, and you
use pointersin much the same way as standard variables. The only real
difference between the two isthat in a standard variable, you can access
the data directly, and with a pointer you mustdereference the pointer to
interact with the data. The following program illustrates theabove
steps.

1

Option Explicit

2

3

'Create a pointer doesn't

point to anything.

4

Dim myPointer As Integer Ptr

5

6

'Initialize the pointer to point to 1 integer

7

myPointer = Callocate(1, Sizeof(Integer))

8

'Print the address

9

Print "Pointer address:";myPointer

10

'Add some meaningful data

11

\*myPointer = 10

12

'Print the contentswill

not be garbage

13

Print "Memory location contains:";\*myPointer

14

'Deallocate the pointer

15

Deallocate myPointer

16

17

Sleep

18

End

Listing 8.1: basicpointer.bas

Analysis: In line 4 a pointer to an integer is created. The pointer
doesn't point to amemory location yet, and if you were to try and use
this uninitialized pointer, you wouldgenerate an error. Line 7 uses the
Callocate function to set aside memory equal to thesize of an integer,
that is 4 bytes, and returns the starting address of the memorysegment.
The second parameter passed to Callocate is the size of the memory unit
toallocate. The first parameter is the number of units to allocate. In
this program, one unitof size integer is being allocated.

Now that myPointer has been initialized, you can use it. Line 9 prints
out contentsof myPointer which illustrates that the variable contains a
memory address and not data.

In line 11 data is added to the memory location using the indirection
operator \*. Theindirection operator tells the compiler you want to work
with the data that myPointer ispointing to, rather than the memory
address contained in the variable. Line 13 prints outthe contents of the
memory location which is now 10.

In line 15, the memory allocated with Callocate is freed using the
Deallocateprocedure. The program is closed in the usual way.

Running the program should produce a result similar to the following
output.

Pointer address:3089536

Memory location contains: 10

Output 8.1: Output of basicpointer.bas

The address printed on your computer will probably be different, since
theoperating system allocates the memory used by Callocate.

When your program terminates, all memory that was allocated in the
program is freedand returned to the operating system. However, it is
good practice to deallocatememory when it is no longer needed, even if
it isn't strictly necessary when a programterminates. The better you
manage your program's memory, the less chance ofproblems you will have
when running the program on different computer configurations.

Typed and Untyped Pointers 
---------------------------

FreeBasic has two types of pointers, typed and untyped. The preceding
programdeclared a typed pointer, Dim myPointer as Integer Ptr, which
tells the compiler thatthis pointer will be used for integer data. Using
typed pointers allows the compiler to dotype checking to make sure that
you are not using the wrong type of data with thepointer, and simplifies
pointer arithmetic.

Untyped pointers are declared using the Any keyword: Dim myPointer as
Any

Ptr Untyped pointers have no type checking and default to size of byte.
Untyped pointersare used in the C Runtime Library and many third party
libraries, such as the Win32 API,

to accommodate the void pointer type in C. You should use typed pointers
so that thecompiler can check the pointer assignments, unless working
with libraries that requirethe void pointer.

Pointer Operators 
------------------

There are two pointer operators in FreeBasic; the indirection operator
and theaddressof operator.

Operator Syntax Comment

\* (Indirection)

\[ \] (Index Access)

B = \*myPointer

\*myPointer = B

B = myPointer\[index\]

myPointer\[index\] = B

You can access the data in a

pointer memory location byeither using the indirectionoperator or using
indexaccess. The index format

uses the size of the data

type to determine theproper indexing.

@ (AddressOf) myPointer = @myVar

myPointer = @mySub()

myPointer = @myFunction()

Returns the memoryaddress of a variable,

subroutine or function.

Table 8.1: Pointer Operators

You will notice that the addressof operator not only returns the memory
address ofa variable, but it can also return the address of a subroutine
or function. You would use

the address of a subroutine or function to create a callback function
such as used in the

CRT function qsort. Callback functions will discussed later in this
chapter.

Memory Functions 
-----------------

FreeBasic has a number of memory allocation functions that are used
withpointers, as shown in the following table.

Function Syntax Comment

Allocate myPointer =

Allocate(number\_of\_bytes)

Allocates number\_of\_bytesand returns the memory

Function Syntax Comment

address. If myPointer is 0,

the memory could not beallocated. The allocated

memory segment is notcleared and contains

undefined data.

Callocate myPointer =

Callocate(number\_of\_elements, size\_of\_elements)

Callocate allocates

number\_of\_elements that

have size\_of\_elements and

returns the memoryaddress. If the memorycould not be allocated,

Callocate will return 0. The

memory segment allocatedis cleared.

Deallocate Deallocate myPointer Frees the memory segmentpointed to by
myPointer.

Reallocate myPointer =

Reallocate(pointer,

number\_of\_bytes)

Reallocate changes the sizeof a memory segmentcreated with Allocate or

Callocate. If the new size is

larger than the existingmemory segment, thecontents of the memorysegment
remainedunchanged. If the new sizeis smaller, the contents of

the memory segment aretruncated. If pointer is 0,

Reallocate behaves just likeAllocate. A 0 is returned if

the memory segmentcannot be changed.

Table 8.2: FreeBasic Memory Functions

These functions are useful for creating a number of dynamic structures
such aslinked lists, ragged or dynamic arrays and buffers used with
third party libraries.

When using the Allocate function you must specify the storage size based
on thedata type using the equation number\_of\_elements \*
Sizeof(datatype). To allocate

space for 10 integers your code would look like this: myPointer =
Allocate(10 \*

Sizeof(Integer)). An integer is 4 bytes so allocating 10 integers will
set aside 40 bytesof memory. Allocate does not clear the memory segment,
so any data in the segment willbe random, meaningless data until it is
initialized.

Callocate works in the same fashion, except that the calculation is done
internally.

To allocate the same 10 integers using Callocate your code would look
like this:

myPointer = Callocate(10, Sizeof(Integer)). Unlike Allocate, Callocate
will clear

the memory segment.

Reallocate will change the size of an existing memory segment, making it
larger orsmaller as needed. If the new segment is larger than the
existing segment, then the datain the existing segment will be
preserved. If the new segment is smaller than the existingsegment, the
data in the existing segment will be truncated. Reallocate does not
clearthe added memory or change any existing data.

All of these functions will return a memory address if successful. If
the functionscannot allocate the memory segment, then a NULL pointer (0)
is returned. You shouldcheck the return value each time you use these
functions to be sure that the memorysegment was successfully created.
Trying to use a bad pointer will result in undesirablebehavior or system
crashes.

There is no intrinsic method for determining the size of an allocation;
you mustkeep track of this information yourself.

Caution Be careful not to use the same pointer variable to allocate two
or morememory segments. Reusing a pointer without first deallocating the
segment it points towill result in the memory segment being lost causing
a memory leak.

Pointer Arithmetic and Pointer Indexing 
----------------------------------------

When you create a memory segment using the allocation functions, you
will need away to access the data contained within the segment. In
FreeBasic there are twomethods for accessing data in the segment; using
the indirection operator with pointerarithmetic, and pointer indexing.

Pointer arithmetic, as the name suggests, adds and subtracts values to a
pointer toaccess individual elements within a memory segment. When you
create a typed pointersuch as Dim myPointer as Integer ptr, the compiler
knows that the data being usedwith this pointer is of size Integer or 4
bytes. The pointer, when initialized, points to thefirst element of the
segment. You can express this as \*(myPtr + 0). To access the
secondelement, you need to add 1 to the pointer, which can be expressed
as \*(myPtr + 1).

Since the compiler knows that the pointer is an Integer pointer, adding
1 to the pointerreference will actually increment the address contained
in myPtr by 4, the size of anInteger. This is why using typed pointers
is preferable over untyped pointers. Thecompiler does much of the work
for you in accessing the data in the memory segment.

Notice that the construct is \*(myPtr + 1) and not \*myPtr + 1. The \*
operator hashigher precedence than +, so \*myPtr + 1 will actually
increment the contents myPtrpoints to, and not the pointer address.
\*myPtr will be evaluated first, which returns thecontents of the memory
location and then +1 will be evaluated, adding 1 to the memorylocation.
By wrapping myPtr + 1 within parenthesis, you force the compiler to
evaluatemyPtr + 1 first, which increments the pointer address, and then
the \* is applied to returnthe contents of the new address.

Pointer indexing works the same way as pointer arithmetic, but the
details arehandled by the compiler. \*(myPtr + 1) is equivalent to
myPtr\[1\]. Again, since thecompiler knows that myPtr is an integer
pointer, it can calculate the correct memoryoffsets to return the proper
values using the index. Which format you use if up to you, butmost
programmers use the index method because of its simplicity.

The following program shows both methods of accessing a memory segment.

Option Explicit

Dim myPtr As Integer Ptr

Dim As Integer i

'Try and allocate space for 10 integers

myPtr = Callocate(10, Sizeof(Integer))

'Make sure the space was allocated

If myPtr = 0 Then

Print "Could not allocate space for buffer."

End 1

End If

'Load data into the buffer

Print "Loading data, print data using \*..."

For i = 0 To 9

 \*(myPtr + i) = i

 Print "Index:";i;" data:";\*(myPtr + i)

Next

Print

'Print data from buffer

Print "Show data using indexing..."

For i = 0 To 9

 Print "Index:";i;" data:";myPtr\[i\]

Next

'Free the memory

Deallocate myPtr

Sleep

End

Listing 8.2: ptraccess.bas

Analysis: In lines 3 and 4 the working variables are declared. Space for
10 integersis created in Line 7 using the Callocate function. Lines 10
through 13 check to make surethat the memory was allocated. If it
wasn't, the program ends. The End 1 terminates theprogram with an exit
code of 1. This is useful for instances where the program may berun from
a batch file and you want to make sure the program ran successfully. You
cancheck the exit code in the batch file and take the appropriate
action.

Lines 17 through 20 load and print the memory segment with ten integers
usingthe indirection operator and pointer arithmetic. Lines 25 through
27 print out the valuesusing the index method. Notice that the index
method is much more compact and easierto read. In line 30 the buffer is
deallocated, even though it isn't strictly necessary as theprogram is
terminating. Deallocating memory is a good habit to get into, even when
itmay not be strictly necessary. The program is closed in the usual way.

When you run the program you should see the following output.

Loading data, print data using \*...

Index: 0 data: 0

Index: 1 data: 1

Index: 2 data: 2

Index: 3 data: 3

Index: 4 data: 4

Index: 5 data: 5

Index: 6 data: 6

Index: 7 data: 7

Index: 8 data: 8

Index: 9 data: 9

Show data using indexing...

Index: 0 data: 0

Index: 1 data: 1

Index: 2 data: 2

Index: 3 data: 3

Index: 4 data: 4

Index: 5 data: 5

Index: 6 data: 6

Index: 7 data: 7

Index: 8 data: 8

Index: 9 data: 9

Output 8.2: Output of ptraccess.bas

As you can see from the output, both formats produce the same results,
but the

index method is a lot easier to read and understand, and less
error-prone than the

indirection method.

Pointer Functions 
------------------

Freebasic has a set of pointer functions to complement the pointer
operators. Thefollowing table lists the pointer functions.

Function Syntax Comment

Cptr myPtr = Cptr(data\_type,

expression)

Converts expression to adata\_type pointer.

Expression can be another

Function Syntax Comment

pointer or an integer.

Peek B = Peek(data\_type,

pointer)

Peek returns the contents of

memory location pointer toby pointer. Data\_typespecifies the type
ofexpected data.

Poke Poke data\_type, pointer,

expression

Puts the value of expressioninto the memory locationpointed to by
pointer. Thedata\_type specifies the typeof data being placed intothe
memory location.

Sadd myPtr =

Sadd(string\_variable)

Returns the location in

memory where the stringdata in a dynamic string islocated.

Strptr myPtr =

Strptr(string\_variable)

The same as Sadd.

Procptr myPtr = Procptr(function) Returns the address of a

function. This works the

same way as the addressofoperator @.

Varptr myPtr = Varptr(variable) This function works the

same way as the addressofoperator @.

Table 8.3: Pointer Functions

The Sadd and Strptr functions will be discussed in the chapter on the
string datatypes. The Peek and Poke functions have been added for the
purposes of supportinglegacy code. Procptr and Varptr both work just
like the address of operator, but Proptronly works on subroutines and
functions and Varptr only works on variables. Cptr is usefulfor casting
an untyped pointer to a typed pointer, such as a return value from a
thirdparty library.

Subroutine and Function Pointers 
---------------------------------

Subroutines and functions, like variables, reside in memory and have an
addressassociated with their entry point. You can use these addresses to
create events in yourprograms, to create pseudo-objects and are used in
callback functions. You create a subor function pointer just like any
other pointer except you declare your variable as apointer to a
subroutine or function rather than as a pointer to a data type. Before
using afunction pointer, it must be initialized to the address of a
subroutine or function usingProcptr or @. Once initialized, you use the
pointer in the same manner as calling theoriginal subroutine or
function. The following program illustrates declaring an using afunction
pointer.

Option Explicit

'Declare our function to be used with pointer

Declare Function Power(number As Integer, pwr As Integer) As Integer

'Dim a function pointer

Dim FuncPtr As Function(x As Integer, y As Integer) As Integer

'Get the address of the function

FuncPtr = @Power

'Use the function pointer

Print "2 raised to the power of 4 is";FuncPtr(2, 4)

Sleep

End

'Write the function that will be called

Function Power(number As Integer, pwr As Integer) As Integer

Return number\^pwr

End Function

Listing 8.3: funcptr.bas

Analysis: Line 4 declares the function prototype that will be used with
the functionpointer. Line 7 declares the function pointer using the the
As Function syntax. Notice thatthe Dim statement does not use the Ptr
keyword; the compiler knows that this will be afunction pointer since it
is declared using the As Function method. When declaring afunction
pointer, the parameter list must match the number and type of parameters
ofthe pointed-to function, but as you can see, the names do not have to
match. In fact, thepointer can be declared as Dim FuncPtr As Function(As
Integer, As Integer) As

Integer, without the parameter names. The only requirement is to make
sure that thetype and number of parameters, and the return type, match
the function declaration anddefinition. Line 10 initializes the function
pointer to the address of the function using theaddress of operator @.
You could use Procptr here as well. Line 13 uses the pointer tocall the
function. The calling syntax is the same as using the function name:
FuncPtr(2,4)

is equivalent to Power(2, 4). Lines 15 and 16 close the program in the
usual way. Lines 19through 21 define the actual Power function.

Running the program will produce the following result.

2 raised to the power of 4 is 16

Listing 8.4: Output of funcptr.bas

While this example program may not seem to have any advantages over
justcalling the function directly, you can use this method to call
several functions using asingle function pointer. For example, if you
were creating your own user interface, youcould implement events using a
function pointer that called one of several differentsubroutines
depending on the object receiving the event. The only requirement would
bethat each subroutine must contain the same number and type of
parameters.

Creating a Callback Function 
-----------------------------

One of the primary uses for function pointers is to create callback
functions. Acallback function is a function that you have created in
your program that is called by afunction or subroutine in an external
library. Windows uses callback functions toenumerate through Window
objects like fonts, printers and forms. The qsort, functioncontained
within the C Runtime Library sorts the elements of an array using a
callbackfunction to determine the sort order. The prototype for the
qsort function is contained instdlib.bi:

declare sub qsort cdecl alias "qsort" (byval as any ptr, byval as
size\_t,

byval as size\_t, byval as function cdecl(byval as any ptr, byval as any

ptr) as integer)

The following lists the parameter information for the qsort subroutine.

1\. The first parameter is the address to the first element of the array.
The easiest wayto pass this information to qsort is to append the
address of operator to the firstelement index: @myArray(0). 

2\. The second parameter is the number of elements in the array, that is
the array 

count.

3\. The third parameter is the size of each element in bytes. For an
array of integers,

the element size would be 4 bytes.

4\. The fourth parameter is a function pointer to the user created
compare function.

The function must be declared using the Cdecl passing model, as shown in
this

parameter.

Using this information, you can see how qsort works. By passing the
address of thefirst element along with the count of elements, and the
size of each element, qsort caniterate through the array using pointer
arithmetic. Qsort will take two array elements,

pass them to your user defined compare function and use the compare
function's returnvalue to sort the array elements. It does this
repeatedly until each array element is insorted order. The following
program uses the qsort subroutine and a compare function tosort an array
of integers.

1

Option Explicit

2

3

\#include "crt.bi"

4

5

'Declare the compare function

6

'This is defined in the same manner as the qsort declaration

7

Declare Function QCompare Cdecl (Byval e1 As Any Ptr, Byval e2 As Any
Ptr) \_

8

As Integer

9

10

'Dimension the array to sort

11

Dim myArray(10) As Integer

12

Dim i As Integer

13

14

'Seed the random number generator

15

Randomize Timer

16

17

Print "Unsorted"

18

'Load the array with some random numbers

19

For i = 0 To 920

'Rnd returns a number between 0 and 1

21

'This converts the number to an integer22

myArray(i) = Int(Rnd \* 20)

23

'Print unsorted array24

Print "i = ";i;" value = ";myArray(i)

25

Next

26

Print

27

28

'Call the qsort subroutine

29

qsort @myArray(0), 10, Sizeof(Integer), @QCompare

30

Print

31

32

'Print sorted array.

33

Print "Sorted"

34

For i = 0 To 935

'Rnd returns a number between 0 and 1 to convert to integer36

Print "i = ";i;" value = ";myArray(i)

37

Next

38

39

Sleep

40

End

41

42

'The qsort function expects three numbers

43

'from the compare function:

44

'1:

if e1 is less than e2

45

'0: if e1 is equal to e2

46

'1: if e1 is greater than e2

47

Function QCompare Cdecl (Byval e1 As Any Ptr, \_

48

Byval e2 As Any Ptr) As Integer49

Dim As Integer el1, el250

Static cnt As Integer51

52

'Get the call count and items passed53

cnt += 154

'Get the values, must cast to integer ptr55

el1 = \*(Cptr(Integer Ptr, e1))

56

el2 = \*(Cptr(Integer Ptr, e2))

57

Print "Qsort called";cnt;" time(s) with";el1;" and";el2;"."

58

'Compare the values59

If el1 &lt; el2 Then60

Return 161

Elseif el1 &gt; el2 Then62

Return 163

Else64

Return 065

End If

66End Function

Listing 8.5: qsort.bas

Analysis: Line 3 includes the crt.bi file so that the qsort routine will
be available inthe program. You need to include this file if you want to
use any of the CRT functions.

Line 7 declares the compare function. You will notice that it is
declared as a Cdecl

function, which matches the 4th parameter definition in the qsort
declaration. Since qsortexpects to see either a -1, 0 or 1, the
function's return type is an integer. The undercorescharacter \_ at the
end of line 7 is the line continuation character and tells the
compilerthat the following line is actually a part of this line. In line
11 an array of integers isdimensioned. The array will have 10 elements,
with indexes from 0 to 9. Line 12dimensions a working variable i, that
will be used to load and display the array values.

Line 15 seeds the random number generator by using the value from the
Timerfunction. The Timer function returns the number of seconds, as a
double-type value,

since the computer was started. Lines 19 through 25 initializes the
array with somerandom integers and displays them to the console screen.
The code in line 22, Int(Rnd \*

20), uses the Rnd function which returns a double precision number
between 0 and 1.

That number is multiplied by twenty to produce a double-precision number
between 0and 20 which is then converted to an integer value using the
Int function. Since Intreturns the largest integer less than or equal to
the input, the resulting random numberswill range from 0 to 19. In line
24 the value of the current array index is printed to theconsole screen.

In line 29 the qsort subroutine is called. Since the array indexes range
from 0 to 9,

the address of operator on the zero index in used for the first
parameter. The array size is10, so that is used as the second parameter.
The array is an integer array, soSizeof(Integer) is used to pass the
array element size. The final parameter is the addressof the compare
function which is passed to qsort using the address of operator. Lines
34through 37 print out the now sorted array. Lines 39 and 40 close the
program in the usual

way.

Lines 47 through 66 contain the compare function code. In line 47 the
function isdefined just like the declare statement in line 7 using two
Any Ptr parameters andreturning an integer. The Any Ptrs allow qsort to
be able to sort any type of data,

including composite types. Lines 49 and 50 delcare the function's
working variables.

Qsort will pass pointers to the functions, not the actual data, so two
integers need to bedeclared so that the data that the pointers point to
can be compared. The variable cnt isdefined as Static so that its value
will be preserved between calls to the function. Cnt isused to keep
track of how many calls to the function qsort will make as it sorts the
array.

Lines 55 and 56 use the indirection operator to return the data from the
passedpointers. Notice the Cptr is used to convert the Any Ptr
parameters to Integer Ptrs beforeusing the indirection operator.
Remember that the code inside the parenthesis will beexecuted before
applying the indirection operator. Line 57 prints out the current
callcount and the passed parameter values.

Line 59 through 65 compare the two values and return the appropriate
indicatorvalue back to qsort. The Return statement, as expected, is used
to set the function'sreturn value. The function is closed using the End
Function keywords in line 66.

When you run the program you should something similar to the following.

Unsorted

i = 0 value = 14

i = 1 value = 18

i = 2 value = 2

i = 3 value = 14

i = 4 value = 3

i = 5 value = 15

i = 6 value = 16

i = 7 value = 4

i = 8 value = 10

i = 9 value = 19

Qsort called 1 time(s) with 18 and 15.

Qsort called 2 time(s) with 19 and 15.

Qsort called 3 time(s) with 10 and 15.

Qsort called 4 time(s) with 2 and 15.

Qsort called 5 time(s) with 14 and 15.

Qsort called 6 time(s) with 3 and 15.

Qsort called 7 time(s) with 14 and 15.

Qsort called 8 time(s) with 16 and 15.

Qsort called 9 time(s) with 4 and 15.

Qsort called 10 time(s) with 16 and 15.

Qsort called 11 time(s) with 4 and 15.

Qsort called 12 time(s) with 18 and 16.

Qsort called 13 time(s) with 19 and 18.

Qsort called 14 time(s) with 18 and 16.

Qsort called 15 time(s) with 10 and 4.

Qsort called 16 time(s) with 2 and 10.

Qsort called 17 time(s) with 14 and 10.

Qsort called 18 time(s) with 3 and 14.

Qsort called 19 time(s) with 14 and 14.

Qsort called 20 time(s) with 10 and 4.

Qsort called 21 time(s) with 2 and 10.

Qsort called 22 time(s) with 14 and 10.

Qsort called 23 time(s) with 3 and 14.

Qsort called 24 time(s) with 10 and 4.

Qsort called 25 time(s) with 2 and 10.

Qsort called 26 time(s) with 3 and 10.

Qsort called 27 time(s) with 3 and 4.

Qsort called 28 time(s) with 2 and 4.

Qsort called 29 time(s) with 3 and 2.

Sorted

i = 0 value = 2

i = 1 value = 3

i = 2 value = 4

i = 3 value = 10

i = 4 value = 14

i = 5 value = 14

i = 6 value = 15

i = 7 value = 16

i = 8 value = 18

i = 9 value = 19

Output 8.3: Output of qsort.bas

The first group of numbers show the unsorted array. The middle group of
numbersshow the number of times the compare function is called along
with the values beingsorted. The last group of numbers show the sorted
array. Even though qsort is calledquite a number of times even on this
small array, the routine is extremely fast since ituses pointers to sort
the values in the array.

Pointer to Pointer 
-------------------

In FreeBasic you can create a pointer to any of the supported data
types, includingthe pointer data type. A pointer to a pointer is useful
in situations where you need toreturn a pointer to a function or in
creating specialized data structures such as linked-listsand ragged
arrays. A pointer to a pointer is called multi-level indirection.

Caution You can have as many levels of indirection as needed, but
anythingbeyond two levels is rarely useful and difficult to manage.

One application of a pointer to pointer is the creation of memory
arrays. Thefollowing program demonstrates the creation, manipulation and
freeing of a memory

array.

1

Option Explicit

2

3

'Declare a pointer to an int pointer

4

Dim myMemArray As Integer Ptr Ptr

Dim As Integer i, j

6

7

'Create 10 rows of integer pointers

8

myMemArray = Callocate(10, Sizeof(Integer Ptr))

9

'Add 10 columns of integers to each row

11

For i = 0 To 912

myMemArray\[i\] = Callocate(10, Sizeof(Integer))

13

Next

14

'Add some data to the memory segment

16

For i = 0 To 917

For j = 0 To 918

myMemArray\[i\]\[j\] = Int(Rnd \* 10)

19

Next

Next

21

22

'Print out data

23

For i = 0 To 924

For j = 0 To 9

Print "i,j = ";i;",";j;" Mem Array =";myMemArray\[i\]\[j\]

26

Next

27

Next

28

29

'Free memory segment

For i = 0 To 931

Deallocate myMemArray\[i\]

32

Next

33

'Free the pointer to pointer

34

Deallocate myMemArray

36

Sleep

37

End

Listing 8.6: memarray.bas

Analysis: Line 4 dimensions a pointer to an integer pointer, myMemArray,
whichwill simulate a two dimensional array, with myMemArray pointing to
a list of integer

pointers. This list of pointers will comprise the “rows” of the array.
Line 5 just declaressome working variables that are used in the For-Next
loops later in the program.

 Line 8 creates the rows of the array by allocating a memory segment
that willcontain 4 integer pointers, which are initialized in lines 11
through 13. Remember thatthe index method of accessing a pointer
automatically does the pointer arithmetic foryou. The code in lines 11
through 13 iterates through the memory segment created inline 8 and
initializes the memory segment with pointers to memory segments that
willcontain integers. In other words, you have a pointer that is
pointing to a list of pointers.

These newly created memory segments are the columns for each row. Each
column indexwill be a pointer to a memory location containing an
integer.

Lines 16 through 20 add some random numbers to the memory array. Notice
thatby using the indexing method you can access the memory array just
like a normal array. ipoints to the row (the list of pointers) and j
points to the individual columns within thatrow which contain the
integer data. The same method is used in lines 23 through 27 toprint out
the array values.

Lines 30 through 32 free the individual rows of memory that were created
in line 8. It isimportant that each row be freed before freeing
myMemArray. If you were to just freemyMemArray, the rows would still be
in memory, but unaccessible, causing a memoryleak. Once all the rows
have been freed, myMemArray can be freed in line 34. Since theprogram is
terminating, Deallocating the memory is not strictly required in this
instance,

but if you needed to reuse the memory, then you must Deallocate in the
methoddescribed, otherwise you will get a memory leak while the program
is running. Lines 36and 37 close the program in the usual way.

Running the program should produce a result similar to the following.

i,j = 0, 1 Mem Array = 5

i,j = 0, 2 Mem Array = 1

i,j = 0, 3 Mem Array = 8

i,j = 0, 4 Mem Array = 5

i,j = 1, 0 Mem Array = 4

i,j = 1, 1 Mem Array = 3

i,j = 1, 2 Mem Array = 8

i,j = 1, 3 Mem Array = 8

i,j = 1, 4 Mem Array = 7

i,j = 2, 0 Mem Array = 1

i,j = 2, 1 Mem Array = 8

i,j = 2, 2 Mem Array = 7

i,j = 2, 3 Mem Array = 5

i,j = 2, 4 Mem Array = 3

i,j = 3, 0 Mem Array = 0

i,j = 3, 1 Mem Array = 0

i,j = 3, 2 Mem Array = 3

i,j = 3, 3 Mem Array = 1

i,j = 3, 4 Mem Array = 1

i,j = 4, 0 Mem Array = 9

i,j = 4, 1 Mem Array = 4

i,j = 4, 2 Mem Array = 1

i,j = 4, 3 Mem Array = 0

i,j = 4, 4 Mem Array = 0

Output 8.4: Output of memarray.bas

As you can see from the output, the memory array behaves exactly like
apredefined array. This structure is useful for adding dynamic arrays to
type definitions,

which normally cannot hold a dynamic array. You will see this in more
detail in thechapter on composite types.

One last note on this program. If you run the program more than once,
you willnotice that the values in the array are always the same, even
though the program isgenerating random numbers. This is because the
program did not seed the randomnumber generator using the Randomize
statement. To get different numbers for each run,

add Randomize Timer before calling the Rnd function.

A Look Ahead 
-------------

Pointers are an efficient and powerful data type, and you will be seeing
more ofthem in this book, including the next chapter where you will
explore the string data typesavailable in FreeBasic.

Chapter 9 String Data Types 
============================

Strings are an essential part of programming, and proper manipulation of
stringsis an essential skill for any programmer. You will need to use
strings in virtually everyprogram you will write, from games to data
entry programs. Strings are importantbecause humans use strings to
communicate concepts and ideas. A menu in a gamecommunicates the various
game options to the user. An address stored in a databasecommunicates
the location of the person who lives at that address. Programs
aresolutions to problems, and in most cases, must communicate that
solution to the userthrough the use of strings.

Computers however, only understand numbers. The string “¡FreeBasic
estáfresco!“ has no meaning to the computer. For the very first
computers this did not mattermuch, since those early computers were just
glorified calculators, albeit calculators thattook up a whole room.
However it soon became evident to computer engineers that inorder for
the computer to be a useful tool, it needed to be able to somehow
recognizestring data, and be able to manipulate that string data.

Since computers only understand numbers, the solution was to convert
alphanumeric

characters to numbers via translation tables. The familiar ASCII code
table is one

such translation scheme that takes a set of alpha-numeric characters and
converts themto numbers. The “A” character is encoded as decimal 65, the
exclamation point asdecimal 33 and the number 1 is encoded as decimal
49. When you press any key on yourkeyboard, a scancode for that key is
generated and stored in the computer as a number.

Humans group letters together to form words, and words to form
sentences. Acertain arrangement of letters and words mean something
according to the semanticrules the writer's language. When you read the
string “FreeBasic is cool!” you understandthe meaning of the words if
you can read the English language. The computer howeverdoesn't know what
FreeBasic is and doesn't know what it means to be cool. When youread
that something is “cool” you know that this is slang for great or
excellent. All thecomputer can do is store the string in memory in a way
that preserves the format of thestring so that a human reading the
string will understand its meaning.

While computers have grown in both speed and capacity, the basic
computingprocesses haven't changed since the 1950's. The next revolution
in computing won't bequantum processors or holographic memory; it will
be when computers can understandlanguage.

The solution to the storage problem was to simply store string data in
memory as asequence of bytes, and terminate that sequence of bytes with
a character 0. To put itanother way, a string in computer memory is an
array of characters, terminated with acharacter 0 to signal the end of
the string. Virtually all early programming languages, andmany modern
ones, have no native String data type. A string in C is a Null
(character 0)

terminated array of Char, where Char can be interpreted as both a
character and number.

While this scheme accurately reflects the internal structure of a string
in memory, it ishard to work with and error prone, and doesn't reflect
the way humans work with stringdata. A better solution to the problem
was the creation of the native String data type. Theinternal structure
of a string has not changed, it is still stored in memory as a sequence

of bytes terminated by a Null character, but the programmer can interact
with string datain a more natural, humanistic way.

FreeBasic has four intrinsic string data types, listed in the following
table.

String Type Declaration Purpose

Dynamic String Dim myString as String 8-bit string that isdynamically
allocated andautomatically resized.

Fixed Length String Dim myString as String \*

length

8-bit, fixed-length string.

Zstring Dim myString as Zstring \*

length

Dim myString as Zstring Ptr

8-bit, fixed-length, Nullterminated character string.

A Zstring is a C-style string.

Wstring Dim myString as Wstring \*

length

Dim myString as Wstring Ptr

16-bit, fixed-length, Nullterminated string used withUnicode functions.

Table 9.1: Intrinsic FreeBasic String Data Types

All FreeBasic strings can hold up to 2 GB of data, or up to the amount
of memory

on your computer.

Dynamic Strings 
----------------

Dynamic strings are variable-length strings that the compiler
automaticallyallocates and resizes as needed. Dynamic strings are
actually structures stored inmemory, called a string descriptor, that
contain a pointer to the string data, the length ofthe string data and
the size of the string allocation. Dynamic strings are allocated in
36byte blocks, which reduces the amount of resizing that the compiler
must do if the stringsize changes. The following program displays the
internal string structure data for atypical dynamic string3.

1

Option Explicit

2

3

'String descriptor

4

Type StringDesc5

strdata As Zstring Ptr6

length As Integer7

size As Integer

8

End Type

9

10

'Create a string

11

Dim As String myString = "This is a dynamic string in FreeBasic!"

12

'Dimension a pointer to the string descriptor

3String descriptor code provided by FreeBasic forum member cha0s.

13

Dim As StringDesc Ptr StringData = Cptr(stringdesc Ptr, @myString)

14

15

'Print string descriptor data

16

Print "Data: ";\*(StringData&gt;

strdata)

17

Print "Length: ";StringData&gt;

length

18

Print "Size: ";StringData&gt;

size

19

20

Sleep

21

End

Listing 9.1: dynastring.bas

Analysis: Lines 4 through 8 defines the string descriptor data type. The
strdatafield is a pointer to a NULL terminated string in memory. The
length fields contains thenumber of characters in the string. The size
field indicates the length of the currentmemory-block allocation. Line
11 creates a dynamic string and initializes the value of thestring. Line
13 creates a pointer, StringData, that points to the string descriptor
ofmyString. Notice that the address of operator is used to return the
address of the stringdescriptor, which is then cast as a StringDesc Ptr
using the Cptr function.

Lines 16 through 18 then print out the string descriptor data. The
memberoperator, -&gt;, is used with type definition pointers and is
comparable to using \*PtrName.

The member operator will be discussed in the chapter on composite types.
The programis closed in the usual way.

Running the program in FBIde will produce the following result.

Data: This is a dynamic string in FreeBasic!

Length: 38

Size: 72

Output 9.1: Output of dynastring.bas

Dynamic strings use Zstrings strings internally so that you can pass a
dynamicstring to a function that expects a Null terminated string and
the function will workcorrectly. The Windows api, the C runtime library
and most third-party libraries written inC expect a Null terminated
string as a string parameter.

Caution In other versions of Basic, strings have been used to load and
manipulatebinary data. If the binary data contains a Null character,
this could cause problems withFreeBasic strings, since the Null
character is used to terminate a string. While it ispossible to have an
embedded Null in a dynamic string (since dynamic strings have astring
descriptor), if you pass this data to a third party library function
that is expecting aC-style string, the data will read only up to the
Null character, resulting in data loss.

Instead of using strings to read binary data, you should byte arrays
instead.

Since a dynamic string is actually a pointer to a string descriptor, you
cannot usedynamic strings in type definitions that you are going to save
to a file. You should use afixed length string instead.

Fixed Length Strings 
---------------------

Fixed length strings are defined using a length parameter, and can only
holdstrings that are less than or equal to the defined size. Trying to
initialize a fixed lengthstring with data that is longer than the
defined size will result in the string beingtruncated to fit.

The following short program illustrates creating and using a fixed
length string.

1

Option Explicit

2

3

'Define a fixed length string

4

Dim myFString As String \* 20

5

6

'Save some dat in the string

7

myFString = "This should fit."

8

Print myFString

9

10

'This data will be truncated.

11

myFString = "This string will be truncated."

12

Print myFString

13

14

Sleep

15

End

Listing 9.2: fixedstr.bas

Analysis: Lines 4 defines a fixed length string that can hold up to 20
characters.

Line 7 loads the variable with a string and line 8 prints the contents
of the variable. Sincethe string "This should fit." is smaller than 20
characters, so the whole string will beprinted out. Line 11 tries to
initialize the string with data that is longer than 20 charactersso the
string will be truncated when it is printed out in line 12.

When you run the program you should see the following output.

This should fit.

This string will be

Output 9.2: Output of fixedstr.bas

As you can see from the output, if a string is too long to fit in the
variable, it will betruncated to fit. Fixed length strings are very
useful when creating random access recordsusing type definitions. This
technique is used in the chapter on file handling.

Zstrings 
---------

Zstrings are Null terminated, C-style strings. The main purpose of a
Zstring is tointerface with third-party libraries that expect a C-style
strings, however they are usefuleven if you do not plan to pass them to
third-party libraries. Zstrings can be defined justlike a fixed-length
string, Dim myZstring as Zstring \* 10, and FreeBasic will handle

them just like fixed strings, automatically truncating data to fit the
defined size.

Unlike fixed strings however, Zstrings can be dynamically managed by
declaring aZstring pointer and using the associated memory functions.
When using a dynamicallyallocated Zstring, you must be careful not to
overwrite the the size of the string, as thiswill overwrite parts of
memory not contained in the string and may cause the program oreven the
operating system to crash.

When using either type of Zstring, FreeBasic will manage the terminating
Nullcharacter for you, but the storage size of a Zstring will be 1 less
than the defined sizesince the the Null character occupies the last
character position. When calculating thesize of a Zstring be sure to add
1 to the value to account for the Null terminator. You mustalso not
include the character 0 in any of your data, or the data will be
truncated sinceFreeBasic will see the Null character as the end of the
string.

The following program shows both uses of the Zstring data type.

1

Option Explicit

2

3

'Declare a fixed length Zstring

4

Dim myFixedZstring As Zstring \* 20 + 1

5

'Declare a dynamic Zstring

6

Dim myDynaZstring As Zstring Ptr

7

8

'Load some data into the fixed zstring

9

Print "123456789012345678901"

10

myFixedZstring = "This should fit."

11

Print myFixedZstring

12

myFixedZstring = "This will be truncated."

13

Print myFixedZstring

14

15

'Create a dynamic zstring

16

Print "123456789012345678901"

17

myDynaZstring = Callocate(20 + 1)

18

\*myDynaZstring = "Let's add some data."

19

Print \*myDynaZstring

20

'Resize the string: 20 for current data + 5 for new

21

'data + 1 for Null

22

myDynaZstring = Reallocate(myDynaZstring, 20 + 5 + 1)

23

Print "12345678901234567890123456"

24

\*myDynaZstring = "Let's add some more data."

25

Print myDynaZstring\[0\]

26

27

'Deallocate the memory segment

28

Deallocate myDynaZstring

29

30

Sleep

31

End

Listing 9.3: zstring.bas

Analysis: Line 4 declares a fixed length Zstring. Notice that the
desired data lengthis 20 so 1 is added to to allocate space for the
terminating Null character. Line 6 declaresa pointer to a Zstring that
will be managed dynamically. Line 9 prints out a ruler tocompare the
print statements in line 11 and 13. Line 10 initializes the Zstring with
somedata that is small enough to fit in the declared size. Line 12 adds
some data that is toolong to fit within the Zstring, which will be
truncated to fit.

Line 16 prints another ruler for comparison with the dynamic Zstring
data. Line 17Callocates enough space for a 20-byte string along with the
terminating Null character.

Since myDynaZstring is defined as a Zstring Ptr, the indirection
operator is used toinitialize the variable data in line 18. Line 22
resizes the Zstring to hold 5 additionalcharacters plus the terminating
Null using the Reallocate function. Another ruler isprinted in line 23
to show the new size of the data loaded into the variable in line 24.
Line25 uses the pointer index method to print out the contents of the
variable. Line 28deallocates the allocated memory.

When you run this program you should get the following output.

123456789012345678901

This should fit.

This will be truncat

123456789012345678901

Let's add some data.

12345678901234567890123456

Let's add some more data.

Output 9.3: Output of zstring.bas

As you can see, the fixed length version of the Zstring data type
behaves exactlylike the fixed string data type and the dynamic version
behaves exactly like any otherpointer-based memory segment. Since there
is no intrinsic method for determining thesize of a Zstring allocation,
you must be careful not to over-run the buffer. The best wayto do this
is to keep a current allocation size in a separate variable that can be
referencedas needed.

You will notice in Line 25 of the listing that the pointer index method
was used toprint the contents of the resized Zstring. What would the
output be if you changed the

index from 0 to 6? Remember that a pointer index behaves much like an
array index, anda Zstring could be viewed as an array of characters. If
you were to use 6 as the index, theoutput would be add some more data.
The Print statement would start at character

position 6 and print everything up to the terminating Null character.

You can directly assign a fixed length Zstring to a dynamic string. For
a dynamicZstring, the pointer must be dereferenced by using \* or the
pointer index method. Keepin mind that the behavior of the indexing
method is the same for assignments as it is forthe Print statement.

Wstrings 
---------

Dynamic, fixed and Zstrings all use 1 byte per character. Wstrings, also
called widestrings, use 2 bytes per character and is generally used in
conjunction with Unicodestrings functions. Unicode is, strictly
speaking, a character coding scheme designed toassociate a number for
every character of every language used in the world today, aswell as
some ancient languages that are of historical interest. In the context
ofdeveloping an application, Unicode is used to internationalize a
program so that the end-

user can view the program in their native language.

Wstrings can be both fixed length and dynamic and are similar to
Zstrings.

Wstrings will be discussed in more detail in the chapter on Unicode.

String Functions 
-----------------

Creating and using strings in your application will often consist of
manipulatingthose strings and FreeBasic has a rich set of string
functions, which are listed in thefollowing table.

Function Syntax Comment

Asc B = Asc(string)

B = Asc(string, position)

Returns the character code

of the first character in a

string as a uninteger, or thecharacter code of character

at position.

Bin B = Bin(number)

B = Bin(number, digits)

Returns the binary form ofnumber as a string. Canoptionally return
onlynumber of digits.

Chr B = Chr(code)

B = Chr(code, code, ...)

Returns the character

represented by Ascii Code. Ifmultiple codes are passed toChr, the
function will return

a string of characters.

Hex B = Hex(number)

B = Hex(number, digits)

Returns the hexadecimal

form of number as a string.

Can optionally return onlynumber of digits.

Instr B = Instr(string, substring)

B = Instr(start, string,

Returns the position ofsubstring within string as an

Function Syntax Comment

substring) integer. Will accept anoptional start position. Ifsubstring
is not found, 0 isreturned.

Lcase B = Lcase(string) Converts string to alllowercase.

Left B = Left(string, number) Returns the leftmost number

of characters from string.

Len B = Len(string)

B = Len(data\_type)

Returns the length of astring or the length of anumeric data type.

Lset Lset(string\_variable, string) Left justifies string withinstring
varibale.

Ltrim B = Ltrim(string)

B = Ltrim(string, trimset)

B = Ltrim(string, ANYtrimset)

The first format will trim all

spaces from left side ofstring. The second formatwill trim characters
from left

side of string if they exactlymatch trimset. The third

format will trim characters

from left side of string ifthey match any in trimset.

Mid (Function) B = Mid(string, start)

B = Mid(string, start, length)

Returns a substring fromstring starting at start to theend of the
string, or oflength.

Mid (Statement) Mid(string, start) = B

Mid(string, start, length) = B

Copies contents of B intostring starting at start forlength. The
currentcharacters in string arereplaced. If no length isgiven, all of B
is inserted.

Oct B = Oct(number)

B = Oct(number, digits)

Returns the octal form of

number as a string. Canoptionally return onlynumber of digits.

Right B = Right(string, number) Returns the rightmostnumber of
characters from

string.

Rset Rset(string\_variable, string) Right justifies string withinstring
varibale.

Rtrim B = Rtrim(string)

B = Rtrim(string, trimset)

B = Rtrim(string, ANYtrimset)

The first format will trim all

spaces from right side ofstring. The second formatwill trim characters
from

right side of string if they

Function Syntax Comment

exactly match trimset. Thethird format will trim

characters from right side ofstring if they match any intrimset.

Space B = Space(number) Returns a string withnumber of spaces.

String B = String(number, code)

B = String(number, string)

String will return a stringwith number of characters

that correspond to the asciicharacter code or the first

character of string.

Trim B = Trim(string)

B = Trim(string, trimset)

B = Trim(string, ANYtrimset)

The first format will trim all

spaces from left and rightside of string. The secondformat will trim
characters

from left and right side ofstring if they exactly matchtrimset. The
third format will

trim characters from left

and right side of string ifthey match any in trimset.

Ucase B = Ucase(string) Converts string to all

uppercase.

Table 9.2: FreeBasic String Functions

Len Versus Sizeof 
------------------

For numeric data types, Len and Sizeof both return the size of the data
type. Forstring data types, Len returns the length of the string data
and Sizeof returns the datatype size. The following program illustrates
the differences in the two functions.

1

Option Explicit

2

3

'declare some string variables

4

Dim myDynaString as String

5

Dim myFixedString as String \* 20

6

Dim myZString as ZString \* 30

7

Dim myWString as WString \* 30

8

9

'add some data

10

myDynaString = "Hello World From FreeBasic!"

11

myFixedString = "Hello World!"

12

myZString = "Hello World From FreeBasic!"

13

myWString = "Hello World From FreeBasic!"

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

33

34

35

36

Print "Dynamic string: ";myDynaString

Print "Fixed string: ";myFixedString

Print "Zstring: ";myZString

Print "Wstring: ";myWString

Print

'print out the lengths of strings

Print "Length of Dynamic String is";Len(myDynaString);" byte(s)."

Print "Length of Fixed String";Len(myFixedString);" byte(s)."

Print "Length of ZString is";Len(myZString);" byte(s)."

Print "Length of WString is";Len(myWString);" byte(s)."

Print

'print out the variable size

Print "Size of Dynamic String is";SizeOf(myDynaString);" byte(s)."

Print "Size of Fixed String";SizeOf(myFixedString);" byte(s)."

Print "Size of ZString is";SizeOf(myZString);" byte(s)."

Print "Size of WString is";SizeOf(myWString);" byte(s)."

'wait for keypress

Sleep

End

Listing 9.4: strtype.bas

Analysis: Lines 4 through 7 dimension a string of each type. Lines 10
through 13initialize the string variables with some string data. Lines
15 through 18 print out thestring data for reference. Lines 22 through
25 use the Len function to print out the lengthof the actual string
data. Lines 29 through 32 use the Sizeof function to print out thelength
of the data types. The program is closed in the usual manner.

Running the program should produce the following output.

Dynamic string: Hello World From FreeBasic!

Fixed string: Hello World!

Zstring: Hello World From FreeBasic!

Wstring: Hello World From FreeBasic!

Length of Dynamic String is 27 byte(s).

Length of Fixed String 20 byte(s).

Length of ZString is 27 byte(s).

Length of WString is 27 byte(s).

Size of Dynamic String is 12 byte(s).

Size of Fixed String 21 byte(s).

Size of ZString is 30 byte(s).

Size of WString is 60 byte(s).

Output 9.4: Output of stringtype.bas

As you can see from the output, Len and Sizeof return different values.
The Lenfunction automatically dereferences the string variables and
returns the length of theactual string, while the Sizeof function
returns the length of the string variable itself. For adynamic string,
Sizeof returns the length of the string descriptor. The string
descriptorcontains a pointer to a Zstring (4 bytes), an integer
containing the length of the string (4bytes) and an integer that
contains the size of the current allocation (4 bytes) which totalto 12
bytes. For fixed length string and for Zstrings, Sizeof returns the
dimensioned sizeof the variable. For a Wstring, the size is twice the
dimensioned value because a Wstringuses 16-bit characters rather than
8-bit characters. The Sizeof function is useful for

determining the allocation size of fixed length strings, fixed
allocation Zstrings and fixedallocation Wstrings so that you do not
inadvertently lose data by trying to initialize thevariable with more
data than it can hold. Dynamic strings can contain variable lengthdata
so Sizeof is rarely used with dynamic strings.

Using String Functions with Zstring Pointers 
---------------------------------------------

There will be times when you will need to use a string function with a
Zstringpointer. If you try to use the pointer with directly with a
string function you will receive aType Mismatch error from the compiler.
What you need to do is to dereference the pointerwhen passing the
Zstring to a string function so that the function can access the
stringdata directly. The following program illustrates this concept.

1

Option Explicit

2

3

Dim myZstring As Zstring Ptr

4

5

myZstring = Callocate(10, Sizeof(Byte))

6

\*myZstring = "Hello FB!"

7

8

Print "F is at position";Instr(\*myZstring, "F")

9

10

Deallocate myZstring

11

12

Sleep

13

End

Listing 9.5: zstringfunc.bas

Analysis: Line 3 dimensions a Zstring pointer, myZstring. Line 5
allocates somespace for the string data in line 6. Line 8 uses the Instr
function to determine the position

of the F character in the string and prints the position to the screen.
Notice that thedereference operator is used inside the function with
myZstring so that Instr has accessto the string data. Line 10
deallocates the memory assigned to the variable. The programis then
closed in the usual way.

When you run the program you should see the following output.

F is at position 7

Output 9.5: Output of zstringfunc.bas

This technique only applies to a Zstring pointer. A fixed length Zstring
can bepassed directly to the string functions with no need to
dereference the variable.

The MK\* and CV\* String Functions 
-----------------------------------

There are times when you will want to save numeric data to a disk file,
such aswhen you are creating your own database system. Saving numeric
data as strings canbe problematic since the string representation of the
data can vary. Once solution to thisproblem is to use the various MK\*
functions which convert the binary representation of anumber into a
string, and CV\* functions which convert the string back into a number.
Theadvantage of using these functions is consistent numeric
representation; an integer isconverted into a 4-byte string, a double is
converted into an 8-byte string. This makessaving and reading binary
data from the disk quite easy. The following table lists the MK\*

and CV\* functions.

Function Syntax Comment

Mkd B = Mkd(number) Converts a double-typenumber to a string withlength
of 8 bytes.

Mki B = Mki(number) Converts an integer-typenumber to a string
withlength of 4 bytes.

Mkl B = Mkl(number) Converts a long-typenumber to a string withlength of
4 bytes.

Mklongint B = Mklongint Converts a longint-typenumber to a string
withlength of 8 bytes.

Mks B = Mks(number) Converts a single-typenumber to a string withlength
of 4 bytes.

Mkshort B = Mkshort Converts a short-typenumber to a string withlength
of 2 bytes.

Cvd B = Cvd(string) Converts an 8 byte string

Function Syntax Comment

created with Mkd into a

double-type number.

Cvi B = Cvi(string) Converts a 4 byte stringcreated with Mki into an

integer-type number.

Cvl B = Cvl(sring) Converts a 4 byte stringcreated with Mkl into an

integer-type number.

Cvlongint B = Cvlongint(string) Converts an 8 byte stringcreated with
Mklongint intoa longint-type number.

Cvs B = Cvs(string) Converts a 4 byte stringcreated with Mks into a

single-type number.

Cvshort B = Cvshort(string) Converts a 2 byte stringcreated with Mkshort
into a

short-type number.

Table 9.3: MK\* and CV\* String Conversion Functions

The following program shows how to use the functions.

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

Option Explicit

'Create some numeric variables

Dim As Integer myInt, myIntC, i

Dim As Double myDbl, myDblC

'Create some string variables

Dim As String mySInt, mySDbl

'Load some data

myInt = 10

myDbl = 254.56

Print "Integer: ";myInt

Print "Double: ";myDbl

Print

'Convert to strings

mySInt = Mki(myInt)

mySDbl = Mkd(myDbl)

Print

'Print out values

Print "Mki: ";

For i = 1 To Len(mySInt)

 Print Asc(Mid(mySInt, i, 1));" ";

23

24

25

26

27

28

29

30

31

32

33

34

35

36

37

38

Next

Print

Print "Mkd: ";

For i = 1 To Len(mySDbl)

Print Asc(Mid(mySDbl, i, 1));" ";

Next

Print

'Convert back to numbers

myIntC = Cvi(mySInt)

myDblC = Cvd(mySDbl)

Print

Print "Cvi: ";myIntC

Print "Cvd: ";myDblC

Sleep

End

Listing 9.6: mkcv.bas

Analysis: Line 4 creates three integer-type variables, myInt which will
contain theinitial integer value, myIntC which will contain the numeric
value after the Cvi conversionand i which is a variable that will be
used in the following For loop. Line 5 create twodouble-type variables,
myDbl which will contain the initial double value and myDblCwhich will
contain the Cvd conversion value. Line 7 creates two string variables,
mySIntand mySDbl which will contain the Mki and Mkd string conversion
values respectively.

Lines 10 and 11 set the initial values of the variables and lines 12 and
13 print outthose values for reference. Lines 16 and 17 convert the
integer and double values tobinary string representations using the Mki
and Mkd functions. Line 21 through 23 printout the ascii code values for
the converted integer string. The Len function is used todetermine the
length of the string, which in the case of the integer will be four
bytes. Theascii codes are print rather than the characters since the
string is a binary representationof the integer value and some of the
characters will not be visible on the screen. Lines 26through 28 print
out the character values for the converted double-type value.

Lines 31 and 32 convert the string representations back into numeric
values whichare printed to the screen in lines 34 and 35.

When you run the program you should see the following output.

Integer: 10

Double: 254.56

Mki: 10 0 0 0

Mkd: 82 184 30 133 235 209 111 64

Cvi: 10

Cvd: 254.56

Output 9.6: Output of mkcv.bas

You can see from the output that the Mk\* functions create an exact
binaryrepresentation of the numeric values. Since the Mk\* functions
create strings that are thesame length as their numeric counterparts,
you have a very consistent representation ofthe numbers. This makes
these functions quite useful when creating variable lengthrecords that
will be stored on the disk.

If your program requires fixed-length records, you can use a Type
definition to createdisk records. This technique will be covered in the
chapter on file handling.

Numeric String Conversion Functions 
------------------------------------

You find as you write programs that there are instances where you need
to converta text string such as “124.5” into a number, and the number
124.5 into a string.

FreeBasic has several conversion functions that can be used to
accomplish these tasks.

Function Syntax Comment

Format B = Format(number,

format\_string)

Returns a formatted

number. You must include

"vbcompat.bi" in yourprogram to use thisfunction.

Str B = Str(number) Converts a numeric

expression to a stringrepresentation. That is, 145will become “145”.

Val B = Val(string) Converts a string to adouble value. The Val

functions will convert from

left to right, ending at thefirst non-numeric character.

Valint B = Valint(string) Converts a string to aninteger value.

Vallng B = Vallng(string) Converts a string to a longinteger value.

Valuint B = Valuint(string) Converts a string to aunsigned integer
value.

Valulong B = Valulong(string) Converts a string to anunsigned long
integer value.

Table 9.4: Numeric String Functions

These functions work just like the Mk\* and Cv\* functions, except that
thesefunctions work with text representations of the numeric values
rather than binaryrepresentations. A common usage of these functions is
in reading text files that containtext numbers, such as ini files, and
the text needs to be converted to a number, and then

back to a string for output to the disk. They are also useful for
getting input from theuser, a technique you will see in the chapter on
the console functions.

The Format function is a general purpose function that can format
numbers, datesand time. A seperate chapter is devoted to using the
Format function.

Wide String Functions 
----------------------

Since wide strings contain 16-bit characters, there are a few string
functions thatwork specifically with wide strings. The functions listed
in the following table behave inthe same manner as their 8-bit
counterparts.

Function Syntax Comment

Wbin B = Wbin(number)

B = Wbin(number, digits)

Returns the binary form ofnumber as a wide string.

Can optionally return onlynumber of digits.

Wchr B = Wchr(unicode)

B = Wchr(unicode, unicode,

...)

Returns the character

represented by Unicode. Ifmultiple codes are passed toWchr, the function
will

return a string of unicodecharacters.

Whex B = Whex(number)

B = Whex(number, digits)

Returns the hexadecimal

form of number as a wide

string. Can optionally returnonly number of digits.

Woct B = Woct(number)

B = Woct(number, digits)

Returns the octal form of

number as a wide string.

Can optionally return onlynumber of digits.

Wspace B = Wspace(number) Returns a wide string withnumber of spaces.

Wstr B = Wstr(number)

B = Wstr(ascii\_string)

The first form of Wstr will

return a wide stringresprestation of a number.

The second form will

convert an ascii string to aUnicode string.

Wstring B = Wstring(number, code)

B = Wstring(number, string)

String will return a widestring with number ofcharacters that
correspondto the ascii character code

or the first character of

string.

Table 9.5: Wide String Functions

The wide string functions work in the same manner as their regular
string

counterparts.

String Operators 
-----------------

There are two string operators & and + which concatenate two or more
strings

together. & is preferred over + since & will automatically convert the
operands to strings,

where + will not.

CRT Character and String Functions 
-----------------------------------

The C Runtime Library has a number of functions to identify different
charactersand manipulate strings. These functions are useful for
managing string data such asidentifying numbers or parsing tokens within
a string. While all of these actions can becoded using Basic code, using
the CRT functions can speed development time, and insome cases operate
much faster than equivalent Basic code.

### Character Functions 

In the ctype.bi declaration file, located in the inc\\crt folder, you
will find a numberof functions to identify different types of
characters. To use these functions in yourprogram you must include the
ctype.bi file, \#include once "crt/ctype.bi". The

following table lists the different character functions. All of these
functions take an asciicharacter code and return a non-zero result if
successful or a zero result if not successful.

Function Syntax Comment

Isalnum B = Isalnum(asc\_code) Returns non-zero if the

character is an alphanumeric

character, zero if

not.

Isalpha B = Isalpha(asc\_code) Returns non-zero if the

character is an alphabeticalcharacter, zero if not.

Iscntrl B = Iscntrl(asc\_code) Returns non-zero if the

character is a control

character, such as a Tab,

zero if not.

Isdigit B = Isdigit(asc\_code) Returns non-zero if the

character is a numeric digit,

0 to 9, zero if not.

Isgraph B = Isgraph(asc\_code) Returns non-zero if the

characterhas a glyphassociated with it, zero if

not. This function onlyidentifies the standard glyphcharacters in the
lower ascii

range.

Function Syntax Comment

Islower B = Islower(asc\_code) Returns non-zero if the

character is lower-case, zero

if not.

Isprint B = Isprint(asc\_code) Returns non-zero if the

character is a printablecharacter, zero if not. This

function only identifies theprintable characters in thelower ascii
range.

Ispunct B = Ispunct(asc\_code) Returns non-zero if the

character is a punctuationcharacter, zero if not.

Isspace B = Isspace(asc\_code) Returns non-zero if the

character is a whitespacecharacter, zero if not.

Whitespace is defined as aspace, form-feed, new-line,

carriage return, horizontaland vertical tabs.

Isupper B = Isupper(asc\_code) Returns non-zero if the

character is upper-case,

zero if not.

Isxdigit B = isxdigit(asc\_code) Returns non-zero if the

character is a hexidecimal

digit, zero if not.

Hexadecimal digits include 0through 9, A through F anda through f.

Table 9.6: CRT Character Functions

The following program illustrates how to use these functions.

1

Option Explicit

2

3

\#include once "crt/ctype.bi"

4

5

Dim As String myString

6

Dim As Integer ret, i, ichar

7

8

'Load some characters into the string

9

myString = "ABcd01!\* " & Chr(128) & Chr(1)

10

11

'Print header on console

12

Print "Char";Tab(6);"Alnum";Tab(12);"Alpha";Tab(18);"Cntrl";Tab(24);

13

Print "Digit";Tab(30);"Graph";Tab(36);"Lower";Tab(42);"Print";Tab(48);

14

Print "Punct";Tab(54);"Space";Tab(60);"Upper"

15

Print String(79, "")

16

17

'Examine each character in string.

18

For i = 1 To Len(myString)

19

ichar = Asc(Mid(myString, i, 1))

20

'Print the character21

Print Chr(ichar);

22

Print Tab(6);

23

'Check to see what kind of character it is24

ret = isalnum(ichar)

25

'If character type then print Y26

If ret &lt;&gt; 0 Then27

Print "Y";

28

Else29

Print "N";

30

End If31

Print Tab(12);

32

ret = isalpha(ichar)

33

If ret &lt;&gt; 0 Then34

Print "Y";

35

Else36

Print "N";

37

End If38

Print Tab(18);

39

ret = iscntrl(ichar)

40

If ret &lt;&gt; 0 Then41

Print "Y";

42

Else43

Print "N";

44

End If45

Print Tab(24);

46

ret = isdigit(ichar)

47

If ret &lt;&gt; 0 Then48

Print "Y";

49

Else50

Print "N";

51

End If52

Print Tab(30);

53

ret = isgraph(ichar)

54

If ret &lt;&gt; 0 Then55

Print "Y";

56

Else57

Print "N";

58

End If59

Print Tab(36);

60

ret = islower(ichar)

61

If ret &lt;&gt; 0 Then62

Print "Y";

63

Else64

Print "N";

65

End If66

Print Tab(42);

67

ret = isprint(ichar)

68

If ret &lt;&gt; 0 Then69

Print "Y";

70

Else71

Print "N";

72

End If73

Print Tab(48);

74

ret = ispunct(ichar)

75

If ret &lt;&gt; 0 Then76

Print "Y";

77

Else78

Print "N";

79

End If80

Print Tab(54);

81

ret = isspace(ichar)

82

If ret &lt;&gt; 0 Then83

Print "Y";

84

Else85

Print "N";

86

End If87

Print Tab(60);

88

ret = isupper(ichar)

89

If ret &lt;&gt; 0 Then90

Print "Y"

91

Else92

Print "N"

93

End If

94

Next

95

96

Sleep

97End

Listing 9.7: crt\_char.bas

Analysis: Line 3 includes the ctype.bi file that is needed to link to
these CRTfunctions. Lines 5 and 6 declare the working variables.
MyString will contain thecharacters to identify, ret is the return value
from the function, i is used in the For-Next

loop and ichar contains the fascicle code of the character that is
passed as the parameterto the different functions. Line 12 through 15
display a header line that will be used toidentify which functions
returns a true result. The different column headers refer to
thedifferent functions. Alnum is the return column for the Isalnum
function, the Alphacolumn is the return for the Isalpha function and so
on.

Line 18 and 94 comprise the For-Next block. Line 19 gets the current
characterfrom the string and converts it to an ascii code using the Asc
function. The character isthen tested with each function. If the
function returns a non-zero result, a Y is printed inthe appropriate
column. If the function returns a zero, an N is printed in the
appropriatecolumn.

The program is then closed in the usual way.

When you run the program you should see the following result.

Char Alnum Alpha Cntrl Digit Graph Lower Print Punct Space Upper

A Y Y N N Y N Y N N Y

B Y Y N N Y N Y N N Y

c Y Y N N Y Y Y N N N

d Y Y N N Y Y Y N N N

0 Y N N Y Y N Y N N N

1 Y N N Y Y N Y N N N

! N N N N Y N Y Y N N

\*

N N N N Y N Y Y N N

N N N N N N Y N Y N

N N N N N N Y N Y N

Ç N N N N N N N N N N

.

NNYNNNNNNN

Output 9.7: Output of crt\_char.bas

As you can see, these functions work with the lower ascii characters,
which are thecharacters you would normally find in text files. Using
these functions can make your joba lot easier when you are trying to
identify characters from a file or from user input.

### Strtok Function 

The Strtok function will return tokens separated by a delimiter set.
Strtok is quitefast and since it will look for a set of delimiters, it
is much easier to use Strtok than Instr

within a loop. Strtok is contained in the string.bi declaration file
located in the inc\\crtfolder of your FreeBasic installation. Strtok is
declared as:

declare function strtok cdecl alias "strtok" (byval as zstring ptr, \_

byval as zstring ptr) as zstring ptr

The first parameter is the string to parse and the second parameter is
the delimiterset. Strtok returns a pointer to the first token in the
string. Even though the parametersare defined as Zstring pointers, you
can use dynamic strings since the compiler willautomatically dereference
a dynamic string if it is passed to a Zstring pointer. This makesworking
with this function quite easy. You will need to define a Zstring pointer
as thereturn value though.

The following program uses Strtok to parse a string into tokens.

1

Option Explicit

2

3

\#include once "crt.bi"

4

5

Dim As String tstr, tmpstr, delim

6

Dim zret As Zstring Ptr

7

8

9

'Create delimiters

10

delim = " ,!"

11

'Create parse string

12

tstr = "HelloWorld,

From Freebasic!"

13

'Create a working copy of string

14

'strtok will alter original string

15

tmpstr = tstr

16

'First call with string and delimiters

17

zret = strtok(tmpstr, delim)

18

'Check for a NULL pointer

19

If zret &lt;&gt; NULL Then20

Print zret\[0\]

21

'Parse rest of string22

Do

23

'Call with NULL to work on same string24

zret = strtok(NULL, delim)

25

If zret &lt;&gt; NULL Then26

Print zret\[0\]

27

End If28

Loop Until zret = NULL

29

End If

30

Sleep

31

End

Listing 9.8: strtok.bas

Analysis: Line 3 includes the crt library declarations so that Strtok is
available tothe program. Lines 5 and 6 define the working variables.
Tstr is the original parse string,

tmpstr is a copy of the original string and delim is the set of
delimiters. Zret is defined as

a Zstring pointer and will be the return value from the function. Line
10 sets the delimiterset and line 12 sets the parse string. In line 15 a
copy is made of the original string, sinceStrtok will alter the string
as it is parsed. If you need to save the original string value, usea
temporary string with the function rather than the original string. Line
17 calls Strtokwith the parse string and the delimiter set. This initial
call sets up the function to parsethe string. Subsequent calls to Strtok
will use a Null in place of the parse string toindicate that you want to
parse the original string and not a new string.

Line 19 checks for a Null pointer. Strtok will return a Null when it
cannot extractany tokens from the parse string. You should always check
for a NULL pointer beforeusing the pointer reference. Line 20 prints the
value of the token using the pointer indexmethod. This will print
everything from index 0 up to the terminating Null character.

Remember that Zstring are C-type strings, an array of characters that
terminate withcharacter zero, a Null.

Line 22 through 28 call Strtok with a Null for the parse string to
extract each tokenfrom the string. Thre loop terminates when a Null is
returned from Strtok. Once again, inline 25, the pointer is checked to
make sure it isn't a Null pointer before the value isprinted to the
console window.

After all the tokens have been processed, zret will be Null, the loop
will exit and theprogram will close in the usual manner.

When you run the program you should the following output.

Hello

World

From

Freebasic

Output 9.8: Output of strtok.bas

The output shows the individual tokens in the string. Not only is Strtok
easy to use,

but because you can pass a set of delimiters the amount of code you have
to write toparse a string that has several delimiters is considerably
less than if you wrote the parsefunction in FreeBasic. Less code means
less chance of things going wrong, which resultsin a more robust, stable
program.

A Look Ahead 
-------------

So far in the book you have seen the individual intrinsic data types.
There aretimes though when you need an aggregate data type to fully
describe your data. This iswhere Type definitions and Unions come in
handy, which are discussed in the nextchapter.

Chapter 10 Composite Data Types 
================================

There are times when creating a program that you may want to define
anaggregate structure such as a personnel record, or an enemy in a game.
While you cando this using individual data types, it is hard to manage
within a program. FreeBasic

offers two composite data types, the Type and Union.

Types 
------

FreeBasic allows you to group several data types into a unified
structure called aType definition which you can use to describe these
aggregate data structures.

The basic structure of a type definition is:

Type type name

var definition

var definition

...

End Type

The Type-End Type block defines the scope of the definition. You define
theelements of the type structure in the same manner as using the Dim
keyword, withoutusing Dim. The following code snippet shows how to build
an employee type.

Type EmployeeType

fname As String \* 10

lname As String \* 10

empid As Integer

dept As Integer

End Type

You can use any of the supported data types as data elements, including
pointersand other type definitions. When you create the type definition,
such as the exampleabove, you are just creating a template for the
compiler. In order to use the typedefinition, you need to create a
variable of the type, as the following code snippetillustrates.

Dim Employee As EmployeeType

Once you have created a variable of the type, you can access each
element withinthe type using the dot notation var\_name.field\_name.
Using the above example, to

access the fname field you would use Employee.fname = “Susan”.

To access multiple fields at a time, you can use the With-End With
block. Thefollowing code snippet shows how to use the With block with
the above example.

With Employee

.fname = "Susan"

.lname = "Jones"

.empid = 1001

.dept = 24

End With

The following program shows how to define, create and manage a type
definition.

1

Option Explicit

2

3

'Create type definition

4

Type EmployeeType5

fname As String \* 106

lname As String \* 107

empid As Integer8

dept As Integer

9

End Type

10

11

'Create an instance of the type

12

Dim Employee As EmployeeType

13

14

'Initialize the type

15

With Employee16

.fname = "Susan"

17

.lname = "Jones"

18

.empid = 100119

.dept = 24

20

End With

21

22

'Print out header row

23

Print "First Name";Tab(13);"Last Name";Tab(25);"Emp ID";Tab(33);"Dept"

24

Print String(79, "")

25

'Print out data

26

With Employee27

Print RTrim(.fname);Tab(13);RTrim(.lname);Tab(24);.empid;Tab(32);.dept

28

End With

29

30

Sleep

31

End

Listing 10.1: type.bas

Analysis: Line 4 through 9 define the type structure that is used in the
program.

The type has 4 fields, two fixed length strings and 2 integer values.
Dynamic strings can

be used within a type definition, however if you want to save the type
information to thedisk, then you need to use fixed length strings.
Dynamic strings are actually pointers to astring descriptor and saving a
type that contains dynamic strings will save the 4 bytepointer value,
rather than the actual string data, resulting in data loss.

Line 12 creates a variable of the type, Employee. The type definition is
a templateand cannot be used until you create an instance of the type by
creating a variable of thetype. Lines 15 through 20 initialize the type
variable with some data using the a With-EndWith block.

Line 23 prints a header row to the console that indicates the field name
data. TheTb function is used to align data names to the appropriate
column. Line 24 uses theString function to print a dashed line, just to
offset the header row from the data row.

Lines 26 through 28 prints the type data. Rtrim is used on the fixed
length stringelements to trim off any unused trailing spaces. The Tab
function is again used to alignthe data to the appropriate columns. The
program is then ended in the usual way.

When you run the program you should the following output.

First Name Last Name Emp ID Dept

Susan Jones 1001 24

Output 10.1: Output of type.bas

As you can see from the program, using a type definition is a perfect
way to grouprelated data into a single data structure. Not only is it a
compact way to describe data inyour program, but by grouping related
data into a single object, you can manipulate thatdata as a single
entity, rather than as a bunch of unrelated variables. This reduces
thechances that errors will creep into your program by trying to manage
large a set ofindividual variables.

Types Within Types 
-------------------

In addition to the intrinsic data types, type fields can also be based
on a typedefinition. Why would you want to do this? One reason is data
abstraction. The moregeneral your data structures, the more you can
reuse the code in other parts of yourprogram. The less code you have to
write, the less chance of errors finding their way intoyour program.
Using the Employee example, suppose for a moment that you needed totrack
more dept information than just the department id. You might need to
keep track ofthe department manager, the location of the department,
such as the floor or thebuilding, or the main telephone number of the
department. By putting this informationinto a separate type definition,
you could this information by itself, or as part of anothertype
definition such as the Employee type. By generalizing your data
structures, yourprogram will be smaller, and much more robust.

Using a type within a type is the same as using on of the intrinsic data
types. Thefollowing code snippets illustrates an expanded department
type and an updated employee type.

Type DepartmentType

id As integer

managerid as integer

floor as integer

End Type

Type EmployeeType

fname As String \* 10

lname As String \* 10

empid As Integer

dept As DepartmentType

End Type

Dim Employee As EmployeeType

To access the department information within the Employee type, you use
thecompound dot notation to access the dept fields.

Employee.dept.id = 24

Employee.dept.managerid = 1012

Employee.dept.floor = 13

The top levels is Employee, so that reference comes first. Since dept is
now a typedefinition, you need to use the dept identifier to access the
individual fields within the

DepartmentType. You can even carry this further, by including a type
within a type withina type. You would simply use the dot notation of the
additional type level as needed.

While there is no limit on the levels of nested type definitions, it
gets to be a bit unwieldywhen used with several levels.

You can also use the With-End With block with nested types, by nesting
the Withblock, as illustrated in the following code snippet.

With Employee

.fname = "Susan"

.lname = "Jones"

.empid = 1001

With .dept

.id = 24

.managerid = 1012

.floor = 13

End With

End With

Notice that the second With uses the dot notation, .dept, to specify the
next levelof type definitions. When using nested With blocks, be sure
that match all the End Withstatements with their correct With statements
to avoid a compile error.

The following program is a modified version of the previous program
illustratingthe new type definitions.

Option Explicit

'Create the type definition

Type DepartmentType

id As Integer

managerid As Integer

floor As Integer

End Type

Type EmployeeType

fname As String \* 10

lname As String \* 10

empid As Integer

dept As DepartmentType

End Type

'Create an instance of the type

Dim Employee As EmployeeType

'Initialize the type

With Employee

.fname = "Susan"

.lname = "Jones"

.empid = 1001

With .dept

 .id = 24

.managerid = 1012

.floor = 13

 End With

End With

'Print out header row

Print "First Name";Tab(13);"Last Name";Tab(25);"Emp ID";Tab(33);

Print "Dept";Tab(39);"Manager";Tab(47);"Floor"

Print String(79, "")

'Print out data

With Employee

 Print Rtrim(.fname);Tab(13);Rtrim(.lname);Tab(24);.empid;Tab(32);

With .dept

Print .id;Tab(38);.managerid;Tab(46);.floor

End With

End With

Sleep

End

Listing 10.2: type-type.bas

Analysis: Lines 4 through 8 define the new type for the department. This
is used inthe employee type definition is line 14. The field dept is
defined as DepartmentType, inthe same manner as Employee is defined in
line 18, with the Dim of course. Line 21through 30 use two With-End With
blocks to initialize the type data. Employee is the firstlevel type,
while .dept, using the dot notation, is the second level type. It is
importantthat you use the dot notation with the second level With block
so that the compiler knowsthat you are referring to a type element
within Employee. Lines 33 and 34 prints theheader row with the
additional department field information. Lines 37 through 42 thenprint
the type data, again using a nested With block. Notice how using the
With blocksdocument the type structure without needing any additional
comments. While this isn'tthe primary reason to use a With block, it
does create code that is easily understood. Theprogram is closed in the
usual way.

When you run the program you should see the following output.

First Name Last Name Emp ID Dept Manager Floor

Susan Jones 1001 24 1012 13

Output 10.2: Output of type-type.bas

While it may not be readily apparent from the example, abstracting the
data in thismanner gives you a tremendous amount of flexibility in your
program. A company willusually have more than one department, so by
abstracting the department informationinto a separate type definition,
you can create functions that manage the departmentinformation, while at
the same time minimizing the impact on the employee data

structure.

Type Assignments 
-----------------

Extending the idea of data abstraction further, it would be nice to be
able toseparate the initialization of the department type from the
initialization of the employeetype. By separating the two functions, you
can easily add additional departments asneeded. This is where you can
use type assignments. Just as you can assign one intrinsicdata type to
another, you can assign one type variable to another type variable,

providing they share the same type definition.

The following program abstracts the department initialization function
and assignsthe result to the department type within the Employee type.

1

Option Explicit

2

3

'Create the type definition

4

Type DepartmentType

5

id As Integer

6

managerid As Integer

7

floor As Integer

8

End Type

9

Type EmployeeType11

fname As String \* 1012

lname As String \* 1013

empid As Integer14

dept As DepartmentType

15

End Type

16

17

'This function will init the dept type and return it to caller

18

Function InitDept(deptid As Integer) As DepartmentType19

Dim tmpDpt As DepartmentType21

Select Case deptid22

Case 24 'dept 2423

With tmpDpt

24

.id = deptid

25

.managerid = 1012

26

.floor = 1327

End With28

Case 48 'dept 4829

With tmpDpt

.id = deptid

31

.managerid = 1024

32

.floor = 1233

End With34

Case Else 'In case a bad department id was passed35

With tmpDpt

36

.id = 0

37

.managerid = 0

38

.floor = 039

End With

End Select41

'Return the dept info42

Return tmpDpt

43

End Function

44

45

'Create an instance of the type

46

Dim Employee As EmployeeType

47

48

'Initialize the Employee type

49

With Employee

.fname = "Susan"

51

.lname = "Jones"

52

53

54

55

56

57

58

59

60

61

62

63

64

65

66

67

68

69

 .empid = 1001

.dept = InitDept(24) 'get dept info

End With

'Print out header row

Print "First Name";Tab(13);"Last Name";Tab(25);"Emp ID";Tab(33);

Print "Dept";Tab(39);"Manager";Tab(47);"Floor"

Print String(79, "")

'Print out data

With Employee

 Print Rtrim(.fname);Tab(13);Rtrim(.lname);Tab(24);.empid;Tab(32);

With .dept

Print .id;Tab(38);.managerid;Tab(46);.floor

End With

End With

Sleep

End

Listing 10.3: type-assign.bas

Analysis: This program is identical to the previous program, with the
addition of thedepartment initialization function in lines 18 through
43. The functions is defined in line18 as returning the DepartmentType,
with one parameter, the department id. Line 19creates a temporary
department type variable that will be initialized with the
appropriatedata, and returned from the function. The function uses a
Select Case block to set the

data within the temporary type. The Select statement will execute the
block of code thatmatches the deptid. If no matches are found, the Else
case will return a zero for eachelement. Since it is probable that no
dept will have an id of 0, this value can be checkedto make sure that
the passed deptid is valid. The Return statement in line 42 returns
theinitialized dept information to the caller.

The function is used in line 53 to set the data values for the
department in theEmployee type. Although this program doesn't include a
check for an invalid departmentid for clarity, you could add a check on
the department id following the Employeeinitialization code to make sure
that a valid department id was used in the function.

The rest of the program is the same as the previous program, and prints
theemployee information to the screen.

When you run the program, you should see that the output is identical to
theprevious program output.

First Name Last Name Emp ID Dept Manager Floor

Susan Jones 1001 24 1012 13

Output 10.3: Output of type-assign.bas

By just adding a simple function to the program, you have made the
programeasier to maintain than the previous versions. If a new
department is created, you cansimply update the InitDept function with
the new department information, recompile andthe program is ready to go.

### Pointers to Types 

You can create a pointer to a type, just as you can create a pointer to
any of theintrinsic data types, and the same rules apply. As with any
pointer, you must allocatesome memory for the pointer, dereference the
data elements, and deallocate the pointerwhen you are done using it.
Type pointers use the arrow notation, -&gt;, rather than the dotnotation
to access the individual fields with a type.

In the previous program listing, the error checking on an invalid
department id wasclunky at best. A better method is to have the InitDept
function return a success codethat indicates a valid department id. The
following program implements this strategy,

and uses a DepartmentType pointer to hold the department information for
the Employee

type.

1

Option Explicit

2

3

\#define deptok 0

4

5

'Create the type definition

6

Type DepartmentType

7

id As Integer

8

managerid As Integer

9

floor As Integer

10

End Type

11

12

Type EmployeeType13

fname As String \* 1014

lname As String \* 1015

empid As Integer16

dept As DepartmentType

17

End Type

'This function will init the dept type and return it to caller

Function InitDept(deptid As Integer, dpt As DepartmentType Ptr ) As
Integer

Dim ret As Integer = deptok22

Select Case deptid24

Case 24 'dept 24

dpt&gt;

id = deptid

dpt&gt;

managerid = 1012

27

dpt&gt;

floor = 1328

Case 48 'dept 48

29

dpt&gt;

id = deptid

30

dpt&gt;

managerid = 1024

31

dpt&gt;

floor = 1232

Case Else 'In case a bad department id was passed

33

dpt&gt;

id = 0

34

dpt&gt;

managerid = 0

35

dpt&gt;

floor = 0

36

ret = Not deptok37

End Select38

'Return the dept status39

Return ret

40

End Function

41

42

'Create an instance of the types

43

Dim Employee As EmployeeType

44

Dim tmpDept As DepartmentType Ptr

45

46

'Initialize the pointer

47

tmpDept = Callocate(Sizeof(DepartmentType))

48

'Get the department info, check return

49

If InitDept(24, tmpDept) &lt;&gt; deptok Then50

'Error on dept type51

Deallocate tmpDept52

Print "Invalid Department ID."

53

Else54

'Department ok, init the Employee type55

With Employee56

.fname = "Susan"

57

.lname = "Jones"

58

.empid = 100159

.dept = \*tmpDept 'Dereference the pointer60

End With61

'Don't need the dept info now62

Deallocate tmpDept63

'Print out header row64

Print "First Name";Tab(13);"Last Name";Tab(25);"Emp ID";Tab(33);

65

Print "Dept";Tab(39);"Manager";Tab(47);"Floor"

66

Print String(79, "")

67

'Print out data68

With Employee69

Print Rtrim(.fname);Tab(13);Rtrim(.lname);Tab(24);.empid;Tab(32);

70

With .dept71

Print .id;Tab(38);.managerid;Tab(46);.floor72

End With73

End With

74

End If

75

76

Sleep

77

End

Listing 10.4: type-ptr.bas

Analysis: This version of the program has a few modifications from the
previousversions, but overall it is the same program. Line 3 defines a
return for the InitDeptfunction. If the functions returns this code, the
department id is valid; if the function doesnot return this code, the
department id is invalid. The type definitions are the same asused
previously, but the function in line 20 has changed.

The function now returns an integer value, and there are two parameters,
adepartment id and a pointer to the DepartmentType. Line 21 dimensions
and initializesthe function return value to deptok. If there are not
errors, this value will be returned. Ifthe deptid is invalid, the Case
Else will set the return value to Not deptok (-1) in line 36.

This is a good technique to return boolean values from a function. By
initializing thereturn variable to the “ok” status, you only need to set
the variable to the “not ok” status,

if an error occurs. Less typing, less code and fewer chances of
introducing bugs into the

program.

In the individual Case blocks, the arrow notation is used to access the
individual

fields of the type pointer. The -&gt; automatically dereferences the
pointer for you, makingit easier to manipulate the individual fields
within the type. Line 39 returns the successcode of the function. You
don't need to return any type information, because the functionis
actually updating the external department type variable through the
pointer.

Line 44 dimensions a DepartmentType pointer. Which is initialized in
line 47.

Remember that Callocate allocates a memory segment, clears the segment
and thenreturns the address of the segment which is stored in the
variable tmpDept. In line 49 theInitDept function is called inside an If
statement. If the function fails, that is returns Notdeptok, then the
program deallocates the pointer and prints an error message. If
thefunction succeeds, that is returns deptok, then the Employee type is
initialized and thedata is printed to the screen. Notice in line 59 that
the program is still using a typeassignment, but because tmpDept is a
pointer, the dereference operator must be used.

Line 62 shows the power of using pointers as intermediate data
structures. Oncethe department data is in the Employee type, you don't
need the department typereference. Line 62 deallocates tmpDept, freeing
the memory it was using. There is nosense in wasting memory on data
structures that you only use for a very short time.

The rest of the program is identical to the previous programs.

When you run this program you should again see the same output as the
previous

programs.

First Name Last Name Emp ID Dept Manager Floor

Susan Jones 1001 24 1012 13

Output 10.4: Output of type-ptr.bas

This change, like the previous change, was minor—most of the original
program isin intact—but the program is now much more robust, easier to
manage, and less prone toerror than the original program. The fact that
the output has not changed even thoughthe program has, is a good
indicator that the changes that were made were did notcreate unwanted
side effects in the program. This is what data abstraction does;

minimize negative impacts on existing code.

### Type Memory Arrays 

In the chapter on pointers, you saw how to create a memory array of
integersusing pointers. You can do the same with Type definitions, in
much the same way. Thefollowing program creates a dynamic memory array
using a type.

1

Option Explicit

2

3

'Declare type

4

Type myType5

id As Integer

6

End Type

7

8

'Declare a pointer to the type

9

Dim myTypePtr As myType Ptr

10

Dim As Integer i

11

12

'Create a memory array of types

13

myTypePtr = Callocate(5, Sizeof(myType))

14

15

'Add some data to the type

16

For i = 0 To 417

myTypePtr\[i\].id = i

18

Next

19

20

'Print data

21

Print "Initial data:"

22

For i = 0 To 423

Print myTypePtr\[i\].id

24

Next

25

Print

26

27

'Resize the array

28

myTypePtr = Reallocate(myTypePtr, 10)

29

30

'Add the new data

31

For i = 4 To 932

myTypePtr\[i\].id = i

33

Next

34

35

'Print data

36

Print "New Data:"

37

For i = 0 To 938

Print myTypePtr\[i\].id

39

Next

40

41

'Release memory

42

Deallocate myTypeptr

43

44

Sleep

45

End

Listing 10.5: memtype.bas

Analysis: Lines 4 through 6 declare a simple type. Line 9 dimensions a
pointer tomyType, and line 10 creates an integer variable i for the
following For-Next loops. Line 13allocates memory for 5 myType entries
in the memory array. Lines 16 through 19initialize the individual type
elements. Notice the syntax istype\_variable\[index\].field\_name. Since
myTypePtr is a typed pointer, you can use theindex method to access each
element in the array. You then use the dot notation toaccess each
individual field of the type, just as you would using a single type
variable.Lines 21 through 25 print the data to the screen using the same
pointer index method. Line 28 resizes the memory array with an
additional 5 type elements. Lines 31through 33 initialize the new memory
segment with data, and lines 26 through 39 printthe all the data to the
screen. Line 42 deallocates the memory and the program is closedin the
usual way.

When you run the program you should the following output.

Initial data:

 0

 1

 2

 3

 4

New Data:

 0

1

2

3

4

5

6

7

8

9

Output 10.5: Output of memtype.bas

As you can see, creating a memory array of types is very straight
forward. Youcreate the number of elements you need by using Callocate
and then using the indexpointer method, you can access each individual
type field using the dot notation. Theadvantage of using this method is
that you can create dynamic structures in memory andgrow or shrink them
as necessary so that you are not wasting memory on elements youmay not
need. You can of course create a standard array of types, which will be
coveredin the chapter on arrays, and you can even create a dynamic array
of types—but themethod shown here does not incur the overhead of a
dynamic array, and can be passedto functions using the pointer method.

Dynamic Arrays in Types 
------------------------

FreeBasic does allow you you to create an array within a type, which is
covered inthe chapter on arrays, but it does not allow you to create
dynamic arrays in types. Thereare times when you will need to create a
dynamic structure in a type, and this can beaccomplished by using memory
array method within a type. The following programillustrates a dynamic
array of a type within a type.

1

Option Explicit

2

3

'This will be the dynamic type

4

Type pt5

row As Integer6

col As Integer

7

End Type

8

9

'The base type:

10

'darray will contain array data

11

Type DType12

darray As pt Ptr

13

End Type

14

15

'Create an instance of type

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

33

34

35

36

37

38

Dim myType As DType

Dim As Integer i

'Create enough space for elements

myType.darray = Callocate(5, Sizeof(pt))

'Load data into array

For i = 0 To 4

myType.darray\[i\].row = Int(Rnd \* 10) + 1

 myType.darray\[i\].col = Int(Rnd \* 10) + 1

Next

'Print data

For i = 0 To 4

 Locate myType.darray\[i\].row, myType.darray\[i\].col

 Print "X"

Next

'Free allocated space

Deallocate myType.darray

Sleep

End

Listing 10.6: dynatype.bas

Analysis: Lines 4 through 7 define a type that will be used in the
dynamic array.

The program will use the row and column to print a character to the
screen. Lines 11through 13 define the base type. Notice that darray is
dimensioned as a pointer to thetype pt. If you needed an array of
integers, you would use As Integer Ptr. The methodsare the same whether
using an intrinsic data type, or another type as illustrated here.

Line 20 allocates memory for 5 array elements. Since the program is
creating an array oftypes, the second parameter to Callocate is the size
of the type, pt. For an integer array itwould be Sizeof(Integer). Lines
23 through 26 initialize the type array with a randomrow and column
which will be used within the print code that follows. The access
syntaxin lines 24 and 25 follow what you have already seen; the dot
notation is used to accessthe base type field darray, which is then
accessed using the pointer indexing method,

since the program is using a typed pointer. The dot notation is then
used to access theindividual fields of the array type. The syntax is the
same as that shown with the typememory array, except here you have one
additional level of indirection because the arrayis contained within a
type.

Lines 29 through 32 use the row and column fields to print an X to the
screen.

Again you can see that the dot notation and pointer index methods are
used to accessthe fields within the type. Line 35 frees the memory
allocated and the program is closedin the usual way.

When you run the program you should see something similar to the
following

output.

 X

 X

 X

 X

 X

Output 10.6: Output of dynatype.bas

The location of the X's will vary since the rows and columns are
generatedrandomly, but since Randomize is not being used, you should the
same layout between

runs.

The two previous programs are quite similar in format. The differences
are thelevels of indirection being used. In the memory array program,
the type itself was beingused as the array element, so the pointer index
was used at the top level, with the dotnotation used to access the field
data. In this program, the memory array is embeddedwithin the type, so
you use the standard dot notation to access the base type field,

darray, and then use the pointer index method on the field to select the
array element.

Since the array element is a type, you use the dot notation to access
the array elementfield, just as you would as if it were a simple type
variable.

You could of course create a memory array that contained a memory array.
In thiscase, you would use the pointer index method to select the base
type element, and thenthe dot notation to select the memory array field,
then a pointer index to access theelement within the embedded array, and
finally the dot notation to select the arrayelement field. It sounds
complicated, but is actually easier to implement than it is toexplain.
The following program modifies the previous program to illustrate this
concept.

1

Option Explicit

2

3

'This will be the embedded type

4

Type pt5

row As Integer6

col As Integer

7

End Type

8

9

'The base type:

10

'darray will contain array data

11

Type DType12

darray As pt Ptr

13

End Type

14

15

'Create a pointer to base type

16

Dim myType As DType Ptr

17

Dim As Integer i, j

18

19

'Set up random number generator

20

Randomize Timer

21

22

'Create enough space for 3 base type elements

23

myType = Callocate(3, Sizeof(Dtype))

24

'Create space for 3 pt elements within base type

25

For i = 0 To 2

26

myType\[i\].darray = Callocate(3, Sizeof(pt))

27

Next

28

29

'Load data within the type arrays

30

For i = 0 To 2

31

For j = 0 To 232

myType\[i\].darray\[j\].row = Int(Rnd \* 10) + 133

myType\[i\].darray\[j\].col = Int(Rnd \* 10) + 134

Next

35

Next

36

37

'Print data

38

For i = 0 To 239

For j = 0 To 240

Locate myType\[i\].darray\[j\].row, myType\[i\].darray\[j\].col41

Print "X"

42

Next

43

Next

44

45

'Free embedded type array

46

For i = 0 To 247

Deallocate myType\[i\].darray

48

Next

49

'Free base type array

50

Deallocate myType

51

52

Sleep

53

End

Listing 10.7: dyna-type2.bas

Analysis: Line 4 through 7 define the type that that will be an array
within the basetype. Lines 11 through 13 define the base type. Darray is
dimensioned as a pointer to the type pt since this will be a memory
array with the base type. Line 16 defines a pointer tothe base type,
Dtype, since the base type will also be a memory array. Line 17
definestwo working variables, i and j, which will be used in the
For-Next loops to create and loaddata within the types. Line 20
initializes the random number generator.

Line 23 creates a three-element memory using the base type. Lines 25
through 27then create a three-element memory array using the subtype,
pt, for each base typeelement. Notice that the base type, myType is
indexed using the pointer index methodsince it is a pointer, and each
darray element is initialized using Callocate, since darray isalso a
pointer. Lines 30 through 35 load data into the memory array elements
row andcolumn. The outer For loop indexes the base type pointer, while
the inner loop indexesthe darray type pointer. Since darray is an
element of myType, darray is selected usingthe dot notation, and since
row and col are elements of daray, these are selected usingthe dot
notation.

Lines 38 through 43 use the same logic to print the X's on the screen.
The outerloop selects the base type pointer, while the inner loop
selects the embedded pointer.The row and col elements of darray are used
in the Locate statement to move the cursorto the position described by
the row and col variables, and an X is printed to the screen.

Lines 46 through 48 deallocate the darray memory array. The order of
deallocationis important here. You must deallocate the embedded array
first, before you deallocatethe base type array. If you deallocate the
base type array without deallocating theembedded array, the embedded
array elements will remain in memory causing amemory leak. The rule of
thumb here is to deallocate the inner most pointer elementsfirst, and
then work out toward the base pointer element. Line 50 deallocates the
basetype elements, only after the darray elements have been deallocated.
The program isthen closed in the usual way.

When you run the program you should see something similar to the
followingoutput. There should be nine X's, however since the random
number generator is workingwithin a 10 by 10 space, it is possible two
X's may occupy the same row and column, soyou may not see all nine X's.

 X X

 X X

 X

 X

 X X

 X

Output 10.7: Output of dyna-type2.bas

While this may seem confusing at first, if you look at the code you will
see arecurring pattern. The pointer elements are selected using the
pointer index method,

followed by the dot notation to select the individual type elements. You
start with thebase type, in this case myType, index the pointer, and
then select the elements using thedot notation, in this case darray.
Since darray is a pointer, it is selected using a pointerindex, followed
by the dot notation to select the row and col elements. The pattern,

pointer index, dot notation, pointer index, dot notation would be used
for as many levelsas needed to resolve a individual element within the
memory array.

The following diagram shows the memory layout of the program.

MyType\[0\] &gt;

.darray\[0\] &gt;

.row, .col

.darray\[1\] &gt;

.row, .col

.darray\[2\] &gt;

.row, .col

MyType\[1\] &gt;

.darray\[0\] &gt;

.row, .col

.darray\[1\] &gt;

.row, .col

.darray\[2\] &gt;

.row, .col

MyType\[2\] &gt;

.darray\[0\] &gt;

.row, .col

.darray\[1\] &gt;

.row, .col

.darray\[2\] &gt;

.row, .col

You can see the pattern reflected in the diagram. If row were a type
pointer, thenyou would just repeat the pattern of index, dot notation on
row to resolve the next levelof elements. This type of data structure
gives you a lot of flexibility in your programming.

There is no need to have three darray elements for each base element;
myType\[0\] maypoint to 4 elements and myType\[2\] may point to 1
element. You would need to add anadditional field in myType to indicate
how many darray elements were each myTypeelement, but that is a minor
adjustment and easily programmed. What this concept givesyou is tight
control over your data structures, efficient use of memory and at a
relativelylow cost in code.

Function Pointers in Types

Once you have created a type definition, you will usually need to create
one ormore subroutines or functions that act on that data. By using
function pointers, you cangroup the code that acts on this data right
along with the data itself. This gives you apowerful capability to
organize your data into code objects that operate as a single unit.

This is one of the ideas behind OOP, or object oriented programming;
encapsulating dataand the methods (subroutines and functions) that
operate on that data into a singleentity. While FreeBasic doesn't yet
support object oriented programming, you can derivesome of the benefits
of OOP by using functions pointers along with data when you createyour
type definitions.

You define a function (or subroutine) pointer by declaring a prototype
functiondeclaration with the type element name. The following code
snippet shows a typicaldeclaration.

Type myObject

arg1 As Integer

arg2 As Integer

ret As Integer

myFunc As Function(arg1 As Integer, arg2 As Integer) As Integer

End Type

Declare Function typeFunc(arg1 As Integer, arg2 As Integer) As Integer

...

Dim Obj as myObject

Obj.myFunc = @typeFunc

...

Function typeFunc(arg1 As Integer, arg2 As Integer) As Integer

...

End Function

The type definition is defined using data in the normal manner, along
with a field,

myFunc, that is defined As Function. When a field is defined As Function
or As Sub, thiscreates a pointer to the function or subroutine. Notice
that the type definition of myFuncdoesn't include a function, but does
include the parameter and return types. Since this isa pointer field,
the name isn't required, but the parameters and return type in
theprototype declaration, must match the actual function in order for
the compiler to do typechecking on the pointer field.

The Declare statement following the type is needed as a forward
reference so thatthe compiler knows that a function is defined somewhere
in the code. If you left out thedeclaration, you would get a variable
not declared error when trying the to compile thecode. You create an
instance of the type using the Dim statement, just as you have seenin
the other examples. Since myFunc is a pointer, you can't use it until
you initialize thepointer and you do this by using the Addressof
operator on the real function's name. Thiswill store the address of the
function in myFunc, which is used when calling the function.

The real function must be coded of course, so that you actually have
some code to callwhen using the function pointer.

The following program illustrates creating and using a function pointer
in a type

def.

1

Option Explicit

2

3

'Create a type definition that has data and function ptr

4

Type myObject

5

arg1 As Integer

6

arg2 As Integer

7

ret As Integer

8

myFunc As Function(arg1 As Integer, arg2 As Integer) As Integer

9

End Type

10

11

'Need to declare function for forward reference

12

Declare Function typeFunc(arg1 As Integer, arg2 As Integer) As Integer

13

'Create a type variable

14

Dim Obj As myObject

15

'Set the address of the function

16

Obj.myFunc = @typeFunc

17

'Set the data elements

18

Obj.arg1 = 1

19

Obj.arg2 = 5

20

'Call the function

21

Obj.ret = Obj.myFunc(obj.arg1, Obj.arg2)

22

'Show result

23

Print "Func return is";Obj.ret

24

25

Sleep

26

End

27

28

Function typeFunc(arg1 As Integer, arg2 As Integer) As Integer

29

Return arg1 + arg2

End Function

Listing 10.8: type-func.bas

Analysis: Lines 4 through 9 define a type with both integer data fields
and afunction pointer field. MyFunc is defined As Function along with
the function prototype.

This sets up myFunc as a function pointer. The Declaration statement in
line 12 is used asa forward reference to the actual function code. If
you did not supply the declaration, youwould get a variable not found
error on line 16. Line 14 creates a variable of the typeand line 16 uses
the Addressof operator to initialize the function pointer to the address
oftypeFunc, the actual function. Lines 18 and 19 initialize the data
fields, arg1 and arg2.

Line 21 actually calls the function with the proper arguments. Notice
that the dot notationis used in calling the function, myFunc as well as
passing the data to the function. Obj.retolds the functions return
value.

The program is closed using the Sleep and End commands, followed by
thefunction definition. Whenever you create a function pointer, you must
have somecorresponding function code in order to pass the address of
that code to the functionpointer.

When you run the program, you should see the following output.

 Func return is 6

Output 10.8: Output of type-func.bas

As you can see, function pointers are quite simple to define and use.
Not only isyour data encapsulated within a single code object, the
methods that act on that data arealso contained within that same object,
giving you a powerful way to organize your datastructures. The example
program is quite simple of course, but you can use this conceptto reduce
the complexity of your code. Suppose you are writing a game and the
enemyunits have been defined using a type definition. By also including
the subroutines orfunctions that act on that data within the type
definition, you have a single code objectthat fully describes an enemy.
If you need to make changes to the enemy code, you only

have to update a single code object, rather than a scattered bunch of
variables andsubroutines.

This method also enables you to pass information to functions or
subroutines as asingle unit, by simply declaring a parameter as the type
definition, and you have accessto both the data and methods within the
called function. This makes the code much more

reliable and easier to maintain. It also enables you to generalize the
code so that whenyou create these type of objects, they can be used in
other programs.

Forward References

There may be a time when you need to create two type definitions that
referenceeach other. Since FreeBasic is a single pass compiler, this
poses a problem since thecompiler will encounter a reference to a type
that hasn't been defined yet. The solution isto create a forward
reference of the second type. You do this by using the Type-Askeywords,
without the End Type. For example, suppose you have two types Type1
andType2. Type1 references Type2 and Type2 references Type1. It doesn't
matter what orderyou define the types, you will generate an error in the
compiler, because each type has areference that hasn't been defined yet.
In order for the compiler to compile successfullyyou need to create a
forward reference to the second type, and then use that referencein
defining the first type. The following code snippet illustrates this
concept.

'Forward reference

Type FT as Type2

Type Type1

fType as FT

End Type

Type Type2

fType as Type2

End Type

The code Type FT as Type2 creates the forward reference that is in turn
used in

the Type1 definition to refer to Type2, fType as FT. FT and Type2 are
actually the samething, FT is just an alias for the Type2 definition.
Whenever you need to have one or motetype definitions refer to each
other, you will need to create forward declarations for thethe types
that have not been defined when referenced.

Bit Fields

There is yet another data type that can be used in type definitions, the
bit field. Bitfields are defined as variable\_name: bits As DataType.
The variable name must befollowed with a colon and the number of bits,
followed by the data type. Only integerdata types are allowed within a
bit field. Bit fields are useful when you need to keep trackof boolean
type information, such as if a pixel is on or off. The following
programillustrates using bit fields within a type definition.

1

Option Explicit

2

3

Type BitType4

b1: 1 As Integer5

b2: 4 As Integer

6

End Type

7

8

Dim myBitType As BitType

9

10

myBitType.b1 = 1

11

myBitType.b2 = 1101

12

13

Print "Bit field 1: ";myBitType.b1

14

Print "Bit field 2: ";myBitType.b2

15

16

Sleep

17

End

Listing 10.9: bitfield.bas

Analysis: Lines 3 through 6 define a type with two bit fields. B1 is
defined as 1 bit,

and b2 is defined as 4 bits. Line 8 creates a variable of the type
definition. Line 10 setsb1 to 1. Since b1 is defined a 1 bit, the only
valid values are 0 or 1. Line 11 sets b2 to1101. Here there are four
bits so you can have a range of 0000 to 1111. Lines 13 and 14print out
the values of the bits. The program is closed in the usual way.

When you run the program you should see the following output.

Bit field 1: 1

Bit field 2: 13

Output 10.9: Output of bitfield.bas

The data type of the bit field determines how many bits you can declare
in a bitfield. Since an integer is 32 bits long, you could declare up to
32 bits in the field.

However, in most cases you would declare a single bit for each field,
and use a number offields to define the bit masking that you wish to
use. Using a single bit simplifies thecoding you need to do to determine
if a bit is set or cleared.

The Field Property

When you create a variable of a type definition, the type is padded in
memory. Thepadding allows for faster access of the type members since
the type fields are aligned ona 4 byte or Word boundary. However, this
can cause problems when trying to read a typerecord from a file that is
not padded. You can use the use field property to change thepadding of a
type definition. The field keyword is used right after the type name and
canhave the values 1, for 1 byte alignment (no padding), 2 for 2 byte
alignment and 4 for 4byte alignment. To define a type with no padding
you would use the following syntax.

Type myType field = 1

v1 As Integer

v2 As Byte

End Type

For 2 byte alignment you would use field = 2. If no field = property is
assigned,

then the padding will be 4 bytes. If you are reading a type definition
created by FreeBasicusing the default alignment, then you do not need to
use the field property.

If you reading a Quick Basic type record, then you will need to use
field = 1, as QB usedbyte alignment by default.

Type Initialization

You can initialize a type definition when you dimension the type just as
you canany of the intrinsic variables. The following code snippet
illustrates the syntax.

Type aType

a As Integer

b As Byte

c As String

End Type

Dim myType As aType =&gt; (12345, 12, "Hello")

In the Dim statement, the arrow operator is used to signal the compiler
that youare initializing the type variable. The type element values must
be enclosed inparenthesis, and separated by commas. The order of the
value list corresponds to theorder of the type elements, where a will be
set to 12345, b to 12 and c to “Hello”. Thefollowing short program
initializes a type using this syntax.

1

Option Explicit

2

3

'Create a type def

4

Type aType5

a As Integer6

b As Byte7

c As String

8

End Type

9

10

'Create and init the type

11

Dim myType As aType =&gt; (12345, 12, "Hello")

12

13

'Display values

14

With myType

15

Print .a16

Print .b17

Print .c

18

End With

19

20

Sleep

21End

Listing 10.10: type-init.bas

Analysis: Lines 4 through 8 define a type definition. Line 11 dimensions
the typevariable and sets the filed elements to the listed values. The
order of the values

correspond to the order of the field elements. Line 14 through 18 prints
the type valuesto the screen. The program is then closed in the usual
way.

When you run the program you should the following output.

 12345

Hello

Output 10.10: Output of type-init.bas

Initializing a type definition in a Dim statement is useful when you
need to have aset of initial values for a type, or values that will not
change during program execution.

Since the values are known at compile time, the compiler can doesn't
have to spendcycles loading the values during runtime.

Unions

Unions look similar to Types in their definition.

Union aUnion

b As Byte

s As Short

i As Integer

End Union

If this were a Type, you could access each field within the definition.
For a Union,

you can only access one field at any given time; all the fields within a
Union occupy thesame memory segment, and the size of the Union is the
size of the largest member. Inthis case, the Union would occupy four
bytes, the size of an Integer, with the b fieldoccupying 1 byte and the
s field occupying 2 bytes within the 4 byte integer space. Eachfield
starts at the first byte, so the s field would include the b field, and
the i field wouldinclude both the b field and the s field. The following
program illustrates this concept.

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

Option Explicit

'Define a union

Union aUnion

b As Byte

s As Short

i As Integer

End Union

Dim myUnion As aUnion

'Set the integer value

myUnion.i = 2047483641

'Print members

Print "Integer: ";Tab(10);Bin(myUnion.i)

Print "Byte: ";Tab(33);Bin(myUnion.b)

Print "Short: ";Tab(28);Bin(myUnion.s)

Sleep

End

Listing 10.11: union.bas

Analysis: Line 4 through 8 define the example union. Line 10 defines a
variable ofthe union definition. Line 13 sets the integer field to a
value that will overlap the b and sfields. Lines 15 through 17 print out
the values of each field of the union in binary so thatyou can see the
overlap of the values. The program is closed in the usual way.

When you run the program you should the following output.

Integer: 1111010000010100001111011111001

Byte: 11111001

Short: 1111011111001

Output 10.11: Output of union.bas

You can easily see the overlapped values in the output. While a union is
useful onits own, you can combine a union with a type definition to
create extremely flexible andefficient data structures.

Types in Unions

A good example of using a type definition in a union is the
Large\_Integer definitionfound in winnt.bi. The Large\_Integer data type
is used in a number of Windows functionswithin the C Runtime Library.
The following code snippet shows the Large\_Integerdefinition.

union LARGE\_INTEGER

type

LowPart as DWORD

HighPart as LONG

end type

QuadPart as LONGLONG

end union

The Dword data type is defined in windef.bi as an Uinteger, type DWORD
as

uinteger, and the Longlong type is defined as a Longint, type LONGLONG
as longint. A

Long is the same as an integer. Remember that a type occupies contiguous
memorylocations, so the HighPart field follows the LoPwart part field in
memory, the typeoccupies the same memory segment as the QuadPart field.
When you set QuardPart to alarge integer value, you are also setting the
values of the type fields, which you can thenextract as the LowPart and
HighPart. You can also do the reverse, that is by setting theLowPart and
HighPart of the type, you are setting the value of the QuadPart field.

As you can see, using a type within a union is an easy way to set or
retrieveindividual values of a component data type without resorting to
a lot of conversion code.

The layout of the memory segments does the conversion for you, providing
that thememory segments make sense within the context of the component
type. In theLarge\_Integer case, the LowPart and HighPart have been
defined to return theappropriate component values. Using values other
than Dword and Long would not returncorrect values for LowPart and
HighPart. You need to make sure when defining a typewithin a union, you
are segmenting the union memory segment correctly within the
typedefinition.

Unions in Types

A union within a type definition is an efficient way to manage data when
one fieldwithin a type can only be a single value. The most common
example of this is the Variantdata type found in other programing
languages.

FreeBasic does not have a Variant data type at this time. However, when
classes areadded to FreeBasic, it will be quite easy to create a Variant
data type and overload thearithmetic operators to create a Variant that
behaves just like the intrinsic data types.

Classes are planned for a future version of FreeBasic.

If you can only access a single field within a union, how do you know
which field toaccess when a union is contained within a type definition?
Usually you will include anidentifier field within the type, but outside
the union, that identifies which union field toaccess. The following
program illustrates this concept by creating a simple Variant data

type.

1

Option Explicit

2

3

'Union field ids

4

\#define vString 0

5

\#define vInteger 1

6

7

'Define type def with variable data fields

8

Type vType9

vt\_id As Integer10

Union11

s As String12

i As Integer13

End Union

14

End Type

15

16

'Create variant variable

17

Dim myVariant As vType

18

19

'This subroutine prints out value

20

Sub PrintVariant(v As vType)

21

If v.vt\_id = vString Then22

Print "String value: ";v.s23

Elseif v.vt\_id = vInteger Then24

Print "Integer value:";v.i25

End If

26

End Sub

27

28

'Set the id to a string

29

myVariant.vt\_id = vString

30

myVariant.s = "This is a string."

31

'Print the string value

32

PrintVariant myVariant

33

'Clear the string memory before seting the integer

34

myVariant.s = ""

35

'Set the id to an integer

36

myVariant.vt\_id = vInteger

37

myVariant.i = 300

38

'Print the integer value

39

PrintVariant myVariant

40

41

Sleep

42

End

Listing 10.12: simplevariant.bas

Analysis: Line 4 and 5 define the union ids. These values will be used
to determine which field within the union to access. Lines 20 through 26
define a subroutine that willprint the value of the union field based on
the id. If the id field is VString, then the s fieldwithin the union is
printed. If the id field is VInteger, then the i field is printed. Line
29sets the id field to Vstring and line 30 sets the union field s to a
string. The PrintVariantsubroutine is called in line 32 to print out the
value. Line 34 clears the allocated memoryof the dynamic string by
setting the union field s to an empty string. Line 36 sets the id field
to an integer, and the value of the union field i is set to300. Line 39
calls the PrintVariant subroutine to print the integer value. The
program isthen closed in the usual way.

Caution There are two subtle danger in this program that may not be
readilyapparent. Remember that a dynamic string is actually a pointer to
an allocated memorysegment. The union field s is actually a pointer to
this memory segment. Since the fieldss and i overlap in memory, setting
i to a value also sets s to a value; that is, in theprogram i is set to
300, which also sets s to 300. Since s is a pointer, trying to access
safter setting i will access memory location 300, which will be garbage
data and maycause the program to crash.

The other problem with this program is that it can potentially lead to a
memoryleak while the program is running. The string value is an
allocated memory segment.

Setting the integer value, overwrites the pointer address in s, which
means you have lostthe pointer address to the memory segment. The string
data still exists in memory, butnow that data is lost, causing a memory
leak. This is why the string value in the unionwas set to an empty
string before setting the integer value. Setting the string value to
anempty string deallocates the string data and frees the string pointer.

When using pointers within a union, great care must be taken to insure
that thepointer is pointing to the correct memory location, and that
they are deallocated correctlyto prevent memory leaks.

When you run the program you should see the following output.

String value: This is a string.

Integer value: 300

Output 10.12: Output of simplevariant.bas

Using a combination of unions and types within a program allows to
design customdata types that have a lot of flexibility, but care must be
taken to ensure that you areusing the data constructs correctly.
Improper use of these data types can lead to hard-tofind

bugs. The benefits however, out-weigh the risks and once mastered, are a
powerfulprogramming skill.

A Look Ahead 
-------------

There are times when you will need values that do not change during a
program.

These values are called Symbolic Constants and are the subject of the
next chapter.

Chapter 11 Symbolic Constants 
==============================

Constants are values that do not change during the life of the program.
Constantsare like variables in that the name of the constant refers to
the defined value, but unlike

a variable, these values cannot be changed in the program. There are two
importantreasons why constants should be used in your program. One, they
help to document theprogram. Suppose in your role-playing game you have
a weapon such as a broadsword. Ifyou define the broadsword as a
constant, which you can do with \#Define broadsword

12, you can then refer to the weapon id as broadsword, rather than 12.
The number 12

imparts no real information when you see it in the code; broadsword on
the the other

hand is quite clear and understandable.

The second reason to use a constant is code maintenance. There may come
a timewhen working on your role-playing game that you need to change the
value of thebroadsword id. If you have defined the id as a constant, you
only need to change it in asingle location, the place where you defined
the constant. If you had just used thenumber 12, you would have to
search through the code and change each instance where12 referred to the
broadsword. If the program is of any length at all, you will
probablymiss a reference or two, introducing bugs into your program.
Bugs that may be difficult tolocate and fix.

One of the things you will discover as you progress in your programming
adventure isthat programs are dynamic, not static. There is always a new
technique beingdeveloped that you can use, a new compiler function that
will improve your program,

and bugs that need to be fixed. The only thing that stays the same in a
program is thefact that programs continually evolve over time. You
should always keep in mind thatwhen you write a program, you will
probably end up making changes to the program,

and you should code accordingly. It may be easier to write 12 than it is
to writebroadsword, but a few extra seconds of typing will save you
hours when you need tochange 12 to 120.

\#Define as a Constant 
-----------------------

You have already seen \#Define at work in several of the example
programs.

\#Define is a preprocessor command, where the defined symbol is
physically replaced inthe code by the associated value. \#Define of
course is used in a number of situations,

from creating macros to conditional compilation, but it is also useful
for creatingconstants within your program. If you look through the
declaration files in the includefolder of your FreeBasic installation,
you will see that \#Define is used extensively forconstant values. Since
the compiler replaces the symbol definition with the defined

value, it is a very efficient coding method. It is also quite easy to
use, as the followingcode snippet illustrates.

'Define directions

\#Define north 1

\#Define neast 2

\#Define east 3

\#Define seast 4

\#Define south 5

\#Define west 6

\#Define swest 7

\#Define nwest 8

Once you define the constants, you can use the symbols in your programs
just asyou would the values. You have already seen this technique used
in some of the exampleprograms presented in the book.

The Const Keyword 
------------------

The Const keyword is another method to define constants in your program.
Theformat is similar to the \#define, as the following code snippet
illustrates.

Const xk = Chr(255)

Const key\_up = xk & Chr(72)

Const key\_dn = xk & Chr(80)

Const key\_rt = xk & Chr(77)

Const key\_lt = xk & Chr(75)

These constants are the character codes returned by Inkey for the arrow
keys.

Inkey returns a two byte string for the extended keys, Chr(255) + the
extended keycharacter code. Inkey is covered in detail in the chapter on
Console Programming. To usethese constaints in your program you would
just use key\_lt for example to check to see ifthe left arrow key had
been pressed.

Const Versus \#Define 
----------------------

As you can see Const and \#Define are similar constructs. The question
thenbecomes, which one should you use? Remember that \#Define replaces
the symbol namewith the text following the symbol. If you wrote \#Define
key\_up xk & Chr(72), then

the code xk & Chr(72) would be replace the symbol key\_up. If you had
several places

where you used key\_up, then there would be several instances of xk &
Chr(72) in your

program. You can see that by using \#Define in this case your program
would beperforming the same calculation over and over. It is much more
efficient to use Const inthis case, since the calculation is only done
once, when the Const is defined.

On the other hand, if you are defining single constant values, such as
compassdirections, then using a \#Define is preferable to using Const.
For a Const value, thecompiler must do a lookup in the symbol table and
it is much more efficient to simplereplace the symbol with the value
using \#Define.

Enumerations 
-------------

Enumerations are sequential values that the compiler can calculate for
you. Tocreate an enumeration, you use enclose the values within an
Enum-End Enum block. Thecompass direction defined above could also be
defined as an enumeration.

Enum compass

north = 1

neast

east

seast

south

west

swest

nwest

End Enum

In this example, neast will be defined as 2, with east defined as 3 and
so on. If nostarting value is set, enumerations start at 0. You can also
change the sequence within anenumeration by setting a symbol to a value
using =, and any following symbols will beincremented from this starting
point.

Enum compass

north = 1

east

south

west

neast = 10

seast

swest

nwest

End Enum

In this example, the value of seast will be 11, swest will be 12 and so
on. Once youdefine an enumeration, you can create variables of the Enum
and use that variable within

your program.

Dim aCompass as compass

You can then use the enumeration values to initialize the variable. The
followingcode snippet set aCompass to the north-defined value.

aCompass = north

Caution The compiler does not check to see if the value being passed to
the Enumvariable is within the defined range of the enumeration. It is
the responsibility of theprogrammer to ensure that the Enum variable
contains the correct values.

A Look Ahead 
-------------

In the next chapter you will see how to create and work with Arrays in
FreeBasic.

149

Chapter 12 Arrays 
==================

Arrays are probably the single most useful programming construct that is

available to you in FreeBasic. Many problems that you will try to solve
with aprogramming solution involve data arranged in tabular format, and
arrays are perfect formanaging this type of data. Understanding arrays
is crucial skill in becoming a competent

programmer.

Arrays are contiguous memory segments of a single or composite data
type. Youcan think of an array as a table, with rows and columns of
data. An array can have one ormore rows, and each row can have one or
columns. The number of rows and columns

define the dimensions of the array. FreeBasic uses the row-major scheme
for arrays,

which means that the first dimension references the row in an array that
has more thanone dimension. FreeBasic supports up to eight dimensions in
an array.

One-Dimensional Arrays 
-----------------------

An array with a single row is called a one-dimensional array. If an
array is a single-

dimensional array, then the row is not defined in the declaration, only
the number ofcolumns in the row. Since an array requires a minimum of
one row, the row is understoodto exist in this case. The following code
snippets create a single-dimension integer arrayusing the different
array definition schemes available in FreeBasic.

Dim myArray(10) as Integer

This will define an array with a single row and 11 columns, with column
indexes(numbers) ranging from 0 to 10. The base array index is 0 if the
lower bound of the arrayis not defined. This behavior can be changed
using the Option Base n compilerdirective. Setting Option Base 1 with
the above example would result in an array with 10columns, with the
indexes ranging from 1 to 10. The Option Base directive must bedefined
before dimensioning any arrays.

Dim myArray(1 to 10) as Integer

This example will define a single-dimension array with 10 columns, with
indexesranging from 1 to 10.

### One-Dimensional Array Indexes 

You access each element of an array using an index value. In the case of
a single-

dimension array, the index would refer to a column number in the default
row. The formatis to use the array variable, with the index surrounded
by parenthesis.

myArray(5) = 7

This would set the value of column 5 of myArray to 7.

myInt = myArray(5)

This will set the value of myInt to the current value of column 5 in
myArray.

Two-Dimensional Arrays 
-----------------------

A two-dimensional array is an array that has more than one row, along
with thedefined columns. A two-dimensional array is like a table, with a
defined number of rows,

where each row has a defined number of columns. The following code
snippet defined anarray using the default method.

Dim myArray(2, 10) as Integer

The first dimension defines the number of rows in the array, while the
seconddimension defines the number of columns in each row. In this
example, the array has 3rows, numbered 0 to 2, and each row has 11
columns, numbered 0 to 10, if Option Basehas not been defined. If Option
Base 1 had been used, then the row indexes would rangefrom 1 to 2, and
the column indexes would range from 1 to 10.

You can also define the lower and upper bounds of the array.

Dim myArray(1 to 2, 1 to 10) as Integer

This definition would set the number of rows to 2, numbered 1 to 2 and
the

number of columns to 10, numbered 1 to 10.

### Two-Dimensional Array Indexes 

To access the array elements you would use two indexes. The first index
selectsthe row, and the second index selects a column within that row.

myArray(1, 5) = 7

This code would set column 5 in row 1 to 7.

myInt = myArray(1, 5)

This code would set myInt to the current value contained within column 5
of row 1of myArray.

Multi-Dimensional Arrays 
-------------------------

For arrays of three or more dimensions, you would use the same format as
listedabove, taking into account the progression of the array
dimensions. For a three-

dimensional array, the first dimension would be the row, the second the
column, the thirdwould be the z-order, or depth, of each column. For
example, to define a cube in space,

you would use the y,x,z format, where y defines the vertical axis, x
defines the horizontalaxis and z defines the depth axis. To create an
array in this format you could define the

array as Dim myCube(y, x, z) as Integer. MyCube(10, 10, 10) would create
a cube

with 11 vertical units, 0 to 10, 11 horizontal units, 0 to 10 and 10
depth units, 0 to 10. Toaccess the center of the cube, you would use
iCenter = myCube(5, 5, 5).

You will probably never need to use arrays of more than three
dimensions, unlessyou are doing some advanced mathematical calculations.
However, if you need to usehigher-dimensional arrays, the same
principles apply.

The following program illustrates creating and accessing a two
dimensional array.

Option Explicit

'Create a twodimensional

array

Dim As Integer myArray(1 To 2, 1 To 10), i, j

'Load some data into the array

For i = 1 To 2

For j = 1 To 9

myArray(i, j) = Rnd \* 10

Next

Next

'Print data in array

For i = 1 To 2

For j = 1 To 9

Print "row:";i;" col:";j;" value:";myArray(i, j)

Next

Next

Sleep

End

Listing 12.1: arrayindex.bas

Analysis: Line 4 creates a two-dimensional array with two rows, with
each rowhaving ten columns. The working variables i and j are also
declared on the same line.

Lines 7 through 11 load some random data into the array. A nested
For-Next loop is thecommon way to access multi-dimensional arrays. The
variable i will select the rowindexes while the j variable will access
the column indexes.

Lines 14 through 18 will print the values stored in the array. The
format is identicalto the load code. The program is closed in the usual
way.

When you run the program you should see the following output.

row: 1 col: 1 value: 0

row: 1 col: 2 value: 6

row: 1 col: 3 value: 2

row: 1 col: 4 value: 8

row: 1 col: 5 value: 6

row: 1 col: 6 value: 5

row: 1 col: 7 value: 4

row: 1 col: 8 value: 9

row: 1 col: 9 value: 8

row: 2 col: 1 value: 7

row: 2 col: 2 value: 2

row: 2 col: 3 value: 9

row: 2 col: 4 value: 7

row: 2 col: 5 value: 5

row: 2 col: 6 value: 3

row: 2 col: 7 value: 0

row: 2 col: 8 value: 1

row: 2 col: 9 value: 4

Output 12.1: Output of arrayindex.bas

Dynamic Arrays

The arrays described above are static arrays; the array size cannot
change duringprogram execution. You can also create dynamic arrays that
can change size duringexecution. Dynamic arrays are useful for creating
data structures such as stacks or

queues.

In order to use dynamic arrays in your program you need to include the
Option

Dynamic directive in your program. Static arrays, the arrays described
above, are kept onthe heap, but dynamic arrays are allocated from the
computer's pool of memory soOption Dynamic is needed to tell the
compiler to dynamically allocate the array. You candimension a dynamic
array in two ways. The first is to declare the array size in the
Dimstatement and then resize it using Redim or Redim Preserve. The
second is to not specifythe array size, use empty parenthesis, and then
use Redim or Redim Preserve to size thearray. Redim will size the array
and clear the array contents. Redim Preserve will size thearray and keep
any existing data in th array.

There are a couple of exceptions to this. When declaring an array using
variables for theindex values, the array is implicitly dynamic. You can
also declare an array withoutspecifying index values, that is using an
empty parentheses in the array declaration,

and then use Redim to resize the array without specifying Option
Dynamic.

The following program creates a simple integer stack and then
manipulates

the stack.

1

Option Explicit

2

Option Dynamic

3

4

'Create an integer stack. The 0 index will be our empty marker.

Dim As Integer stack(0), top = 0, i, ivalue

6

7

'This will push a value on the stack, update the top of stack

8

Sub PushValue(astack() As Integer, stacktop As Integer, value As
Integer)

9

'Increment the top of the stack

stacktop += 111

'Resize the stack12

Redim Preserve astack(stacktop)

13

astack(stacktop) = value

14

End Sub

'This will pop a value off the stack, update top of stack

16

Function PopValue(astack() As Integer, stacktop As Integer) As Integer17

Dim As Integer ret18

19

If stacktop = 0 Then

ret = 021

Else22

ret = astack(stacktop)

23

stacktop =

124

Redim Preserve astack(stacktop)

End If

26

Return ret

27

End Function

28

29

'Push five values on to stack

Print "Pushing values on stack..."

31

For i = 1 To 532

ivalue = i \* 233

PushValue stack(), top, ivalue34

Print "Stack top:";Ubound(stack),"Value:";ivalue

Next

36

Print

37

38

'Pop the values off the stack

39

Print "Popping values from stack..."

ivalue = PopValue(stack(), top)

41

Do While ivalue &gt; 042

Print "Stack Value:";ivalue43

ivalue = PopValue(stack(), top)

44

Loop

Print

46

47

'Check stack size

48

Print "Stack size after pops:";Ubound(stack)

49

50

Sleep

51

End

Listing 12.2: stack.bas

Analysis: In line the Option Dynamic directive is used to create the
stack arrayusing dynamic memory. Line 5 dimensions the working
variables. The 0 index in the stackarray will be used to indicate that
the stack is empty. Even though this wastes oneinteger, it makes the
code easier to implement. Line 8 through 14 defines the code topush a
value on to the the stack. The parameters of the subroutine are the
stack array,

the top-of-stack variable, and the value to push on to the stack. You
could determine thetop of the stack using the Ubound function, however
in a real stack implementation, youwill probably need to pass the
top-of-stack to other functions, and keeping the value in avariable will
reduce the number of calculations the program must do.

Line 10 increments the stack top variable, and line 12 uses Redim
Preserve toresize the array, while keeping the existing data in the
array. Line 13 set the new arraylocation to the value passed to the
subroutine.

Line 16 through 27 pops the top value of the stack, if the stack index
is grater thanzero, updates the top-of-stack variable and then returns
the popped value. Line 19 and20 checks to make sure that the stack has
some data. If the index is 0, the stack is

empty. Lines 22 through 24 get the current value of the top stack item,
updates the stackpointer variable and then resizes the stack using Redim
Preserve. Lines 31 through 35use a For-Next loop to push 5 values on to
the stack. Lines 40 through 44 pop the valuesoff the stack. A Do-Loop is
used to pop the values since when the stack is empty, thereturn value
will be 0. Line 48 then cheks to see if all the values have been popped
fromthe stack.

The program is closed in the usual way.

When you run the program you will see the following output.

Pushing values on stack...

Stack top: 1 Value: 2

Stack top: 2 Value: 4

Stack top: 3 Value: 6

Stack top: 4 Value: 8

Stack top: 5 Value: 10

Popping values from stack...

Stack Value: 10

Stack Value: 8

Stack Value: 6

Stack Value: 4

Stack Value: 2

Stack size after pops: 0

Output 12.2: Output of stack.bas

Stacks have a wide range of uses, however most implementations use
pointerssince it is much faster to manipulate a pointer than it is an
array. The advantage of anarray is the simplicity of use, and the
readability of the code, but if you need speed, youshould use a pointer
memory array for stacks.

You can only Redim or Redim Preserve the first index, that is the row,
in amultidimensional array.

Array Functions 
----------------

There are a number of functions that you can use to manage arrays. The
followingtable lists the array functions available in FreeBasic.

Function Syntax Comment

Clear Clear array, value,

num\_bytes

Sets num\_bytes in array tobyte value.

Erase Erase array Erases dynamic arrays frommemory, or clears static

arrays.

Lbound B = Lbound(array)

B = Lbound(array,

dimension)

Returns the lowest index of

a single or multidimensionalarray. The dimensionparameter is the
dimensionto check in a

multidimensional arraywhere the first dimension is

Function Syntax Comment

1, the second dimension is

2, and so on.

Option Dynamic Option Dynamic Allocates arrays intodynamic memory
bydefault.

Option Static Option Static Clears a previous OptionDynamic. All
subsequentarrays will be allocated onthe heap.

Preserve Redim Preserve Preserves data in an arraywhen resized using
theRedim statement.

Redim Redim array(dimensions) asDataType

Resizes an array to sizedimensions.

Ubound B = Lbound(array)

B = Lbound(array,

dimension)

Returns the highest index ofa single or multidimensionalarray. The
dimensionparameter is the dimensionto check in a

multidimensional arraywhere the first dimension is

1, the second dimension is

2, and so on.

Table 12.1: Array Functions

Out of all the functions, you will probably use the Lbound and Ubound
functionsthe most, especially when working with dynamic arrays. The
following program uses bothfunctions to get the size of a two
dimensional array.

1

Option Explicit

2

Option Dynamic

3

4

'Create a dynamic array

5

Dim As Integer myArray(), i, nb

6

'Resize array with two dimensions

7

Redim myArray(1 To 1, 1 To 5)

8

9

'Print upper and lower bounds for each row and column

10

Print "First Redim"

11

Print ""

12

Print "Min Row Index:";Lbound(myArray, 1);

13

Print " Max

Row Index:";Ubound(myArray, 1)

14

Print "Min Column index:";Lbound(myArray, 2);

15

Print" Max

Column index:";Ubound(myArray, 2)

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

Print

Print "Additional Redims"

Print ""

'Redim array five times

For i = 1 To 5

 nb = Ubound(myArray, 1) + 1

Redim myArray(1 To nb, 1 To 5)

'Print new array size

Print "Min Row Index:";Lbound(myArray, 1);

Print " Max

Row Index:";Ubound(myArray, 1)

Print "Min Column index:";Lbound(myArray, 2);

Print " Max

Column index:";Ubound(myArray, 2)

Print

Next

Sleep

End

Listing 12.3: ulbound.bas

Analysis: Line 2 set the compiler directive Option Dynamic so that the
array isallocated in dynamic memory. Line 5 creates a dynamic array with
no dimensionsspecified. Line 7 uses Redim to create a two-dimensional
array. Lines 10 through 15 printthe upper and lower bounds using Lbound
and Ubound respectively. Notice that thedimension parameter is used to
specify which dimension to get the lower and upperbounds. 1 is used to
get the bounds for the first dimension, and 2 is used to get thesecond
dimension.

Lines 20 through 29 resize the first dimension of the array and print
the new lowerand upper indexes. Line 21 gets the current upper bound of
the first dimension, 1 isadded to that value and then Redim is used in
line 22 to resize the first dimension of the

array. Lines 24 through 27 get the new bounds and print the values to
the screen.

The program is closed in the usual way.

When you run the program you should see the following output.

First Redim

Min Row Index: 1 Max

Row Index: 1

Min Column index: 1 Max

Column index: 5

Additional Redims

Min Row Index: 1 Max

Row Index: 2

Min Column index: 1 Max

Column index: 5

Min Row Index: 1 Max

Row Index: 3

Min Column index: 1 Max

Column index: 5

Min Row Index: 1 Max

Row Index: 4

Min Column index: 1 Max

Column index: 5

Min Row Index: 1 Max

Row Index: 5

Min Column index: 1 Max

Column index: 5

Min Row Index: 1 Max

Row Index: 6

Min Column index: 1 Max

Column index: 5

Listing 12.4: Output of ulbound.bas

The first Redim sets the initial bounds for the array. The additional
Redims increasethe number of rows in the array, while leaving the number
of columns in intact. Keep inmind that arrays in FreeBasic are
table-like, where each row has the same number ofcolumns. Ragged arrays,
where each row has a different number of columns, cannot becreated in
FreeBasic using arrays. You would have to use pointers to create a
ragged

array.

Arrays of Types 
----------------

Type definitions allow you to group related data into a single entity,
and often youwill need more than one instance of a type to fully express
the data. Arrays of types allowyou create multiple instances of a type
definition that can be easily managed using thearrays functions. An
example of this usage may be an inventory system for your RPG, aseries
of document descriptions within an editor, and a set of employee records
from arandom access database.

You create arrays of types just as you would with any of the intrinsic
data types.

The following code snippet illustrates the syntax.

Type myPoint

x As Integer

y As Integer

End Type

Type myLine

p1 As myPoint

p2 As myPoint

char As String \* 1

End Type

Dim myLineSet (1 to 3) as myLine

The code defines a set of 3 lines, with endpoints p1 and p2, where each
endpointis located at row and col. The following program illustrates
using this definition to printsome lines to the console screen.

1

Option Explicit

2

3

'Define the point

4

Type myPoint

5

x As Integer

6

y As Integer

7

End Type

8

9

'Define the line

10

Type myLine

11

p1 As myPoint

12

p2 As myPoint

13

char As String \* 1

14

End Type

15

16

'Create a set of 3 lines

17

Dim myLineSet (1 To 3) As myLine

18

Dim As Integer i

19

20

'This subroutine uses the Bresenham Line algorithm

21

'to print a line on the console screen. Google

22

'"Bresenham Line algorithm" for more information.

23

Sub DrawLine(aLine As myLine)

24

Dim As Integer i, deltax, deltay, num25

Dim As Integer d, dinc1, dinc226

Dim As Integer x, xinc1, xinc227

Dim As Integer y, yinc1, yinc228

Dim As Integer x1, y1, x2, y229

30

'Get the endpoint coordinates31

x1 = aLine.p1.x32

y1 = aLine.p1.y33

x2 = aLine.p2.x34

y2 = aLine.p2.y35

36

'Get the delta change in both x and y37

deltax = Abs(x2 x1)

38

deltay = Abs(y2 y1)

39

40

'Calculate the slope of the line41

If deltax &gt;= deltay Then

42

num = deltax + 143

d = (2 \* deltay) deltax44

dinc1 = deltay Shl 145

dinc2 = (deltay deltax)

Shl 146

xinc1 = 147

xinc2 = 148

yinc1 = 049

yinc2 = 150

Else51

num = deltay + 152

d = (2 \* deltax) deltay53

dinc1 = deltax Shl 154

dinc2 = (deltax deltay)

Shl 155

xinc1 = 056

xinc2 = 157

yinc1 = 158

yinc2 = 159

End If60

61

If x1 &gt; x2 Then62

xinc1 = xinc163

xinc2 = xinc264

End If65

66

If y1 &gt; y2 Then67

yinc1 = yinc168

yinc2 = yinc269

End If70

71

x = x172

y = y173

Locate y, x74

Print aLine.char;

75

For i = 2 To num76

'Get the next iteration of the line77

If d &lt; 0 Then78

d = d + dinc179

x = x + xinc180

y = y + yinc181

Else82

d = d + dinc283

x = x + xinc284

y = y + yinc285

End If86 Locate y, x

87

88

89

90

91

92

93

94

95

96

97

98

99

100

101

102

103

104

105

106

107

108

109

110

111

112

 Print aLine.char;

Next

End Sub

'Returns a random number between low and high

Function GetRandom(lowerbound As Integer, upperbound As Integer) As
Integer

GetRandom = Int((upperbound lowerbound

+ 1) \* Rnd + lowerbound)

End Function

Randomize Timer

'Initialize and print the lines

For i = Lbound(myLineSet) To Ubound(myLineSet)

 'Set the first endpoint coordinates

myLineSet(i).p1.x = GetRandom(1, 80)

myLineSet(i).p1.y = GetRandom(1, 25)

'Set the second endpoint coordinates

myLineSet(i).p2.x = GetRandom(1, 80)

myLineSet(i).p2.y = GetRandom(1, 25)

'Get the display character

myLineSet(i).char = Chr(GetRandom(33, 47))

'Print the line

DrawLine myLineSet(i)

Next

Sleep

End

Listing 12.5: arrayoftypes.bas

Analysis: Lines 4 through 7 define the coordinates for the an endpoint
of a line.

Lines 10 through 14, define a line, with two endpoints and the character
used to print theline on the console screen. Line 17 defines a set of
three lines, and line 18 defines a

working variable that will be used in a For-Next loop that will
initialize and display theline.

Lines 23 through 89 define a subroutine that implements the Bresenham
Linealgorithm to print the line to the console screen. There are a
number of resources on theInternet that explain the algorithm in detail
and can be found using your favorite searchengine.

Lines 92 through 94 define a function that will return a random integer
in therange of lowerbound to upperbound, inclusive. Line 96 initializes
the random numbergenerator by seeding the generator with the current
Timer value. Randomize Timerensures that each call to Rnd will return a
different random number. Without the

Randomize statement, Rnd will return the same sequence of random number.

Line 98 through 109 initialize each line in the array and then calls the
DrawLinesubroutine to print the line. When accessing the fields of a
type within an array, you mustspecify which array element you are
accessing by using parentheses with an index value,

jut as you would an intrinsic data type. You can then access each
element within the typeusing the familiar dot notation you saw in the
chapter on composite types. Notice thatthe syntax is similar to the
syntax used in the type memory array example, and the rulesare accessing
type fields is the same.

Once each array element has been initialized and each line printed, the
program isclosed in the usual way.

When you run the program you should see something like the following
output.

 %%%

 %%%

 %% )

 %%% )

 %%% )

 %%% )

 %%% )

 %% )

 %%% )

 %% )

 //////

//////////

//////////

//////////

//////////

//////////

/////

Output 12.3: Output of arrayoftypes.bas

Your output will vary since the end points of the lines, and the line
character arerandom generated.

Arrays in Types

As you saw in the chapter on composite types, type fields be both
intrinsic andcomposite type. You can also create static arrays within a
type definition. In the listingabove, you can see that a line has two
endpoints. Rather than using two distinct fields,

you can create an array of endpoints that describe the line. The
following code listing is amodification of the previous listing, using
an array to describe the endpoints.

1

Option Explicit

2

3

'Define the point

4

Type myPoint

x As Integer

6

y As Integer

7

End Type

8

9

'Define the line

Type myLine11

pts(1 To 2) As myPoint12

char As String \* 1

13

End Type

14

'Create a set of 3 lines

16

Dim myLineSet (1 To 3) As myLine

17

Dim As Integer i, j

18

19

'This subroutine uses the Bresenham Line algorithm

'to print a line on the console screen. Google

21

'"Bresenham Line algorithm" for more information.

22

Sub DrawLine(aLine As myLine)

23

Dim As Integer i, deltax, deltay, num24

Dim As Integer d, dinc1, dinc2

Dim As Integer x, xinc1, xinc226

Dim As Integer y, yinc1, yinc227

Dim As Integer x1, y1, x2, y228

29

'Get the endpoint coordinates

x1 = aLine.pts(1).x31

y1 = aLine.pts(1).y32

x2 = aLine.pts(2).x33

y2 = aLine.pts(2).y34

'Get the delats change in both x and y36

deltax = Abs(x2 x1)

37

deltay = Abs(y2 y1)

38

39

'Calculate the slope of the line

If deltax &gt;= deltay Then41

num = deltax + 142

d = (2 \* deltay) deltax43

dinc1 = deltay Shl 144

dinc2 = (deltay deltax)

Shl 1

xinc1 = 146

xinc2 = 147

yinc1 = 0

164

48

yinc2 = 149

Else50

num = deltay + 151

d = (2 \* deltax) deltay52

dinc1 = deltax Shl 153

dinc2 = (deltax deltay)

Shl 154

xinc1 = 055

xinc2 = 156

yinc1 = 157

yinc2 = 158

End If59

60

If x1 &gt; x2 Then61

xinc1 = xinc162

xinc2 = xinc263

End If64

65

If y1 &gt; y2 Then66

yinc1 = yinc167

yinc2 = yinc268

End If69

70

x = x171

y = y172

Locate y, x73

Print aLine.char;

74

For i = 2 To num75

'Get the next iteration of the line76

If d &lt; 0 Then77

d = d + dinc178

x = x + xinc179

y = y + yinc180

Else81

d = d + dinc282

x = x + xinc283

y = y + yinc284

End If85

Locate y, x86

Print aLine.char;

87

Next

88

End Sub

89

90

'Returns a random number between low and high

91

Function GetRandom(lowerbound As Integer, upperbound As Integer) As
Integer92 GetRandom = Int((upperbound lowerbound

+ 1) \* Rnd + lowerbound)

93

94

95

96

97

98

99

100

101

102

103

104

105

106

107

108

109

110

111

112

End Function

Randomize Timer

'Initialize and print the lines

For i = Lbound(myLineSet) To Ubound(myLineSet)

 For j = Lbound(myLineSet(i).pts) To Ubound(myLineSet(i).pts)

'Set the first endpoint coordinates

myLineSet(i).pts(j).x = GetRandom(1, 80)

myLineSet(i).pts(j).y = GetRandom(1, 25)

'Set the second endpoint coordinates

myLineSet(i).pts(j).x = GetRandom(1, 80)

myLineSet(i).pts(j).y = GetRandom(1, 25)

'Get the display character

myLineSet(i).char = Chr(GetRandom(33, 47))

'Print the line

 Next

DrawLine myLineSet(i)

Next

Sleep

End

**Listing 12.6: arrayintypes.bas**

Analysis: This program is identical to the previous program, except that
thisprogram uses an array to describe the endpoints of the line. Only
the changes to theprogram will discussed in this section.

Line 11 defines a single dimension array of endpoints that has two
elements. Inlines 97 through 110, the program initializes each line
element. The outer loop selectseach line type within the line set array.
The inner For-Next loop then selects eachendpoint element with the
endpoint array. Notice that you an use Lbound and Ubound forthis array,
just as you can with the main array. Arrays within a type definition are
truearrays, and all the functions available in FreeBasic can be used
with embedded arrays.

The inner j loop Lbound and Ubound use the outer loop specification,
myLineSet(i).pts,

to select a line element within the line set array, and then the
function is applied to theembedded array. The endpoints are then
initialized using both the i and j specifications,

myLineSet(i).pts(j).x = GetRandom(1, 80). The variable i selects a line
while j

selects an endpoint within the selected line. The dot notation is used
to reference each

field within the type definition, including the endpoint array. Again,
the notation andprinciples are similar to a type memory array.

The program is closed in the usual way after printing all the lines.

The output of this program is the same as the previous program and is
not shownhere. Using an array for the endpoints enables you to easily
extend the line definition tosupport not only lines, but triangles and
squares. The following code snippet shows onepossible definition.

Type myObj

objid As Integer

Union

myLine(1 To 2) As myPoint

myTriangle(1 To 3) As myPoint

mySquare(1 To 4) As myPoint

End Union

char As String \* 1

End Type

The objid field would indicate which type of object is contained within
thedefinition. That is, a 1 may indicate a line, a 2 may indicate a
triangle and a 3 mayindicate a square. Since the definition defines a
single object, a union is used to enclosethe endpoint arrays to maximize
memory usage. To print the object to the screen, youwould examine the
objid and then use the Lbound and Ubound on the appropriateendpoint
array definition, printing the number of lines that correspond to the
type ofobject. One further enhancement you can make to this program is
to add a functionpointer to the type definition, and then write print
routines that correspond to the type ofobject being printed. Using this
technique will enable you to further extend theusefulness of the code by
simplifying the process of adding new objects to the typedefinition. For
example, if you needed to be able to describe a cube, you would
simplyadd an new array to the union, add a cube print function, and the
type definition wouldbe able to print a cube by simply adding a few
lines of code, while keeping the originalfunctionality intact.

Array Initialization 
---------------------

You can initialize an array with values when using the Dim statement in
a mannersimilar to initializing any of the other intrinsic data types,
and type definitions. Thefollowing code snippet illustrates the syntax
using a one dimensional array.

Dim aArray(1 to 5) As Integer =&gt; {1, 2, 3, 4, 5}

This code snippet dimensions a ubyte array with 5 elements, then sets
theelements to the list contained within the curly brackets. The arrow
operator, =&gt; tells thecompiler that the list following the Dim
statement should be used to initialize the array.

You can also dimension multidimensional arrays in the same manner, by
specifyingblocks of data enclosed within curly braces as the following
code snippet illustrates.

Dim bArray(1 to 2, 1 to 5) As Integer =&gt; {{1, 2, 3, 4, 5}, \_

{6, 7, 8, 9, 10}}

In this example, the first block, {1, 2, 3, 4, 5}, corresponds to row 1,
and thesecond block, {6, 7, 8, 9, 10}, corresponds to row 2. Remember
that FreeBasic arrays arerow-major, so the row is specified before the
column. When you initialize an array in thismanner, you must be sure
that the number of elements defined will fit into the array.

The following programs initializes two arrays and print the values to
the console.

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

Option Explicit

Dim aArray(1 To 5) As Integer =&gt; {1, 2, 3, 4, 5}

Dim bArray(1 To 2, 1 To 5) As Integer =&gt; {{1, 2, 3, 4, 5}, \_

{6, 7, 8, 9, 10}}

Dim As Integer i, j

'Print aArray values.

For i = 1 To 5

 Print "aArray(";i;" ):";aArray(i)

Next

Print

'Print bArray values.

For i = 1 To 2

For j = 1 To 5

Print "bArray(";i;",";j;" ):";bArray(i, j)

Next

Next

Sleep

End

Listing 12.7: arrayinit.bas

Analysis:

Line 3 creates a single-dimension array and initializes the values of
thearray. Line 4 creates a two-dimensional array and initializes the
both rows of the array.

Line 9 through 11 print the contents of the first array to the screen
and lines 15 through19 print the contents of the second to the screen.
The program is then closed in the usual

way.

When you run the program you should see the following output.

aArray( 1 ): 1

aArray( 2 ): 2

aArray( 3 ): 3

aArray( 4 ): 4

aArray( 5 ): 5

bArray( 1, 1 ): 1

bArray( 1, 2 ): 2

bArray( 1, 3 ): 3

bArray( 1, 4 ): 4

bArray( 1, 5 ): 5

bArray( 2, 1 ): 6

bArray( 2, 2 ): 7

bArray( 2, 3 ): 8

bArray( 2, 4 ): 9

bArray( 2, 5 ): 10

Listing 12.8: Output of arrayinit.bas

As you can see from the output, both arrays have been initialized
correctly, andwithout using a loop to load the data into the array. You
can initialize arrays of any sizeusing this method, although large
arrays get a bit hard to work with and it is important tomaintain the
proper order of data in the initialization block.

Type Array Initialization 
--------------------------

Since you can initialize a type definition and an array, it stands to
reason you cando the same with a type array. In the chapter on type
definitions you saw the syntax forinitializing a type, and here you have
seen how to initialize an array. To initialize a typearray, you use both
the type initialization syntax with the array initialization syntax,
asyou would expect. The following code snippet illustrates this combined
syntax.

Type aType

a As Integer

b As Byte

c(1 To 2) As Zstring \* 10

End Type

Dim As aType myType(1 To 2) =&gt; { (1234, 12, {"Hello", "World"}), \_

(5678, 24, {"From", "Freebasic"}) \_

}

The curly brackets signify that this is an array initialization, while
the parenthesisindicate the type initialization. Since the type has an
embedded array, you use the curlybrackets to load the data into the
embedded array, just as you would a stand-alone array.

If the embedded array was a multidimensional array, then you would need
to wrap eachrow in { and } just as you would a stand-alone array.

The following program shows how all this works together.

1

Option Explicit

2

3

'Create a type definiton

4

Type aType5

a As Integer6

b As Byte7

c(1 To 2) As Zstring \* 10

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

End Type

'Dimension and init the type array

Dim As aType myType(1 To 2) =&gt; { (1234, 12, {"Hello", "World"}), \_

(5678, 24, {"From", "Freebasic"}) \_

}

'Working variables

Dim As Integer i, j

'Display type values

For i = 1 To 2

Print "Type array index: ";i

With myType(i)

 Print .a

Print .b

For j = 1 To 2

 Print .c(j)

 Next

End With

Print

Next

Sleep

End

Listing 12.9: typearray-init.bas

Analysis: Lines 4 through 8 define the type definition. Line 11
dimensions andinitializes the type definition array. The type elements
are enclosed in parenthesis, whilethe embedded array is enclosed within
curly brackets. Line 15 creates some workingvariables for the For-Next
loops. Lines 18 through 28 print the values to the consolescreen using a
With block. The program is closed in the usual way.

When you run the program you should see the following output.

Type array index: 1

1234

12

Hello

World

Type array index: 2

5678

24

From

Freebasic

Output 12.4: Output of typearray-init.bas

CRT Array Functions 
--------------------

There are a few CRT functions that you can use to manipulate arrays. The
followingtable lists the Mem\* functions which are defined in string.bi.

Function Syntax Comment

Memchr Ptr =

Memchr(@Array(start),

byte\_value, Ubound(Array))

Returns a pointer tobyte\_value in byte Array, orNull pointer if
byte\_value isnot found. Memchr onlyworks with byte arrays.

Memcpy Ptr =

Memcpy(@ArrayTo(start),

@ArrayFrom(start),

num\_bytes)

Copies num\_bytes fromArrayFrom to ArrayTo andreturns a pointer to
ArratTo.

Do not use this function if

From and To overlap. UseMemmove instead.

Memmove Ptr =

Memmem(@ArrayTo(start),

@ArrayFrom(start),

num\_bytes)

Works the same as Memcpybut correctly handlesoverlapping memory

segments.

Table 12.2: CRT Array Functions

The following program illustrates using Memchr to search for a byte
within a bytearray, and Memcpy to copy one array into another array.

1

Option Explicit

2

3

\#include once "crt.bi"

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

Dim As Ubyte aArray(1 To 5) =&gt; {65, 123, 100, 52, 42}, bArray(1 To 5)

Dim bret As Ubyte Ptr

Dim As Integer index, i

'Look for 100 in byte array

Print "Looking for byte 100..."

Print

bret = Memchr(@aArray(1), 100, Ubound(aArray))

If bret &lt;&gt; NULL Then

 index = bret @

aArray(Lbound(aArray)) + Lbound(aArray)

Print "100 found at index ";index

Else

 Print "100 not found."

End If

Print

'Copy aArray to bArray

Print "Copying aArray to bArray..."

Print

bret = Memcpy(@bArray(1), @aArray(1), Ubound(aArray) \* Sizeof(Ubyte))

If bret &lt;&gt; NULL Then

 For i = 1 To 5

Print "bArray(";i;" ) = ";bArray(i)

Next

End If

Sleep

End

Listing 12.10: memfunc.bas

Analysis: Line 3 includes the crt.bi header file so that Memchr and
Memcpy will beavailable to the program. Both functions are located in
string.bi, which is included whenyou include crt.bi. Line 5 creates two
ubyte arrays, the first which is initialized with somebyte data.
Remember that the ubyte data type has a range of 0 to 255. Line 6
declares aubyte pointer which will be the return value fr the Memchr
function. Line 7 declares twoworking variables, index which will be used
to calulate the array index of the Memchrsearch, and I which will be
used to print the contents of bArray after the Memcpyoperation.

Line 12 calls the Memchr function. The first parameter is the address of
the firstelement of aArray, which has an index of 1, the value to find,
which is 100, and thelength of the array. If Memchr finds the byte in
the array, it will return a pointer to thevalue. If it cannot find the
byte, bret will be Null. Line 13 checks the return value to makesure
that bret is not Null; using a Null pointer will cause the program to
behave strangelyor crash.

Line 14 calculates the array index of the found byte. Bret contains the
address ofbyte 100 in the array. @aArray(1) returns the address of the
first element of the array.

Since arrays are sequential memory locations, you can find the array
index by

subtracting the address of the first array element from bret, and then
adding the lowerbound index to the value. This will give you the index
of the array element. Line 15 printsthe calculated index value to the
console.

Line 23 copies the values from aArray to bArray. Again, the address of
the firstelement of each array is passed to function, along with the
number of bytes to copy. Thenumber of bytes to copy is passed to the
function with the code Ubound(aArray) \*

Sizeof(Ubyte), which uses the number of elements in the array times the
size of a ubyte.

Lines 24 through 28 then print the values of bArray to screen to verify
that the array wasin fact copied. The program is closed in the usual
way.

When you run the program you should see the following output.

Looking for byte 100...

100 found at index 3

Copying aArray to bArray...

bArray( 1 ) = 65

bArray( 2 ) = 123

bArray( 3 ) = 100

bArray( 4 ) = 52

bArray( 5 ) = 255

Output 12.5: Output of memfunc.bas

As you can see from the output, both operations succeeded. Memcopy
isextremely handy when you need to make a copy of an array. The function
is much fasterthan using a For-Next, and there considerably less code to
write.

Using the -exx Compiler Switch 
-------------------------------

The -exx compiler switch will enable error and bounds checking within
yourprogram. If you go outside the bounds of an array within your
program, the compiler willgenerate an “out of bounds” error while the
program is running. This is a great help indebugging your program, and
finding problems associated with arrays. -exx will alsoinform of you of
Null pointer assignments, so it is quite useful when working with
pointersas well. If you are using FBIde select View-&gt;Settings from
the menu and the FreeBasictab in the settings dialog. Add -exx to the
end of your compiler command string.

Using -exx does add quite of bit of additional code to your program, so
once yourprogram is functioning correctly, you will want to compile the
program without the -exxswitch.

A Look Ahead 
-------------

Manipulating date and time values is a common task in programming.
FreeBasic

has a number of date and time functions that make working with date and
timeinformation quite easy, as you will see in the next chapter.

Chapter 13 Date and Time Functions 
===================================

Working with dates and time in many Basic languages can be problematic
due tothe lack of date and time functions. FreeBasic however, has a rich
set of date and time

functions, and when used in combination with the Format function, which
you will see inthe next chapter, you can easily handle any date or time
problem you may encounter.

Intrinsic Date and Time Functions 
----------------------------------

FreeBasic includes the standard date and time functions that you see in
most Basiclanguages. The following table lists these functions.

Function Syntax Comment

Date B = Date Returns the current systemdate as a string.

Setdate B = Setdate(date\_string) Sets the system date todate\_string,
returning 0 onsuccess and non-zro on

failure. Date string must bein one of the followingformats: mm-dd-yy",
"mmdd-

yyyy", "mm/dd/yy", or"mm/dd/yyyy".

Settime B = Settime(time\_string) Sets the system time totime\_string,
returning 0 onsuccess and non-zero on

failure. Time string must bein one of the followingformats: "hh:mm:ss",

"hh:mm", or "hh".

Time B = Time Returns the current systemtime as a string.

Timer B = Timer Returns the number of

seconds since the computerwas started as a double-

type value. If the computer'sCPU supports thePerformance Counter, than

Timer has a resolution in

microseconds. On

computers without thePerformance Counter, the

resolution is 1/18 of asecond.

Table 13.1: Intrinsic Date and Time Functions

The following short programs demonstrates the return values for Date and
Time aswell as using Timer in a delay loop.

1

Option Explicit

2

3

Dim myTimer As Double

4

5

Print "Current time is ";Time

6

Print "Current date is ";Date

7

Print "Number of seconds since computer started: ";Timer

8

Print "Pausing for 2 seconds..."

9

myTimer = Timer + 2

10

Do11

Sleep 10

12

Loop Until Timer &gt; myTimer

13

Print "Press any key to continue..."

14

15

Sleep

16

End

Listing 13.1: datetime.bas

Analysis: Line 3 dimensions a double-type variable for use with the
Timer function.

Line 5 prints out the current system date. Line 6 prints out the current
system time. Line7 prints out the number of seconds since the computer
was started. Line 9 initializes thevariable myTimer with the current
Timer result plus 2 seconds. The Do-Until loop in lines10 through 12
loop until the 2 seconds have expired. The Sleep in line 11 allows
theoperating system to handle any other events while the computer is
busy in the Do loop.

Whenever you have an extended loop of this nature, you need to use a
Sleep xcommand, where x is the number of milliseconds to wait. This will
keep your programfrom consuming 100% CPU time and allow other processes
to execute. The program isended in the usual way.

When you run the program you should see something similar to the
following

output.

Current time is 11:44:02

Current date is 06272006

Number of seconds since computer started: 10710.42349851727

Pausing for 2 seconds...

Press any key to continue...

Output 13.1: Output of datetime.bas

As the example program illustrates, you can use the Timer function for
delay loops.

This is common in games that want to control the FPS, or
frames-per-second, when usingreal-time animation techniques. In the code
above, the initial Timer value is saved in avariable. Timer returns the
number of seconds since the computer was started, so adding2 to this
variable will create a 2 second interval. The Until portion of the loop
checks tosee if the current result of the Timer function is greater than
the saved value, and exitswhen 2 seconds have elapsed.

Extended Date and Time Functions 
---------------------------------

In addition to the functions listed above, FreeBasic has several
extended date and

time functions that enable you to easily calculate date and time
intervals, and extractdifferent parts of a date or time number for use
in your program. In order to use thesefunctions you must include
"vbcompat.bi" in your program. Most of these functionsrequire a date
serial, a double-type value that represents a date and time number.
Thedate is stored in the integer portion of the double, while the time
is stored in thefractional part of the double.

### DateAdd Function 

The DateAdd function returns a future or past date or time based on a
certaininterval. The function requires a serial start date or time, an
interval string and thenumber of intervals.

date\_serial = DateAdd(interval\_string, number\_of\_intervals,

start\_date\_serial)

The following list explains each of the parameters in order; that is,
interval\_stringis 1 below, number\_of\_intervals is listed as 2, and so
on, along with the return value.

 1. Interval string: This is a string that indicates what interval to
add to the startdate\_serial.

a\) “yyyy”: years

 b)

“q”: quarters

 c)

“m”: months

 d)

“ww”: weeks

 e)

“d”,”w”,”y”: days

 f)

“h”: hours

 g)

“n”: minutes

 h) “s:” seconds

 2. Number of intervals: The number of intervals defined in
interval\_string to add tothe passed date\_serial.

3\. Date serial: The starting date in the calculation. 

 4. Return: Returns a date serial that is offset by intervals from the
starting date.

The following program illustrates the DateAdd function.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

'Date serial variable

6

Dim nDate As Double

7

Dim interval As Integer = 2

8

Dim intervalstr As String

9

10

Print "Number of intervals:";interval

11

Print

12

Print "Current Date: ";Format(Now, "mmddyyyy")

13

Print

14

'Year interval

15

intervalstr = "yyyy"

16

nDate = DateAdd(intervalstr, interval, Now)

17

Print intervalstr;": ";Format(nDate, "mmddyyyy")

18

'Quarter interval

19

intervalstr = "q"

20

nDate = DateAdd(intervalstr, interval, Now)

21

Print intervalstr;": ";Format(nDate, "mmddyyyy")

22

'Month interval

23

intervalstr = "m"

24

nDate = DateAdd(intervalstr, interval, Now)

25

Print intervalstr;": ";Format(nDate, "mmddyyyy")

26

'Week interval

27

intervalstr = "ww"

28

nDate = DateAdd(intervalstr, interval, Now)

29

Print intervalstr;": ";Format(nDate, "mmddyyyy")

30

'Day interval

31

intervalstr = "d"

32

nDate = DateAdd(intervalstr, interval, Now)

33

Print intervalstr;": ";Format(nDate, "mmddyyyy")

34

'w day interval

35

intervalstr = "w"

36

nDate = DateAdd(intervalstr, interval, Now)

37

Print intervalstr;": ";Format(nDate, "mmddyyyy")

38

'y day interval

39

intervalstr = "y"

40

nDate = DateAdd(intervalstr, interval, Now)

41

Print intervalstr;": ";Format(nDate, "mmddyyyy")

42

43

44

45

46

47

48

49

50

51

52

53

54

55

56

57

58

59

60

61

62

63

'Quarter interval

intervalstr = "q"

nDate = DateAdd(intervalstr, interval, Now)

Print intervalstr;": ";Format(nDate, "mmddyyyy")

Print

Print "Current time: ";Format(Now, "hh:mm:ss")

Print

'Hour interval

intervalstr = "h"

nDate = DateAdd(intervalstr, interval, Now)

Print intervalstr;": ";Format(nDate, "hh:mm:ss")

'Minute interval

intervalstr = "n"

nDate = DateAdd(intervalstr, interval, Now)

Print intervalstr;": ";Format(nDate, "hh:mm:ss")

'Second interval

intervalstr = "s"

nDate = DateAdd(intervalstr, interval, Now)

Print intervalstr;": ";Format(nDate, "hh:mm:ss")

Sleep

End

Listing 13.2: dateadd.bas

Analysis: In line 3 the “vbcompat.bi” is included in the program. You
need toinclude this file if you want to use the extended date time
functions as well as the formatfunction. Line 6 dimensions a double-type
variable to hold the return value from theDtaeAdd function. Line 7
creates an integer variable to hold the interval, which is set to

2\. Line 8 creates a string that will hold the various interval strings.
Line 10 prints thecurrent interval number. Line 12 prints the current
date using the Format function and theNow function. The Now function
returns the current date and time as a date serial. The 

format function's format string “mm-dd-yyyy” will print a two digit
month, a two digit dayand a four digit year.

Lines 15 through 17 set the interval string for the DateAdd function,
“yyyy” in thiscase, passes the interval string, interval and the current
date serial, using the Nowfunction. The calculated date is returned in
nDate, which is passed to the Format functionin line 17. Lines 18
through 45 use the same code blocks to calculate the result for
eachinterval string.

Line 47 pints the current time. DateAdd works with time numbers as well
as dates,

and lines 50 through 60 illustrate the different time offsets. The
Format function uses theformat string “hh:mm:ss” in 47 which prints a
24-hour time. The same code blocks areused for the time calculations
that were used in the date calculations, and the results are

printed in the same fashion.

When you run the program your output should look similar to the
following.

Number of intervals: 2

Current Date: 06272006

yyyy: 06272008

q: 12272006

m: 08272006

ww: 07112006

d: 06292006

w: 06292006

y: 06292006

q: 12272006

Current time: 16:28:12

h: 18:28:12

n: 16:30:12

s: 16:28:14

Output 13.2: Output of datedd.bas

Using a negative interval number will return a past date, rather than a
future date.

Changing the variable interval in the above program to -2 will result in
the followingoutput. Notice that the date and time return values are two
intervals in the past.

Number of intervals:2

Current Date: 06272006

yyyy: 06272004

q: 12272005

m: 04272006

ww: 06132006

d: 06252006

w: 06252006

y: 06252006

q: 12272005

Current time: 16:52:09

h: 14:52:09

n: 16:50:09

s: 16:52:07

Output 13.3: Output with Negative Interval Number

### DateDiff Function 

The DateDiff functions returns the difference between two date or time
serials

based on a certain interval. The function requires two date or time
serials and an intervalstring. You can optionally specify the first day
of the week or the first day of the year.

int\_value

= DateDiff(interval\_string, date\_serial1, date\_serial2)

int\_value

= DateDiff(interval\_string, date\_serial1, date\_serial2,

first\_day\_of\_week)

int\_value

= DateDiff(interval\_string, date\_serial1, date\_serial2,

first\_day\_of\_week, first\_day\_of\_year)

You can specify the first day of the week when using the “ww” interval
but thedefault is to use the system setting. You can also specify which
week belongs to whichyear when a week spans the end of one year and the
beginning of the next year.

 1. Interval string: The interval strings are the same strings used in
the DateAddfunction.

2\. Date Serial 1: The first date or time of the difference. 

3\. Date Serial 2: The second date or time of the difference. 

4\. First Day of the week: Specifies the day number of the first day of
the week. This isused when using the “ww”, or week, interval string. 

a\) Not specified: Sunday. 

b\) 0: Local settings. 

c\) 1: Sunday. 

d\) 2: Monday. 

e\) 3: Tuesday. 

f\) 4: Wednesday. 

g\) 5: Thursday. 

h\) 6: Friday. 

i\) 7: Saturday.

 5. First day of the year: Specifies what year a week will be associated
withwhen the week spans years.

a\) 0: Local settings. 

b\) 1: January 1 week. 

c\) 2: First week having four days in the year. 

 d) 3: First full week of year.

 6. Return: Returns an integer value that represents the number of
intervalsbetween the two date or time values.

The following program illustrates the DateDiff function.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double Date1, Date2

6

7

'Get current date

8

Date1 = Now

9

'Get past date

10

Date2 = DateValue("1/1/2006")

11

12

'Print out number of days since first of year '06

13

Print "Number of days since ";Format(Date2, "mm/dd/yyyy");"
is";DateDiff("d", Date2,

14

Date1)

15

16

Sleep

End

Listing 13.3: datediff.bas

Analysis: Line 3 includes the extended date and time functions contained
in the

vbcompat.bi include file. Line 5 dimensions two double-type variables to
hold the currentand past date. Line 8 gets the current date and time.
Line 10 uses the DateValue functionto convert the string date to a
DateSerial value. Line thirteen prints the number of daysthat have
elapsed since January 1, 2006.

When you run the program you should see output similar to the following.

Number of days since 01/01/2006 is 225

Output 13.4: Output of datediff.bas

### DatePart Function 

The DatePart function returns a specific part of a DateSerial, using the
specifiedinterval. The function requires a DateSerial, the interval to
return and optionally, the firstday of the week and the first day of the
year. The function returns an integer valuerepresenting the specified
interval.

int\_value = DatePart(interval\_string, date\_serial)

int\_value

= DatePart(interval\_string, date\_serial, first\_day\_of\_week)

int\_value

= DatePart(interval\_string, date\_serial, first\_day\_of\_week,

first\_day\_of\_year)

1\. Interval string: The interval strings are the same strings used in
the DateAddfunction. 

2\. Date Serial: A date or time serial number. 

3\. First Day of the week: Specifies the day number of the first day of
the week. Thevalues are the same as those listed in the DateDiff
function. 

4\. First day of the year: Specifies what year a week will be associated
with when theweek spans years. The values are the same as those listed
in the DateDiff function. 

5\. Return: Returns an integer representing the interval value. 

The following program illustrates using the DatePart function.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double myDate

6

7

'Get current date

8

myDate = Now

9

10

'Print date values

11

Print "Day number is";Datepart("d", myDate)

12

Print "Week number is";Datepart("ww", myDate)

13

Print "Month number is";Datepart("m", myDate)

14

'Print the current time numbers

15

Print "Hour is";DatePart("h", myDate)

16

Print "Minutes are";DatePart("n", myDate)

17

Print "Seconds are";DatePart("s", myDate)

18

19

Sleep

20

End

Listing 13.4: datepart.bas

Analysis: Line 3 includes the extended date and time functions. Line 5
creates a

double-type varibale to hold the current date and time serial. Line 8
uses the Nowfunction to return the current system date and time. Line 11
prints the day number. Line12 prints the week number. Line 13 prints the
month number. Line 15 prints the hournumber. Line 16 prints the minute
number. Line 17 prints the second number. Theprogram is closed in the
usual way.

When you run the program you should see something similar to the
following.

Day number is 15

Week number is 33

Month number is 8

Hour is 9

Minutes are 52

Seconds are 58

Output 13.5: Output of datepart.bas

The values you see will depend on the current date and time setting of
your

computer.

### DateSerial Function 

The DateSerial function will return a double-type DateSerial value based
on thepassed year, month and day. The date value returned by DateSerial
has no time

component.

date\_serial = DateSerial(year, month, day)

1\. Year: The year component of the date. 

2\. Month: The month component of the date. 

3\. Day: The day component of the the date. 

4\. Return: Returns a DateSerial that is the value of the year, month and
day 

components.

The following program illustrates using the DateSerial function.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double myDate

6

7

'Build a date serial using the Datepart function

8

myDate = DateSerial(Datepart("yyyy", Now), Datepart("m", Now), \_

9

Datepart("d", Now))

10

Print "Current date is ";format(myDate, "mm/dd/yyyy")

11

12

Sleep

13

End

Listing 13.5: dateserial.bas

Analysis: Line 3 includes the extended date and time functions in the
program.

Line 5 dimensions a double-type variable which will contain the date
serial value. Lines 8and 9 create a date serial using the Datepart
function to extract the year, month and daycomponents from the current
system date. Line 10 uses the Format function to print thedate to the
console screen.

When you run the program you should see the current system date.

Current date is 08/15/2006

Output 13.6: Output of dateserial.bas

Of course it is a bit silly to use the DatePart function when you could
simply usethe Now function to return the current system date, but this
program shows how bothfunction could be used together in a program. In a
real program, the year, month and dayvalues would be probably be coming
from an external source which would need to becombined to create a date
serial that would then be used for a date calculation.

### DateValue Function 

The DateValue function takes a string as it argument and returns a date
serialvalue. The date string must be in the same format as the regional
settings of the

computer.

date\_serial = DateValue(date\_string)

1\. Date String: A date string in the current regional setting format.
DateValue will onlyconvert a date string, not a time string. 

2\. Return: A DateSerial representing the date string. 

The following program illustrates using the DateValue function.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double myDate

6

Dim As String myDateStr

7

8

'Create a date string value

9

myDateStr = "08/15/2006"

10

'Get the serial date value

11

myDate = DateValue(myDateStr)

12

'Print the value

13

Print "Date string is ";Format(myDate, "mm/dd/yyyy")

14

15

Sleep

16

End

Listing 13.6: datevalue.bas

Analysis: Line 3 includes the extended date and time functions. Line 5
creates a

double DateSerial variable that will contain the converted value. Line 6
defines a stringthat will hold the date string value. Line 9 initializes
the string variable to a date format,

using the US regional settings. This may have to be changed on your
computer if you areusing a different setting. Line 11 creates a
DateSerial from the string value. Line 13 printsthe value using the
Format function.

When you run the program you should see the following output.

Date string is 08/15/2006

Output 13.7: Output of datevalue.bas

If you run this program and get a strange date, then the regional
settings on yourcomputer are different than what is shown in this
program. For example, if your settinghas the year first, then you will
need to change the string format to have the year first inthe string,
rather than last. The DateValue function, used in conjunction with the
IsDatefunction which is covered later in this chapter, is an easy way to
get a date from the userwhich then can be used for date calculations.

Day Function

The Day function will return the day number from a DateSerial. The Day
functiontakes a single date serial value and returns an integer
representing the day number.

int\_value = Day(date\_serial)

1\. DateSerial: The date serial value. 

2\. Return: Integer value representing the day of the month. 

The Day function returns the same value as DatePart with the day
intervalspecified.

Hour Function

The Hour function returns the current hour number from a TimeSerial
value. The

Hour function takes a single TimeSerial value, or a DateSerial value
with a timecomponent and returns an integer that represents the hour.

int\_value = Hour(time\_serial)

1\. TimeSerial: The time serial value. 

2\. Return: Integer value representing the hour of the day. If the PM
specifier is addedto the time value, the hour number returned will be in
24 hour format. That is, 1:00 

PM will return 13.

The following program illustrates using the Hour function.

1 Option Explicit

2

3 \#Include Once "vbcompat.bi"

4

5 Dim As Double myTime

6 Dim As String myTimeStr

7

8 'Create a date string value

9 myTimeStr = "1:10:23 pm"

10 'Get the serial date value

11 myTime = TimeValue(myTimeStr)

12 'Print the value

13 Print "Hour is";Hour(myTime)

14

15 Sleep

16 End

Listing 13.7: hour.bas

Analysis: Line 3 includes the extended date and time functions. Line 5
creates a

double-type TimeSerial variable. Line 6 creates a string variable to
hold the string timevalue. Line 9 initializes the string variable to a
time string. Line 11 converts ythe timestring to a TimeSerial using the
TimeValue function. Line 13 prints the hour number of theTimeSerial.

When you run the program you should see the following output.

Hour is 13

Output 13.8: Output of hour.bas

Minute Function

The Minute function returns the minute number from a TimeSerial value.
The

Minute function takes a single TimeSerial value, or a DateSerial with a
time component,

and returns an integer representing the minute.

int\_value = Minute(time\_serial)

1\. TimeSerial: The time serial value. 

2\. Return: Integer value representing the minute of the hour. 

Month Function

The Month function returns the month number from a DateSerial value. The
Month

function takes a single DateSerial value and returns an integer
representing the month.

int\_value = Month(date\_serial)

1\. DateSerial: The date serial value. 

2\. Return: Integer value representing the month of the year. 

MonthName Function

The MonthName function returns a string representing the name of the
month. TheMonthName function takes an integer representing the month,
and an optional flag thatwill return a month abbreviation if set.

string\_value = MonthName(month\_number)

string\_value = MonthName(month\_number, abbreviate)

1\. Month Number: An integer representing the month. 

2\. Abbreviate: A flag that indicates whether to return an abbreviated
month name. Ifflag is 0, the full month will be returned. If the flag is
1, the abbreviated monthname will be returned. 

3\. Return: A string value representing the name of the month. The return
value isbased on the current locale settings of the system. 

The following program illustrates using the MonthName function.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Integer i

6

7

For i = 1 To 12

8

Print "Month ";Monthname(i);" is abbreviated as ";Monthname(i, 1)

9

Next

10

11

Sleep

12End

Listing 13.8: monthname.bas

Analysis: Line 3 includes the extended date and time function. Line 5
dimensions

an integer variable for the following For-Next routine. The For-Next
block in lines 7through 9 call the MonthName function to get the full
name, and then is called a secondtime with the abbreviate flag set to 1
to get month abbreviation.

When you run the program you should see output similar to the following,

depending on your local settings.

Month January is abbreviated as Jan

Month February is abbreviated as Feb

Month March is abbreviated as Mar

Month April is abbreviated as Apr

Month May is abbreviated as May

Month June is abbreviated as Jun

Month July is abbreviated as Jul

Month August is abbreviated as Aug

Month September is abbreviated as Sep

Month October is abbreviated as Oct

Month November is abbreviated as Nov

Month December is abbreviated as Dec

Output 13.9: Output of monthname.bas

Now Function

The Now function returns a double-type value representing the current
systemdate and time. The Now function takes no parameters.

double\_value = Now

1\. Return: A double value representing the current system date and time.

Second Function

The Second function returns an integer value representing the second
number of aTimeSerial value, or a DateSerial with a time component. The
Second function takes asingle TimeSerial value.

int\_value = Second(time\_serial)

3\. TimeSerial: The time serial value. 

4\. Return: Integer value representing the second of the minute. 

TimeSerial Function

The TimeSerial function will return a double-type TimeSerial value based
on thepassed hour, minute and secondy. The time value returned by
TimeSerial has no date

component.

time\_serial = TimeSerial(hour, minute, second)

1\. Hour: The hour component of the time. The hour is passed in
twenty-four format. 

2\. Minute: The minute component of the time. 

3\. Second: The second component of the the time. 

4\. Return: Returns a TimeSerial that is the value of the hour, minute
and second 

components.

The TimeSerial function works just like the DateSerial function, except
that itreturns a time value rather than a date value. You can get both a
date and time byadding a DateSerial value created with the DateSerial
function to a TimeSerial valuecreated with the TimeSerial function.
Since the date is contained within the integerportion of the DateSerial
and the time is contained within the fractional portion of
theDateSerial, you can combine the two values by simply adding them. The
followingprogram illustrates this concept.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double ts, ds, cs

6

7

'Get a date serial

8

ds = Dateserial(2006, 1, 10)

9

'Get a time serial

10

ts = Timeserial(13, 10, 42)

11

'Combine the two

12

cs = ds + ts

13

'Print values

14

Print "Date and time is ";Format(cs, "mm/dd/yyyy hh:mm:ss AM/PM")

15

16

Sleep

17

End

Listing 13.9: timedateserial.bas

Analysis: Line 3 includes the extended date and time functions. Line 5
creates

three double-type values, ts which will be the time serial value, ds
which will be the dateserial value and cs, which will be the combined
date and time serial value. Line 8 gets thedate serial value using the
DateSerial function. Line 10 gets the time serial value fromthe
TimeSerial function. Line 12 adds the two values together to get a
combined date andtime serial value. Line 14 uses the Format function to
print both the date and time. TheAM/PM specifier is added to the time
format string to convert the 24-hour value to a 12hour

value.

When you run the program you should see the following output.

Date and time is 01/10/2006 01:10:42 PM

Output 13.10: Output of timedateserial.bas

TimeValue Function

The time value function will return a TimeSerial value from a string
representingthe time value. The time string can contain either a 24-hour
format such as “13:10:42” ora 12-hour format such as “01:10:42PM”.

time\_serial = TimeValue(time\_string)

1\. Time String: A time string in either 24 or 12-hour formats. 

2\. Return: A TimeSerial representing the time string. 

Year Function

The Year function returns an integer value representing the year number
of aDateSerial value. The Year function takes a single DateSerial value.

int\_value = Year(date\_serial)

1\. DateSerial: The date serial value. 

2\. Return: Integer value representing the year of the date serial value.

Weekday Function

The Weekday function returns the number of the day of the week. The
Weekdayfunction takes a DateSerial value and an optional flag that
represents the first day of theweek.

int\_value = Weekday(date\_serial)

int\_value = Weekday(date\_serial, first\_day\_of\_week)

1\. DateSerial: The date serial value. 

2\. First Day of Week: A flag that represents the day number that is
regarded as thefirst day of the week. The values are the same as those
in the DateDiff function. 

3\. Return: Integer value representing the day of the week. 

WeekDayName Function

The WeekDayName function returns a string that is the name of the day.
TheWeekDayName function takes an integer representing the day of the
week, an optionalflag that indicates whether to return an abbreviated
name and an option flag thatindicates the first day of the week.

int\_value = WeekDayName(day\_number)

int\_value = WeekDayName(day\_number, abbreviate)

int\_value = WeekDayName(day\_number, abbreviate, first\_day\_of\_week)

1\. Day Number: The day number. The day number is interpreted by the
first-day-ofthe-

week setting.

2\. Abbreviate: If this flag is 1, the function will return an
abbreviated name, if 0 thenthe full name is returned. 

3\. First Day of Week: A flag that represents the day number that is
regarded as thefirst day of the week. The values are the same as those
in the DateDiff function. 

4\. Return: A string value that represents the name of the day of the
week. The dayname is based on the computer's locale setting. 

The function works juts like the MonthName function with the added
first-day-ofthe-

week setting.

A Look Ahead 
-------------

Once you have created the data in your program, whether it be numeric,
date ortime data, you will at some point need to format that data. The
Format function has allthe capability you need to format these data
types, and is the subject of the nextchapter.

Chapter 14 The Format Function 
===============================

The Format function is a general purpose formatting function that can
handle awide range of numeric values. Once you understand the
capabilities of the function, youwill find yourself using this function
for all your formatting routines. The Format functioncan handle simple
numeric data, date and time values.

string\_value = Format(numeric\_value, format\_string)

The numeric value parameter can any of the numeric values available in
FreeBasic.

The format string contains format characters that specify how to format
the numericvalue. If the Format string is an empty string, then Format
behaves just like the Strfunction.

String Format Characters

You can display text within the format string using the general
formatting string.

The following table lists the string format characters.

Character Comment

: ? + \$ () space Will return as a literal string.

\\ Will return the next character in the stringas a literal character.

“text” Will return text within double quotes as aliteral string.

: Used as a separator for time components.

/ Used as a separator for date components.

Table 14.1: String Format Characters

The values listed in the table will return as literal text, and can be
used to generatea string that contains both literal characters and
formatted numeric text.

Numeric Format Characters

There are a number of format characters that can be used to format
simplenumeric types. The following table lists the format characters.

Character Comment

0 (zero) The zero is a digit placeholder. How thenumber is formatted
depends on how manyzeros are in the format string and howmany numbers on
either side of the

Character Comment

decimal point of the number. If there arefewer digits than 0's, a
leading or trailingzero are added to the format string. If thereare more
digits to the right of the decimalthan there are 0's, then the number is

rounded. The number to the left of the

decimal are not changed.

\# This format character works in the same

way as the 0 character, except the leadingor trailing zeros are not
displayed.

. (decimal point) Will return a decimal point within theformated string.
If the format string onlyhas \#'s to the left of the decimal point,
thennumbers smaller than 1 will be displayedwith only a leading decimal
point.

% Will multiply number by 100 and returnpercentage sign.

, (comma) The comma is used as the thousands

separator. Two adjacent commas, or acomma right after the decimal point,
willnot display the thousands digits and willround the number.

E- E+ e- e+ These characters are used to format a

string in scientific format. Placing a 0 or \#

to either the left or right of the characterdetermines the number of
digits to displayon either side of the exponent sign. Thenegative
characters are used to displaynegative exponents and the
positivecharacters are used to display positive

exponents.

Table 14.2: Numeric Format Characters

As you can see from the character table, there is a wide range of
formattingoptions available for formatting numeric data. The following
program demonstrates howto use some of the formatting options.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double myValue = 123456.789

6

7

Print "Value: ";Format(myValue)

8

'Print various format string

9

Print "Value as currency: ";Format(myValue,
"\$\#\#\#,\#\#\#,\#\#\#.\#\#")

10

myValue = .10

11

Print "Value: ";Format(myValue)

12

Print "Value as scientific: ";Format(myValue, "\#\#\#E+\#\#\#")

13

Print "Value with zeros: ";Format(myValue, "00.0000")

14

Print "Value as percentage: ";Format(myValue, "\#\#%")

15

16

Sleep

17

End

Listing 14.1: format-numeric.bas

Analysis: Line 3 includes the extended date and time function library
which alsoincludes the Format function. Line 5 creates a double value
that will be used as the

numeric value in the formatting expressions. Line 7 prints the
unformatted value. Line 9prints the value as a currency value using the
\$ with commas used to separate thethousand places and two \# characters
after the decimal point to round the value. Line 10sets the double
variable to .1 for different formatting. Line 11 prints the
unformattedvalue. Line 12 prints the value in scientific format. Line 13
prints the value with leadingand trailing zeros. Line 14 prints the
value as a percentage.

When you run the program you should see the following output.

Value: 123456.789

Value as currency: \$123,456.79

Value: .1

Value as scientific: 100E3

Value with zeros: 00.1000

Value as percentage: 10%

Output 14.1: Output of format-numeric.bas

Date Format Characters

In the previous chapter you saw some of the date format characters used
in theexample programs. The following table lists all the date format
Characters and theirmeaning.

Character Comment

d Returns the day of the month withoutleading zeros.

dd Returns the day of the month with leading

zeros.

ddd Returns the day of the week name as anabbreviation.

Character Comment

dddd Returns the day of the week name as a full

name.

ddddd Returns the serial date formatted accordingthe locale setting.
Includes the year, monthand day.

m Returns the month number without leading

zeros.

mm Returns the month number with leadingzeros for single month numbers.

mmm Returns the month name as an

abbreviation.

mmmm Returns the month name as a full name.

y Returns the year number formatted as twodigits.

yyyy Returns the year number formatted as fourdigits.

Table 14.3: Date Format Characters

The following program demonstrates some of the formatting options for
dates.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double myDate = Now

6

7

'Print some formatted dates

8

Print "Date Serial: ";Format(myDate, "ddddd")

9

Print "Date with single chars: ";Format(myDate, "d/m/yy")

10

Print "Date with double chars: ";Format(myDate, "dd/mm/yyyy")

11

Print "Date with year first: ";Format(myDate, "yyyy/mm/dd")

12

Print "Date with ():

";Format(myDate, "ddmmyyyy")

13

Print "Date with ( ): ";Format(myDate, "dd mm yyyy")

14

15

Sleep

16

End

Listing 14.2: format-date.bas

Analysis: Line 3 includes the date-time and format library definition.
Line 5 createsa date serial values and initializes it to the current
date and time using the Now function.

Line 8 prints the serial date using the local settings. Line 9 prints
the date as single

month and day values with a two-digit year. Line 10 prints the date with
two-digit monthand day values and a four-digit year. Line 11 prints the
date with the year first. Line 12using a dash to separate the date
components and line 13 uses a space to separate thedate components.

When you run the program you should see the following.

Date Serial: 8/16/2006

Date with single chars: 16/8/06

Date with double chars: 16/08/2006

Date with year first: 2006/08/16

Date with ():

16082006

Date with ( ): 16 08 2006

Output 14.2: Output of format-date.bas

Time Format Characters

The time format characters are similar to the date format characters and
are used

in much the same way. The following table lists the format characters
that you can usewith a TimeSerial value.

Character Comment

h Returns the hour without a leading zero.

hh Returns the hour with a leading zero forsingle digit hour numbers.

m Returns the minute without a leading zero.

mm Returns the minute with a leading zero forsingle digit minute
numbers.

s Returns the second without a leading zero.

ss Returns the second with a leading zero forsingle digit second
numbers.

ttttt Returns a TimeSerial value formatted as the

local specific time format.

AM/PM

am/pm

Converts the time to a 12-hour format and

adds an am or pm to the return value.

A/P

a/p

Converts the time to a 12-hour format ans

adds an a or p the return value.

Table 14.4: Time Format Characters

The following program demonstrates some ways to format a time value.

1

Option Explicit

2

3

\#Include Once "vbcompat.bi"

4

5

Dim As Double myTime = Timeserial(8, 1, 1)

6

7

'Print some formatted times

8

Print "Time Serial: ";Format(myTime, "ttttt")

9

Print "Time with single chars: ";Format(myTime, "h:m:s")

10

Print "Time with double chars: ";Format(myTime, "hh:mm:ss")

11

Print "Time with am/pm: ";Format(myTime, "hh:mm:ss am/pm")

12

Print "Time with a/p: ";Format(myTime, "hh:mm:ss a/p")

13

14

Sleep

15

End

Listing 14.3: format-time.bas

Analysis: Line 3 includes the extended date and time library. Line 5
creates a timeserial value using the TimeSerial function. Line 8 prints
the time using the TimeSerialformat. Line 9 prints the time using
single-digit characters. Line 10 prints the time usingtwo-digit
characters. Line 11 prints the time as in 12-hour format using the
AM/PMformat, and line 12 also prints the time in a 12-hour format with
the a/p format.

When you run the program you should see the following output.

Time Serial: 8:01:01 AM

Time with single chars: 8:1:1

Time with double chars: 08:01:01

Time with am/pm: 08:01:01 am

Time with a/p: 08:01:01 a

Output 14.3: Output of format-time.bas

The Format function has a tremendous amount of functionality, and when
workingwith numeric data, it is an invaluable resource in formatting.
You should some time tobecome acquainted with this function as it will
save you lot of time when you need toformat your data.

A Look Ahead 
-------------

At this point you should have a good understanding of the data types
available inFreeBasic. Creating data is only half the story though. You
need to display that data andyou need to gather data from your user. The
next chapter shows how to make yourscreen output look interesting and
explains the various ways to gather user input.

199

Chapter 15 Console Programming 
===============================

Console programming, or more generally text-based programming, is
aprogramming style that uses text as the primary medium to display
information to, andto interact with, the user. This is in contrast to
GUI programming, where a graphical userinterface is used for display and
interaction or a graphics-based program where graphicalobjects are used
for display and interaction. Text-based programming has its roots in
theearly days of computing, when computers did not have graphical
displays or the graphicswere too primitive to be of use. Even today, in
this era of photo-realistic graphics, text-based programming remain a
vibrant area of application development.

At first glance it may seem that text-based applications would be
limited, howeverthis is not the case at all. Over the years everything
from sophisticated word processorsand spreadsheets to games have been
developed using only text. Text user interfaces, orTUIs have been
developed that have all the functionality of modern graphical
userinterfaces. Many of the most popular games in history, such as Zork,
were writtenentirely in text. Text-based application are content
oriented, and if conveying content iswhat you are trying to do, then a
text-based application is well suited to the task.

If you are interested in text-based programming you should visit Ascii
World located athttp://www.ascii-world.com. Ascii World is a site
devoted entirely to text-basedprogramming, regardless of the programming
language.

The Console Screen

The console can be viewed as a grid, where each row contains a certain
numbercolumns. In FreeBasic you can specify how many rows and columns a
console cancontain, providing the operating system supports the
configuration. The basic consoleconfiguration is 25 rows by 80 columns.
Consoles are row oriented, so you specify aposition on the grid using
the row followed by the column Each grid location can containa single
character.

The character set for the console under Windows®, is the Ascii character
set. The

Ascii character set contains 256 characters and includes all the
numbers, letters and

punctuation you would expect, as well as some extended characters used
in Europeanlanguages, and a set graphical characters that can used for
drawing lines and boxes onthe screen. By using both text and the Ascii
graphical characters in a console applicationyou can create quite
sophisticated user interfaces completely in text.

The Console Functions

FreeBasic has a number of console functions that enable you to position
text onthe screen, set the foreground and background colors of the text,
and to retrieveinformation from the console screen. You can also use the
mouse in the console for added

functionality. The following table lists the console commands available
in FreeBasic.

Function Syntax Comment

Cls Cls mode Clears the screen. If mode is

Function Syntax Comment

0 or omitted, entire screen

is cleared. If mode is 1 the

graphics viewport is cleared.

If mode is 2, the text

viewport is cleared.

Color Color foreground,

background

B = Color

Sets the foreground and/orbackground color of printed

text.

Color can also be used to

return the current color

attributes, where the

foreground color is the low-

word and the backgroundcolor is the high-word.

Csrlin B = Csrlin Returns the row that the

cursor currently occupies.

Format B = Format (numeric,

format\_string)

Formats a numerical

expression according toformat\_string.

Getmouse Getmouse col, row, wheel,

button

Returns the current positionof the mouse cursor in row,

col, the current wheel state

and button state.

Locate Locate row, column,

cursor\_state

Positions the cursor on the

row and column. If

cursor\_state is 0, cursor is

hidden. If 1, cursor is shown.

Pos B = Pos Returns the current column

of the cursor.

Print

?

Print expression

Print expression,

Print expression;

? expression

? expression,

? expression;

Prints expression to thescreen. Expression can betext, a string variable
ornumeric variable. A comma

at the end of the print stringwill print a tab space withno carriage
return. A semicolon

will not print acarriage return. If no commaor semi-colon, a
carriagereturn is printed.

Print Using Print Using format\_string,

expression1

Print Using format\_string,

expression1,

Print Using format\_string,

expression1;

Print expression to thescreen using a format string.

Print Using has some knownbugs and should not beused. Use format
instead.

Function Syntax Comment

Screen B = Screen(row, col,

color\_flag)

Screen returns the ascii

character code at row and

column position if color\_flagis 0. If color\_flag is 1, Screenreturns
the color attribute.

You can determine the

background color with

background = attribute

shr 4 and the foregroundcolor with foreground =

attribute and &hf.

Spc Spc columns Causes next print statementto skip number of columns.

Tab Tab column Sets column for next print

statement.

View Print View Print first\_row To

last\_row

Sets printing area of screen.

Width Width columns, rows Sets the the number of

columns and rows of the

console window.

Table 15.1: Console Commands

Console Colors

The default color scheme for the console is white text on a black
background. Youcan change the color scheme by using the Color function
to change either or both theforeground and background color of printed
text. For the console, the color numbersrange from 0, black, to 15,
bright white. The following list enumerates the color numbersthat can be
used in the console.

.

0: black

.

1: blue

.

2: green

.

3: cyan

.

4: red

.

5: magenta

.

6: yellow

.

7: white

.

8: gray

.

9: bright blue

.

10: bright green

.

11: bright cyan

.

12: bright red

.

13: bright magenta

.

14: bright yellow

.

15: bright white

The colors listed above may vary, depending on your graphics card and
monitor,

but they should approximate those listed. In addition to printing
colored text, you canalso set the background of the entire console
screen by setting the background colorusing the Color function, and then
using Cls to clear the screen. When the screen iscleared, the background
will be in the selected color.

Color is useful for enhancing the look of your application, but you
should never rely oncolor alone to indicate critical information in your
application. Approximately 15 millionpeople are color blind just in the
United States. Depending on the level of colorblindness, an individual
may miss critical information if it is displayed using color alone.

It is good practice to identify critical information through the use of
text manipulation,

such as a pop-up box, so that the information won't be missed by a color
blind user.

Each character position on the console screen stores the character
value, alongwith the current color attributes which can be determined
using the Screen function. Ifcolor\_flag is 0, Screen will return the
ascii code of the character at the selected row andcolumn. If
color\_flag is 1, Screen will return the color attribute. Colors are
stored as bytevalues with the high 4 bits indicate the background color
and the low 4 bits indicate theforeground color, the color of the text.
You can determine the color attributes by usingthe following formulas.

Foreground = attribute And 15

Background = attribute Shr 4

The following program illustrates how you might use these functions in a
program.

1

Option Explicit

2

3

Dim As Integer clr, ccode

4

5

'Set the color

6

Color 15, 0

7

8

'Get the current color

9

clr = Color

10

11

'Print foreground and background color numbers

12

Print "Current color setting:"

13

Print "Foreground: ";Loword(clr)

14

Print "Background: ";Hiword(clr)

15

Print

16

'Get the current character position at 1, 1

17

ccode = Screen(1, 1)

18

Print "Character code at 1,1 is";ccode;" which is ";Chr(ccode);"."

19

20

'Get the color attributes at 1,1

21

clr = Screen(1, 1, 1)

22

Print "Foreground color at 1,1:";clr And 15

23

Print "Background color at 1,1:";clr Shr 4

24

25

26

Sleep

27

End

Listing 15.1: color.bas

Analysis: Line 3 dimensions the working variables, clr which contains
the colorattribute of a text position and ccode which is the character
code. Line 6 sets the currentcolor to bright white, 15, with a black
background, 0. Line 9 stores the current clr settingin the variable clr.
Lines 13 and 14 print the current color numbers to the screen usingthe
Loword and Hiword macros. Line 17 stores the character code at row
position 1,

column position 1 in ccode. Line 18 prints both the character code and
the correspondingcharacter to the screen. Line 21 retrieves the color
attribute for the same position, andlines 22 and 23 print the color
values using the formula listed above. The program isclosed in the usual
way.

When you run the program you should see the following output.

Current color setting:

Foreground: 15

Background: 0

Character code at 1,1 is 67 which is C.

Foreground color at 1,1: 15

Background color at 1,1: 0

Output 15.1: Output of color.bas

The display will be in bright white, with a black background. As you can
see, youhave tremendous control over the appearance of console text and
can easily determinethe attributes of the text.

Positioning Text

You can position text anywhere on the console screen using the Locate
statement.

The Locate statement sets the text cursor position for subsequent
printing of text. To

print to a certain location on the screen, you must first position the
text cursor using thelocate statement, then follow that command with a
print statement. You can turn the textcursor on and off by using the
optional cursor flag of the locate statement. 1 turns thetext cursor on,
and 0 turns the cursor off. This is useful if, for example, you are
using themouse for console input.

The Print command will update the current cursor position. You can
obtain the

current row setting by using the Csrlin function and the current column
setting by usingthe Pos function.

Printing Text

The Print statement is used to print text to the screen. The location
and color ofthe text is determined by the current cursor setting and the
last color statement. Usingthe Print statement with a semi-colon after
the print string will position the text cursor tothe end of the string.
Using a comma after the print string will position the text cursor tothe
next tab location. A Print statement without either a semi-colon or
comma, will insert

a carriage return and/or line feed positioning the cursor at the
beginning of the next line.

You can format the output of numeric text using the Print Using command,

although this is a deprecated function and has some known, minor bugs.
The function isavailable mainly for backward compatibility with older
programs. For new programs, youshould use the Format function, which is
covered in a separate chapter later in this book.

For details on the Print Using function see the FreeBasic documentation
wiki4. The

function will not be covered in this book.

You have already seen the Spc and Tab functions in several of the
exampleprograms. The Spc function will cause the next print position to
skip a number of columnswhile the Tab function will put the text cursor
at the next tab position. Both of thesefunctions are useful for printing
tabular data to the screen.

Determining and Setting the Size of the Console

You can determine the current console size, or set the number of rows
and columns

of the console by using the Width function. To determine the current
console size, use theWidth function without any parameters as shown in
the following code snippet.

MyInt = Width

columns = Loword(myInt)

rows = Hiword(myInt)

The number of columns of the console is stored in the low word of the
return

integer value while the number of rows is stored in the high word of the
integer. To setthe console size, use the Width function with the number
of desired columns and rows, as

illustrated in the following code snippet.

Width 80, 25

This will set the console to 80 columns by 25 rows. The standard
consoleconfiguration is 80 columns by 25 rows, however, if you need a
different size for your

4At the time of this writing, the Print Using wiki page is loacted
athttp://www.freebasic.net/wiki/wikka.php?wakka=KeyPgPrintusing.

application you can use the Width function to check if the console is
the appropriate sizeand then resize if necessary. Setting the console
size will reset the cursor position to row1 and column 1, so you may
need to issue a Locate statement to reset the cursor positionafter the
change.

The following program shows how to use the Width function to get the
consile sizeinformation and reset the console.

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

Option Explicit

Dim As Integer consize, rows, cols

'Get the current console size

consize = Width

rows = Hiword(consize)

cols = Loword(consize)

Print "Current Rows =";rows

Print "Current Columns =";cols

Print "Press any key..."

Sleep

Cls

'Resize console if necessary

If rows &gt; 25 Then

Width 80, 25

End If

'Get the new console size

consize = Width

rows = Hiword(consize)

cols = Loword(consize)

Print "New Rows =";rows

Print "New Columns =";cols

Sleep

End

Listing 15.2: width.bas

Analysis: Line 3 dimensions three variables, consize that will contain
the Width

return value, rows which will contain the number of rows and cols which
will contain the

number of columns. Line 6 gets the current console size. Line 7
retrieves the number ofrows using the Hiword macro and line 8 retrieves
the number of columns using theLoword macro. The current setting is
printed to the screen in lines 9 and 10. The Sleepcommand is used in
line 12 to pause the program and wait for a key press from the user.

Line 13 clears the screen.

Lines 16 through 18 check to see if the number of rows is greater than
15 and iftrue, then resets the console to 80 columns by 25 rows. Line 21
checks the new consolesize and the current rows and columns are
retrieved in lines 22 and 23. The new values

are printed in lines 24 and 25. The program is then closed in the usual
way.

When you run the program you should see output similar to the following.

Current Rows = 25

Current Columns = 80

Press any key...

Output 15.2: Output a of width.bas

New Rows = 25

New Columns = 80

Output 15.3: Output b of width.bas

Output a shows the console setting when the program starts, and Output b
showsthe console setting after checking the console size. In this run
the default setting was thedesired size, so the Width statement did not
need to be executed.

Getting User Input

If you need to interact with the user, then you will need to get user
input. Thereare several ways to collect user input which are listed in
the following table.

Function Syntax Comment

Inkey B = Inkey Returns a key from thekeyboard buffer as a string.

If an extended key ispressed, the return stringcontains character 255 +

key character. Inkey doesnot wait for keyboard input.

Input Input variable\_list

Input “prompt”; variable\_list

Input “prompt”,variable\_list

Input will gather input forone or more variables listed

in variable\_list. The

variables should be

separated with commas.

The type of variabledetermines how input willcollect the data. If the
data

type of the variable is astring, Input will convert theinput data to a
string. If thedata type of the variable is

numeric, Input will convertthe data to a number. If an

invalid numeric string isentered, Input will attempt

to convert as manycharacters as possible to anumber. If no characters
can

be converted to a string,

Input will return 0. If a semicolon

is used with Input, aquestion mark will bedisplayed after the prompt.

If a comma is used, a

question mark will not beprinted.

Input() B =

Input(number\_of\_characters)

Input() will return a stringcontaining number ofcharacters entered.

Getkey B = GetKey Returns the ascii code of the

current key in the keyboardbuffer. Getkey will wait for akey. If an
extended key ispressed, the first characteris skipped, character 255,

and the second character is

returned.

Line Input Line Input string\_variable

B = Line Input “prompt”;

string\_variable

B = Line Input “prompt”,

string\_variable

Line Input will return a lineof text from the keyboard.

All characters up to, but notincluding the enter key areread. An
optional promptcan be displayed with eithera question mark, using
asemi-colon, or no questionmark when using a comma.

Winput() B =

Winput(number\_of\_characters)

Wide string version ifInput().

Table 15.2: Input Functions

Inkey

Inkey is useful for polling the keyboard buffer in a loop and can be
used in gamesor in text-based user interfaces since Inkey does not with
for a key to be pressed. Thisallows you to process other events within
your program, and then take action if a key hasbeen pressed. If the
buffer is empty, Inkey will return an empty string. If a key is
waitingin the buffer, Inkey will return a string that is either one or
two character long. Keys canbe either the normal printable keys, such as
A or 1, or an extended key such as the UpArrow or F1. Normal keys return
1 key code, while the extended keys return 2 key codes,

with the first code being character 255.

The following program will display the character and ascii code(s) of
both normaland extended keys.

Option Explicit

Dim As String key, char

Dim As Integer i

Do

'Check keyboard buffer

key = Inkey

'If key has been pressed

If Len(key) &gt; 0 Then

 'Clear the last message

Locate 1, 1

Print Space(79);

'Reposition cursor

locate 1,1

'Print current key codes

For i = 1 To Len(key)

 char = Mid(key, i, 1)

Print "Character: ";char; " Code: ";Asc(char); " ";

 Next

End If

Sleep 10

Loop Until key = Chr(27)

End

Listing 15.3: inkey.bas

Analysis: Line 3 dimensions two string variables, key which will be the
return valuefrom Inkey and char which will be the individual characters.
The integer variable i in line4 will be used in the For-Next to extract
the individual characters fro the key variable.

Line 6 through 23 define a keyboard processing loop using. Line 8 checks
for keyboardinput. Line 10 checks to see if the length of key is greater
than zero, indicating that Inkeyreturned a key. Lines 12 through 15
clear the previous output line that may have beenprinted. Lines 17
through 20 extract each character from the key variable, loading
theactual character into the variable char in line 18 and then printing
the corresponding asciicode to the screen in line 19.

The Sleep command is used in line 22 to allow the operating system to
processother events. If you are using an extended loop such as this
keyboard input loop, youshould always insert a Sleep \# command in the
loop to allow the operating system toprocess background tasks, otherwise
your program may consume 100 percent of theoperating system's time.

Line 23 then checks to see if the escape key was pressed, which is ascii
code 27,

and then exits the loop if the key was pressed. The program is then
closed using the end

statement.

A sample output is shown below.

Character: Code: 255 Character: ; Code: 59

Output 15.4: Output of inkey.bas

The output shows the codes when the F1 key is pressed. Once you know the
keycodes, then you can build Const statements to trap for certain keys.
For example, to trapfor the F1 key, you would create the Const statement
shown in the code snippet below.

Const F1\_key = Chr(255) & Chr(59)

You can then check the Inkey return to see if the key returned natches
the F1 key.

If key = key\_F1 Then

'Then do something

End If

You can set up any number of keys in this manner. The F1 key is usually
used todisplay help content, and in your application you could display a
help screen by executingthe help display code in the body of the If
statement. If you are coding a game, you mightwant to use the arrow keys
to move your character player around the screen, by settingup the arrow
key constants and then adding a If-Then-Elseif ladder to process the
arrowskeys.

Getkey

Unlike Inkey, Getkey does wait for the user to press a key. If an
extended key ispressed, Getkey will discard the first character and
return the second character. Getkey isused in situations where you are
not interested in the extended key set and you need topause the program
to gather user input.

Input

The Input function is used to gather information from the user that will
be loadedinto one or more variables. The data type of the variable
determines how the user inputis processed. If the variable is a string,
Input will process the information as a string; ifthe variable is a
numeric data type, Input will try to convert the information to a
number.

The variables must be separated using commas.

You can display a prompt string with Input by enclosing a literal string
before thevariable list. If a semi-colon is used after prompt string, a
question will be displayed afterthe prompt. If a comma is used after the
prompt string, no question mark is printed.

If you are supplying multiple variables to Input, then the user will
need to enter thevalues separated by either spaces or commas. The spaces
and commas are not returned

by Input. If you need to process either spaces or commas, then you need
to use LineInput rather than Input.

Line Input

Line Input will return a single string up to but not including the enter
key. That is,

Line Input expects a single string variable, rather than multiple
variables. Line Input willread both spaces and commas in the entered
string. Like Input, you can use a semi-colonto display a question mark
at the end of the prompt string. Unlike Input however, you canuse either
a literal string or a string variable for the prompt. Line Input returns
the userinput as a string and does not convert numeric strings to
numbers.

Using the Mouse 
----------------

Another way to get user input is to use the mouse. The Getmouse function
willreturn the current zero-based row and column of the mouse as well as
the state of the

buttons and mouse wheel. Since the rows and columns are zero-based, you
will need toadd 1 to the values to map the return values to the screen

The current state of the mouse wheel as an integer that starts at zero
when theprogram starts and will return either a more positive number if
the mouse wheel is turnedin a forward direction and a more negative
number if the mouse wheel is turned in thereverse direction. Normally,
you would store the mouse wheel value at program start,

and then take an action based on the offset value returned by Getmouse.
For example, toscroll some text, you may scroll up if the wheel number
is moving in the positive directionand scroll down if the wheel number
is moving in the negative direction.

You can also determine which buttons have been pressed by checking the
buttonreturn value. Getmouse supports three buttons, left and right and
a middle button, whichoften doubles as the mouse wheel. You can
determine which button has been pressed byusing the following formulas.

.

Left button = button And 1

.

Right button = button And 2

.

Middle button = button And 4

Button is the value returned by the Getmouse function. Not only can you
check forsingle button presses, but you can also check to see if both
button have been pressed bychecking each button state simultaneously.
There is no way to check for a double clicknatively however, so you will
need to create your own timing code to determine if abutton has been
double-clicked.

The following program illustrates using the Getmouse functions.

Option Explicit

'Mouse return values

4

Dim As Integer mx, my, oldmx, oldmy, mwheel, mbuttons

5

6

'Turn off text cursor

Locate ,,0

Do

 'Get mouse info

 Getmouse mx, my, mwheel, mbuttons

 'Zero based so add 1

 mx += 1

 my += 1

 'Check to see if we have new information

 If (mx &gt; 0) And (my &gt; 0) then

 Locate 1, 1

 'Print current row, column and wheel setting

 Print "Row:";my;" Col:";mx;" W:";mwheel;" BT:";

 'Check for button press

 If mbuttons And 1 Then Print "L";

 If mbuttons And 2 Then Print "R";

 If mbuttons And 4 Then Print "M";

 Print " "

 'Clear old cursor

 Locate oldmy, oldmx

 Print chr(32);

 'Print new cursor

 Locate my, mx

 Print Chr(15);

 'Save the old values

 oldmx = mx

 oldmy = my

 End If

 Sleep 10

Loop Until Inkey\$&lt;&gt;""

'Turn on cursor

Locate ,, 1

End

Listing 15.4: con-mouse.bas

Analysis: Line 4 creates the mouse parameter working variables. Mx and
my arethe current column and row returned by the Getmouse function.
Oldmx and oldmy arethe old column and row settings that are used to
erase the mouse cursor character that isdisplayed on the screen. Mwheel
is the current mouse wheel setting while mbuttons isthe current button
state. Line 7 uses the Locate statement to turn off the text cursor.
Line

8 through 35 are the mouse input loop that polls the mouse. Line 10 uses
the Getmousefunction to return the current mouse state information.
Since Getmouse returns the row

and column as a zero-based value, lines 12 and 13 add 1 to the value to
map the returnvalue to the actual screen coordinates. Line 15 checks to
see if the mouse is still within

the console screen. If the mouse is outside the console screen, Getmouse
will return -1

for the row and column values. Since the program added 1 to these
values, if the mouse

is outside the console window, the mx and my values will be 0; that is,
-1 + 1 = 0. Youshould always check to make sure the mouse is still
inside the console window beforeinteracting with the mouse.

Lines 16 and 18 prints the current row, column and wheel settings to the
consolescreen. Lines 20 through 22 check to see what mouse button, if
any, has been pressedand prints the mouse button id to the screen. L is
the left mouse button, R is the rightmouse button and M is the middle
button. Lines 25 and 26 erase the old mouse location

indicator, an asterisk that will follow the mouse cursor on the screen.
Lines 28 and 29

then print the asterisk at the new mouse location. Lines 31 and 32 save
the current mxand my values in oldmx and oldmy, to use in the next loop
iteration.

The Do-Loop is exited in line 35 when any key is pressed. Line 27 turned
the textcursor back on and the program is closed with the End statement
in line 39.

When you run the program you should see something similar to the
following.

Row: 2 Col: 4 W: 2 BT:L

¤

Output 15.5: Output of con-mouse.bas

If the mouse does not work in the console window, then you will need to
turn offthe Quick Edit mode of the console. Right click the title bar
and select Properties. UnderEdit Options, uncheck the QuickEdit mode. If
a pop-up window appears, select SaveProperties for Future Windows with
Same Title, then click the OK button. The mouseshould not work in the
console window.

Creating a Text View Port

You can create a text view port using the View Print statement. A text
view portcan be thought of as a window -within-a-window, where all text
operations occur. Youdefine a view by passing the beginning row and
ending row to the View Print command.

Once the command has been issued, all subsequent text operations occur
within the view

port.

The following program creates a 10 line view port and prints some text
within theview, which can be scrolled using the mouse wheel. If the
mouse does not work withinthe console window, you will need to turn off
the QuickEdit mode as described above.

1

Option Explicit

2

3

'Create paragraph

4

Dim Shared As String \* 80 myText(1 To 19) =&gt; { \_

5

" Lorem ipsum dolor sit amet consectetuer id a ut magna Vestibulum.", \_

6

"Id elit justo pretium commodo vitae convallis urna magnis mattis ", \_

7

"tempor. Duis vitae id semper euismod dolor wisi turpis leo dolor in. ",
\_

8

"Neque non Vivamus ac eget nunc sagittis ut mauris at orci. Tincidunt ",
\_

9

"ipsum habitasse accumsan leo iaculis et vitae congue vitae malesuada.
", \_

"Wisi sem Curabitur id ut ipsum adipiscing facilisi elit In id. Et
urna.", \_

11

" Lorem ipsum dolor sit amet consectetuer eleifend Suspendisse sem ", \_

12

"lacus iaculis. Wisi feugiat mus augue parturient et felis Pellentesque
", \_

13

"wisi et nec. Vitae metus senectus a dolor Nullam amet accumsan integue
", \_

14

"nonummy id. Sed justo in fames turpis justo platea ultrices est ", \_

15

"convallis vel. Interdum ut Morbi enim ut Vestibulum senectus lacinia",
\_

16

"Sed congue metus.", \_

17

" Lorem ipsum dolor sit amet consectetuer lacinia molestie wisi", \_

18

"semper pretium. Et gravida congue volutpat ac Maecenas elit Nunc ", \_

19

"orci Curabitur lobortis. Felis tincidunt nonummy vitae at ut et ", \_

"et montes pellentesque Donec. Vitae elit habitant nunc cursus ", \_

21

"ullamcorper risus sagittis tempus consectetuer velit. Est ", \_

22

"Vestibulum non id pulvinar Nam vitae metus id congue massa. ", \_

23

"Phasellus."}

24

25

Dim As Integer idx = 1, mx, my, oldwheel, mwheel, delta

26

Dim As Integer vtop = 10, vbot = 20

27

28

Sub PrintText(tidx As Integer)

29

Dim As Integer i, tbot31

'Clear view port to black32

Color , 033

Cls34

'Calc text that will fit into view port35

tbot = tidx + 1036

If tbot &gt; 19 Then tbot = 1937

For i = tidx To tbot38

Print Rtrim(myText(i))

39

Next

End Sub

41

42

'Set the console size

43

Width 80, 25

44

'Turn off text cursor

45

Locate ,,0

46

'Clear screen to blue

47

Color , 1

48

Cls

49

'Create view port

View Print vtop To vbot

51

'Print the current text

52

PrintText idx

53

'Get the current wheel setting

54

Getmouse mx, my, oldwheel

55

56

57

58

59

60

61

62

63

64

65

66

67

68

69

70

71

72

73

74

75

76

Do

'Get mouse wheel info

Getmouse mx, my, mwheel

If mwheel &lt;&gt; oldwheel Then

 'Get delta amount

delta = oldwheel mwheel

'Use delta amount to adjust text index

idx = idx + delta

'Make sure text isn't out of bouns

If idx &gt; 19 Then idx = 19

If idx &lt; 1 Then idx = 1

'Print text

PrintText idx

'Save the current mouse wheel value

oldwheel = mwheel

 End If

 Sleep 10

Loop Until Inkey&lt;&gt;""

'Turn on text cursor

Locate ,,1

End

Listing 15.5: view-print.bas

Analysis: Line 4 creates a single-dimension array that initialized to
some randomtext. The text will be printed in the view port created later
in the program. Line 25 and 26creates the working variables. Idx is the
current line index into the myText array. Mx andmy are the mouse column
and rows, which are not used in the program, but are neededfor the
Getmouse function. Oldwheel and mwheel are the last and current wheel
positionvariables. Delta is the difference between the old wheel
position and the current wheelposition. Delta is used to calculate the
offset for the idx variable. Line 26 dimensions twovariables, vtop and
vbot which are the top and bottom of the view port.

Line 28 through 40 define the PrintText subroutine which will print the
array text tothe view port. The tidx parameter, is the current value
contained within the idx variable,

and points to the current line position in the text array. Line 29
creates two variables, iwhich is used in the following For-Next block
and tbot which is used to calculate howmany rows of text to print. Line
32 and 33 clear the view port. Line 35 calculates thenumber of lines to
display. Tidx contains the start line in the text array, and tbot
containsthe end line in the text array. Line 36 checks to make sure that
the end line containedwithin tbot does not point past the end of the
array. Line 37 through 39 print the text tothe view port. Since the view
port is 10 lines, the code prints a 10 line “window” from thearray to
the view port.

Line 43 sets the width of the console, and lines 45 through 48 clear the
mainconsole window to a blue color. At the point the view port has not
be created so thesecommands apply to the console widow as a whole. Line
505 creates a view port that

starts at vtop and extends to vbot, inclusive. All text commands issued
after the ViewPrint command will go now to the view port. Line 52 prints
the initial 10 lines of text. Line54 gets the initial value of the mouse
wheel, for use later to calculate the delta value.

Line 55 through 71 define the mouse input loop. Line 57 gets the current
mousewheel value. Line 58 checks to see if the new value is different
than the old value, and if

they are different, this means the mouse wheel has been moved. Line 60
calculates the

delta, or changed value, between the old mouse wheel setting and the new
mouse wheelsettings. Using this technique, you can calculate how to
scroll the text, because the valuewill be either positive or negative
depending on whether the mouse wheel is movedforward or backward.

Line 62 uses the delta value, to update the idx variable, which is the
pointer to thecurrent top line in the text array. If delta is positive,
idx will move toward the end of thearray, which means that the text will
scroll up. If delta is negative, idx will move towardthe beginning of
the array, so the text will scroll down. Line 64 and 65 make sure that
idxdoes not point past the beginning and end of the array. The current
text block is thenprinted in line 67. Line 69 then saves the current
wheel value in the oldwheel variable, tobe used in the next delta
calculation.

If a key pressed the loop is exited in line 72 and then program is
closed with anEnd statement.

When you run the program you should see output similar to that shown
below.

Sed congue metus.

 Lorem ipsum dolor sit amet consectetuer lacinia molestie wisi

semper pretium. Et gravida congue volutpat ac Maecenas elit Nunc

orci Curabitur lobortis. Felis tincidunt nonummy vitae at ut et

et montes pellentesque Donec. Vitae elit habitant nunc cursus

ullamcorper risus sagittis tempus consectetuer velit. Est

Vestibulum non id pulvinar Nam vitae metus id congue massa.

Phasellus.

Output 15.6: Output of view-print.bas

When you run the program you will see a blue screen with a black view
port in themiddle with some text. Scroll the mouse wheel, and the text
will scroll. Move the mouse

wheel forward and the text will scroll down, move the mouse backward and
the text will

scroll up. The text will stop scrolling when the beginning or the end of
the text is reached.

As you can see, using the view port command along with the Getmouse
function is asimple way to add a great deal of functionality to your
text-based programs.

A Look Ahead 
-------------

Now that you can create variables and gather input, you need to see how
to buildcontrol structures to act on this data. In the next chapter you
will see the various controlstructures that are available in FreeBasic.

Chapter 16 Control Structures 
==============================

Controls structures allow you to change the flow of your program, to
executedifferent parts of your program based on certain criteria and to
iterate through codeblocks. Control structures fall into two categories;
decision-making structures such as theIf and Select Case statements, and
looping structures such as the For-Next and Do-Loop

statements.

The decision-making, or branching structures, allow you define criteria
based ondata values, and then execute code based on those data values.
If a variable is less than

5, you can execute one code block, and if the variable is greater than
5, you can executea different code block, and if the variable is equal
to 5, you can execute yet another codeblock. Being able to make
decisions within your program is crucial for implementing thelogic that
your program describes.

The looping structures are also necessary elements to any program, since
you willoften need to process groups of information in a loop, such as
reading a disk file orgetting input from the user. Data manipulation
almost always involves looping, since youwill need to iterate through
data structures to gather specific information that you willneed in your
program. FreeBasic has a rich set of both decision-making and looping

structures.

A Program is a State Machine

You can think of a program as a state machine, where at any given
moment, theprogram is in a particular state, or condition, which changes
over time. This may sound abit cryptic, so an example may help
illustrate what this means. Suppose it is getting closeto evening and
you realize that you are getting hungry. Call this the hungry state.
Yourstomach is empty, and your brain is telling you to get some food.
You run down to thelocal hamburger joint, get a nice juicy double
cheeseburger and consume it. You are nowfull, so call this the satisfied
state. This is basically how a state machine operates. At onemoment,
your stomach is empty and the state is hungry and at the next moment,
yourstomach is full and the state is satisfied. You started in one state
(hungry), executed abranching action (drove to the burger joint) and
ended in another state (satisfied).

Programs do much the same thing.

A variable is like your stomach. If the variable is empty, the program
is in theempty state; that is, there is no meaningful data within the
variable, so the programcannot do any meaningful work with that data.
Programs are designed to do something,

so you need to transition from the empty state to the satisfied state,
by executing abranching statement (driving down to the burger joint) in
order to initialize the variablewith data. Once the variable is
initialized (you ate the hamburger) the program changesstate and now you
can do something meaningful, since you now have meaningful data.

Control structures are the transition mechanisms that enable you to
change thestate of your program. If you are writing a game, you can use
a Do-Loop to wait on userinput. Once the user presses a key, you can
then use an If or Select Case statement blockto act on this key press.
The program moves from a waiting state, to an action state, andthen back
to a waiting state, until another key is pressed or the program
terminates. Toeffectively use control structures within your program,
you must keep in mind the variousstates of your program, both before and
after state transitions.

The If Statement Block

You can think of the If statement block as a question that requires a
True or Falseanswer. The answer determines which section of code your
program will execute. Sincecomputers only work with numbers, you frame
the question as a conditional equationthat will result in either 0 for
False or non-zero for True. The following table lists theconditional
operators that you can use within an If statement.

Operator Syntax Comment

Equal If var = 5 Then If operand on both sides ofthe = are equal,
thenexecute code after Then

statement.

Inequality If var &lt;&gt; 5 Then If operands on both sides ofthe
&lt;&gt; are not equal, thenexecute code after Then.

Less Than If var &lt; 5 Then If first operand is less thansecond operand
thenexecute code after Then.

Less Than or Equal If var &lt;= 5 Then If first operand is less thanor
equal to second operand,

then execute code after

Then.

Greater Than If var &gt; 5 Then If first operand is greaterthan second
operand, thenexecute code after Then.

Greater Than or Equal If var &gt;= 5 Then If first operand is
greaterthan or equal to secondoperand then execute codefollowing Then.

Table 16.1: Logical Operators

You can mix arithmetic, logical and conditional operators, as well as
parenthesis,

within an If statement. The compiler evaluates the conditional
statements from left toright, taking into account the precedence of the
operators. For example, all of the

following code snippets are legal If statement constructs.

If var1 = 5 Then

If (var1 = 5) And (var2 &lt; 3) Then

If var1 + 6 &gt; 10 Then

All of these conditional expressions are valid constructs, and if they
evaluate toTrue, or non-zero, then the code following the Then clause
will be executed.

Using Bitwise Operators in an If Statement

Remember that the operators And, Or and Not are bitwise operators. That
is, theyreturn a value based on the bitwise operation that they perform.
You should take carewhen using bitwise operators within an If statement
to make sure that the result willevaluate correctly. Take the second
code snippet listed above. If var1 = 5, the compilerwill return True, or
-1 for the expression. If var2 is less than 3 then the compiler will
returnTrue or -1 for this expression. The compiler will then evaluate
the And operator with -1And -1 returning -1. Since -1 is non-zero, or
True, the code following the Then will beexecuted. If either of the
statements within the parenthesis evaluate to 0, then And willreturn 0,
which is False, and the code following the Then clause will be skipped.
Whenusing bitwise operators you should frame the conditional expressions
on either side ofthe bitwise operator so that they return either True or
False. This will give you consistentresults in your evaluations.

The Not Problem

The Not bitwise operator can be a problem in an If statement. You may be
used towriting If Not var Then, with Not performing a logical, rather
than a bitwise operation.

In FreeBasic Not performs a bitwise operation, not a logical operation.
If var were tocontain the value of 3, then Not 3 is -4, which will be
regarded as a True result and thecode following the Then will be
executed, which is probably not what you wanted. Insteadof writing If
Not var Then, you should write If var &lt;&gt; 0 Then.

The Single-Line If Statement

The basic form of the If statement will execute a single statement if
the conditionalexpression evaluates to True.

If &lt;expression&gt; Then &lt;statement&gt;:&lt;statement&gt;...

In this form, &lt;expression&gt; can be a single or compound expression
and&lt;statement&gt; can be more than one statement separated with : or
colons. The followingprogram demonstrates the syntax of the single-line
If.

1

Option Explicit

2

3

Dim As Integer myInt = 1

4

5

If myInt Then Print "This is the first statement." \_

6

:Print "This is the second statement."

7

8

myint = 0

9

If myInt Then Print "This is the first statement." \_

10

:Print "This is the second statement."

11

12

Sleep

13

End

Listing 16.1: if-single.bas

Analysis: Line 3 creates an integer value and initializes the variable
to 1. Line 5uses a single-line If to evaluate the variable. Since myInt
is one, which evaluates to True,

the compound statement following the Then clause if executed. In line 8,
myInt is set to

0\. The If statement in line 9 evaluates the variable, which is now 0 or
False, so the 

compound statement following the Then clause is not executed.

When you run the program you should see the following output.

This is the first statement.

This is the second statement.

Output 16.1: Output of if\_single.bas

You will notice that there is only one set of print lines in the output,
since thesecond If evaluated to False and the print statements were
never executed.

The If Code Block

A better way to group multiple statements within an If is to use the
If-End If code

block. By separating the statements inside a code block, it is much
easier to read and todebug if necessary.

If &lt;expression&gt; Then

&lt;statement&gt;

&lt;statement&gt;

...

End If

The block If statement operates in the same manner as the single-line
If. If&lt;expression&gt; evaluates to True, then the statements between
the If and End If areexecuted.

Nested If Statements

At times it may become necessary to nest If statements in order to
better describethe decision making process of the evaluation. While the
If statement can handle multiplearguments within an expression, there
are times when you may want to incrementallycheck for certain ranges of
values which you can do using a nested If block.

If &lt;expression&gt; Then

&lt;statement&gt;

...

If &lt;expression&gt; Then

&lt;statement&gt;

&lt;statement&gt;

...

End If

End If

It is important to close each block properly when opened by an If to
avoid compileror logical errors. Compiler errors are fairly easy to fix,
while logical errors can be tricky totrack down and correct. The best
way to make sure you are closing the blocks properly isto indent the
nested If statements and then indent the matching End If statements at
thesame level. In the example above, the indentation tells you at a
glance which End If goeswith which If.

The Else Statement

When an If expression evaluates to True, the statements following the
Then willexecute. If the expression evaluates to False, then the
statements following the If willexecute. However, there are times when
you will want to execute a different set ofinstructions if the If
evaluates to False, rather than just continuing on with the program.

The Else statement allows you code one or more statements to handle the
False case ofan If evaluation.

If &lt;expression&gt; Then

&lt;statement&gt;

&lt;statement&gt;

...

Else

&lt;statement&gt;

&lt;statement&gt;

...

End If

The If-Else-End If construct allows you to handle both the True and
False cases ofan If evaluation. One example of using this format is when
you try to open a file. If theOpen succeeds, then you can process the
file in the statements following the Thenclause. If the Open fails, you
can display an error message to the user in the Else block,

set a flag that indicates the file could not be opened or End the
program at this point.

How you handle the exception depends on the needs of your program, but
the Elsestatement allows you handle these types of program exceptions.

The ElseIf Statement

The ElseIf statement enables you to create an “If Ladder” construct,
where you cantest a series of conditions much like the rungs of a
ladder. FreeBasic will evaluate theexpressions in order, from top to
bottom, and then execute the first series of statementsthat evaluate to
True, skipping the rest of the ElseIf tests. Elseif can be used
inconjunction with a final Else statement to execute a default set of
statements if none ofthe expressions in the ladder evaluate to True.

If &lt;expression&gt; Then

&lt;statement&gt;

&lt;statement&gt;

...

ElseIf &lt;expression&gt; Then

&lt;statement&gt;

&lt;statement&gt;

...

Else

&lt;statement&gt;

&lt;statement&gt;

...

End If

You start the block with a standard If statement, then add any
additional ElseIfstatements as necessary, and optionally, as in the
example, you can add an Elsestatement as a default handler. The order of
an If-ElseIf block can be important. Thecompiler will evaluate the first
If statement, and if the expression is False, it will then dropdown to
the next ElseIf and evaluate that expression, and continue on down the
ladderuntil an End If or Else is encountered. If your expressions are
range values or compoundstatements then you need to make sure that the
expression ranges don't overlapotherwise you may execute the wrong set
of Then statements. The following programshows an example of using the
ElseIf statement.

1

Option Explicit

2

3

Randomize Timer

4

5

Dim As Integer myNumber, i

6

7

For i = 1 to 10

8

myNumber = Int(Rnd \* 10) + 1

9

'Build an if ladder

10

If (myNumber &gt; 0) And (myNumber &lt; 4) Then

11

Print "Number is between 1 and 3:";myNumber

12

Elseif (myNumber &gt; 3) And (myNumber &lt; 8) Then

13

Print "Number is between 4 and 7:";myNumber

14

Else

15

Print "Number is greater than 7:";myNumber

16

End If

17

Next

18

19

Sleep

20

End

Listing 16.2: elseif.bas

Analysis: Line 3 initializes the random number generator with the Timer
statement.

Line 5 creates two integer variables, myNumber which will hold a random
integer

between 1 and 10 and i, which will be used in the For-Next statement.
Line 7 opens theFor-Next block which will execute the code between the
For and Next 10 times. Line 8

uses the Rnd function to generate a random number in the rand 1 to 9.
Since Rnd returnsa double precision number, the Int function is used to
convert the value to an integer.

Line 10 through 16 define the If ladder. Line 10 checks to see if the
random number isbetween 1 and 3; that is, if the number is 1 it will be
greater than 0 and less than 4.

Using &gt; and &lt; in this manner defines a range of values to test.
Line 12 uses an ElseIf totest for the next range of values between 4 and
7 inclusive. Line 14 defines the defaultcode handler using an Else
statement. If the If and ElseIf evaluate to False, then the
Elsestatement will execute. Line 17 closes the For-Next block.

When you run the program you should see output similar to the following.

Number is between 1 and 3: 3

Number is between 4 and 7: 7

Number is between 1 and 3: 1

Number is between 4 and 7: 5

Number is between 1 and 3: 2

Number is between 4 and 7: 7

Number is between 4 and 7: 4

Number is greater than 7: 10

Number is greater than 7: 9

Number is between 4 and 7: 6

Output 16.2: Output of elseif.bas

This example program is a case where you must be careful not to overlap
therange values, otherwise you will get results you did not expect.
Using the &gt; and &lt;

operators create a range that is 1 more than the second operand of &gt;
and 1 less than thesecond operand of &lt;. If you were to incorrectly
overlap the 4 value for example, then theElseIf statement would execute
for a value of 4, which is not the intention of the program.

The IIF Function

The Iif, or “immediate If” function returns one of two numeric values
based on an

expression. You can think if the Iif function as an in-line If statement
that acts as afunction call.

Value = Iif(&lt;expression&gt;, numeric\_value\_if\_true,
numeric\_value\_if\_false)

Iif can be as a standalone function or inside other expressions where
you do notwant to split the expression to insert an If statement. The
numeric values can be literalvalues, variables or numeric function
calls. The limitation of the function is that it will onlyreturn a
numeric value, not a string value, however you can work around this
limitationby using pointers.

Unlike the Visual Basic version of this function, FreeBasic does
evaluate both of the

return statements.

The following program shows the different ways to use the Iif function.

1

Option Explicit

2

3

\#define False 0

4

\#define True Not False

5

\#define Null 0

6

7

Dim As Integer iresult, a, b, c, d

8

Dim As Zstring Ptr myZString

9

10

Function ResultTrue As Integer11

Print "&lt;In function ResultTrue.&gt;"

12

Return True

13

End Function

14

15

Function ResultFalse As Integer16

Print "&lt;In function ResultFalse.&gt;"

17

Return False

18

End Function

19

20

Function GetString As Zstring Ptr21

Dim As Zstring Ptr zp22

23

Print "&lt;In function GetString.&gt;"

24

'Need to add 1 for the terminating Null character25

zp = Callocate(Len("Here is a string.") + 1)

26

\*zp = "Here is a string."

27

Return zp

28

End Function

29

30

a = 5

31

b = 6

32

c = True

33

d = False

34

35

'Return literal values via the define

36

iresult = Iif(a &gt; b, True, False)

37

Print "IIF with values:";iresult

38

39

'Return variable values

40

iresult = Iif(a = b, c, d)

41

Print "IIF with variables:";iresult

42

43

'Return results from numeric function calls

44

iresult = Iif(a &lt; b, ResultTrue, ResultFalse)

45

Print "IIF with functions:";iresult

46

47

'Return a pointer to a string

48

myZString = Iif(a &lt; b, GetString, Null)

49

If myZString &lt;&gt; Null Then50

Print myZString\[0\]

51

Deallocate myZString

52

End If

53

54

Sleep

55

End

Listing 16.3: iif.bas

Analysis: Lines 3 thorough 5 define the constant values that will be
used in theprogram. False is defined as 0, and True is defined as Not
False which will evaluate to -1.

Null is defined as 0, which will be used as a check for the pointer
variable declared laterin the program. Lines 7 and 8 create the working
variables for the program. The iresultvariable is used as the return
value for the Iif function, while the rest of the variables are

used as expression and return variables. The pointer variable myZString,
is used as the

return value from the function GetString.

Lines 10 through 13 and 15 through 18 define two functions that will be
used forthe True and False return values of the Iif function. Each
function prints a string to thescreen to indicate that the function was
called, and returns either True or False. Lines 20

through 28 define the GetString function that will allocate a memory
segment (line 25),

initialze the memory segment to a string value (line 26), and return a
pointer to thismemory segment (line 27). The function also prints a
string to the screen in line 23 toindicate that the function was called.

Lines 30 through 33 set the variables to their default values. Line 36
shows how toreturn a literal value from the Iif function. Since the
\#define statement will replace theTrue and False with the defined
literal values, this works in the same manner as typing in-1 and 0 into
the Iif function. Line 40 shows the Iif function using variables as the
returnvalues. Line 44 illustarates using Iif with function calls for the
return values. Line 48illustrates how to return a pointer to a string.
Notice that Null is returned in the False partof the Iif function; this
is to prevent using a null pointer in the program, since you cancheck
the return value against the Null to be sure that the pointer was
properlyinitialized. Lines Lines 49 through 52 check to see if myZString
contains a valid pointerassignment and then prints the string value
using the pointer index method in line 50.

Line 51 deallocates the memory segment, although in this instance it
isn't reallynecessary, as the memory segment will automatically be
deallocated when the programends. However, it is a good reminder that if
you were using this function within aprogram, such as a loop, you would
want to deallocate the memory segment when youfinished using it. Good
memory management is a good habit that you cultivate.

When you run the program you should see the following output.

IIF with values: 0

IIF with variables: 0

&lt;In function ResultTrue.&gt;

IIF with functions:1

&lt;In function GetString.&gt;

Here is a string.

Output 16.3: Output of iif.bas

As you can see from the example program, the Iif function has a lot of
flexibility.

Being able to return a function value allows you to extend the
functionality to strings andcomposite types, which you cannot do with
the basic format of the function.

The Select Case Statement Block

The Select Case block can be viewed as an optimized if ladder, and works
in muchthe same way. The standard Select Case can use any of the
standard data types for

&lt;expression&gt; and the specialized Select Case As Const format is
optimized for integer

values.

Select Case &lt;expression&gt;

Case &lt;list&gt;

&lt;statement&gt;

&lt;statement&gt;

...

Case Else

&lt;statement&gt;

&lt;statement&gt;

...

End Select

This code snippet shows the syntax of the standard select case.
Expression isusually a variable which can be of any of the standard data
types, or individual elementsof a Type or array. The &lt;list&gt; clause
of the Case statement can be any of the followingformats.

.

Case &lt;value&gt;: Value is one of the supported data types or an
enumeration.

.

Case &lt;value&gt; To &lt;value&gt;: Specifies a range of values.

.

Case Is &lt;operator&gt; &lt;value&gt;: Operator is any of the logical
operators listed inTable 17.1.

.

Case &lt;value&gt;, &lt;value&gt;, ...: List of values separated with
commas.

.

Case &lt;variable&gt;: A variable that contains a value.

Select Case As Const &lt;integer\_expression&gt;

Case &lt;list&gt;

&lt;statement&gt;

&lt;statement&gt;

...

Case Else

&lt;statement&gt;

&lt;statement&gt;

...

End Select

The Select Case As Const is a faster version of the Select statement
designed towork with integer expressions in the range of 0 to 4097. The
&lt;list&gt; statement formats forthe Select Case As Const are limited
to values or enumerations of values. That is, the

operator expressions are not allowed within a Case As Const.

When a Case block is executed, the statements following the Case keyword
up tothe next Case keyword (o End Select) will be executed. Only one
block of statementswithin a Case will execute at any one time. If a Case
Else is present, then the statementswithin the Else block will execute
if no Case matches the &lt;expression&gt; portion of theSelect
statement. The following program illustrates using the Select Case
statementblock.

1

Option Explicit

2

3

'Ascii code of key press

4

Dim As Integer keycode

5

6

'Loop until esc key is pressed

7

Do8

keycode = Asc(Inkey)

9

Select Case As Const keycode10

Case 48 To 5711

Print "You pressed a number key."

12

Case 65 To 9013

Print "You pressed an upper case letter key."

14

Case 97 To 12215

Print "You pressed a lower case key."

16

End Select17

Sleep 1

18

Loop Until keycode = 27 '27 is the ascii code for Escape

19

20

End

Listing 16.4: selectcase.bas

Analysis: Line 4 declares an integer value that will be used to capture
the asciicodes in the Do-Loop block. Line 7 opens the Do-Loop block.
Line 8 uses the Inkey andAsc functions to return the ascii code of a key
press. Lines 9 through 16 define the SelectCase As Const block. Line 9
uses the variable keycode as the expression for the selectcase. Line 10
checks to see if the keycode variable is between 48 and 57 inclusive,
and ifTrue will execute the code in line 11. Line 12 checks to see if
the ascii code falls in the

upper case letter range and if True, will execute line 13. Line 14
checks the lower caseletter range and executes line 15 if True. Line 16
closes the Select Case block.

Sleep is used in line 17 to allow other process to run while this
program is running.

Line 18 checks to see if the keycode variable contains 27, the ascii
code for the Escapekey, and exits the loop if True. The program is then
closed in the usual way.

When you run the program you should see something similar to the
following.

You pressed an upper case letter key.

You pressed an upper case letter key.

You pressed a lower case key.

You pressed a lower case key.

You pressed a number key.

You pressed a number key.

Listing 16.5: Output of selectcase.bas

You wil notice that when the program runs, only one Case statement is
executed atany one time. If you have used C, then the Select Case is
like the Switch statement, butwith implicit break statements within each
Case block. Since only one Case block willexecute, you cannot have
fall-through situations like you have in C.

Appendix A: GNU Free Documentation License
==========================================

 GNU Free Documentation License Version 1.2, November 2002

 Copyright (C) 2000,2001,2002 Free Software Foundation, Inc.

 51 Franklin St, Fifth Floor, Boston, MA 021101301

USA

 Everyone is permitted to copy and distribute verbatim copies

 of this license document, but changing it is not allowed.

0\. PREAMBLE 

The purpose of this License is to make a manual, textbook, or other
functional and useful document "free" in the sense of freedom: to assure
everyone the effective freedom to copy and redistribute it, with or
without modifying it, either commercially or noncommercially.
Secondarily, this License preserves for the author and publisher a way
to get credit for their work, while not being considered responsible for
modifications made by others.

This License is a kind of "copyleft", which means that derivative works
of the document must themselves be free in the same sense. It
complements the GNU General Public License, which is a copyleft license
designed for free software.

We have designed this License in order to use it for manuals for free
software, because free software needs free documentation: a free program
should come with manuals providing the same freedoms that the software
does. But this License is not limited to software manuals; it can be
used for any textual work, regardless of subject matter or whether it is
published as a printed book. We recommend this License principally for
works whose purpose is instruction or reference.

1\. APPLICABILITY AND DEFINITIONS 

This License applies to any manual or other work, in any medium, that
contains a notice placed by the copyright holder saying it can be
distributed under the terms of this License. Such a notice grants a
worldwide,

royaltyfree

license, unlimited in duration, to use that

work under the conditions stated herein. The "Document", below, refers
to any such manual or work. Any member of the public is a licensee, and
is addressed as "you". You accept the license if you copy, modify or
distribute the work in a way requiring permission under copyright law.

A "Modified Version" of the Document means any work containing the
Document or a portion of it, either copied verbatim, or with
modifications and/or translated into another language.

A "Secondary Section" is a named appendix or a frontmatter section of
the Document that deals exclusively with the relationship of the
publishers or authors of the Document to the Document's overall subject
(or to related matters) and contains nothing that could fall directly
within that overall subject. (Thus, if the Document is in part a
textbook of mathematics, a Secondary Section may not explain any
mathematics.) The relationship could be a matter of historical
connection with the subject or with related matters, or of legal,
commercial, philosophical, ethical or political position regarding them.

The "Invariant Sections" are certain Secondary Sections whose titles are
designated, as being those of Invariant Sections, in the notice that
says that the Document is released under this License. If a section does
not fit the above definition of Secondary then it is not allowed to be
designated as Invariant. The Document may contain zero Invariant
Sections. If the Document does not identify any Invariant Sections then
there are none.

The "Cover Texts" are certain short passages of text that are listed, as
FrontCover Texts or BackCover Texts, in the notice that says that the
Document is released under this License. A FrontCover Text may be at
most 5 words, and a BackCover Text may be at most 25 words.

A "Transparent" copy of the Document means a machine readable copy,
represented in a format whose specification is available to the general
public, that is suitable for revising the document straightforwardly
with generic text editors or (for images composed of pixels) generic
paint programs or (for drawings) some widely available drawing editor,
and that is suitable for input to text formatters or for automatic
translation to a variety of formats suitable for input to text
formatters. A copy made in an otherwise Transparent file format whose
markup, or absence of markup, has been arranged to thwart or discourage
subsequent modification by readers is not Transparent. An image format
is not Transparent if used for any substantial amount of text. A copy
that is not "Transparent" is called "Opaque".

Examples of suitable formats for Transparent copies include plain ASCII
without markup, Texinfo input format, LaTeX input format, SGML or XML
using a publicly available DTD, and standard conforming simple HTML,
PostScript or PDF designed for human modification. Examples of
transparent image formats include PNG, XCF and JPG. Opaque formats
include proprietary formats that can be read and edited only by
proprietary word processors, SGML or XML for which the DTD and/or
processing tools are not generally available, and the machine generated
HTML, PostScript or PDF produced by some word processors for output
purposes only.

The "Title Page" means, for a printed book, the title page itself, plus
such following pages as are needed to hold, legibly, the material this
License requires to appear in the title page. For works in formats which
do not have any title page as such, "Title Page" means the text near the
most prominent appearance of the work's title, preceding the beginning
of the body of the text.

A section "Entitled XYZ" means a named subunit of the Document whose
title either is precisely XYZ or contains XYZ in parentheses following
text that translates XYZ in another language. (Here XYZ stands for a
specific section name mentioned below, such as "Acknowledgements",
"Dedications", "Endorsements", or "History".) To "Preserve the Title" of
such a section when you modify the Document means that it remains a
section "Entitled XYZ" according to this definition.

The Document may include Warranty Disclaimers next to the notice which
states that this License applies to the Document. These Warranty
Disclaimers are considered to be included by reference in this License,
but only as regards disclaiming warranties: any other implication that
these Warranty Disclaimers may have is void and has no effect on the
meaning of this License.

2\. VERBATIM COPYING 

You may copy and distribute the Document in any medium, either
commercially or noncommercially, provided that this License, the
copyright notices, and the license notice saying this License applies to
the Document are reproduced in all copies, and that you add no other
conditions whatsoever to those of this License. You may not use
technical measures to obstruct or control the reading or further copying
of the copies you make or distribute. However, you may accept
compensation in exchange for copies. If you distribute a large enough
number of copies you must also follow the conditions in section 3. You
may also lend copies, under the same conditions stated above, and

you may publicly display copies.

3\. COPYING IN QUANTITY 

If you publish printed copies (or copies in media that commonly have
printed covers) of the Document, numbering more than 100, and the
Document's license notice requires Cover Texts, you must enclose the
copies in covers that carry, clearly and legibly, all these Cover Texts:
FrontCover Texts on the front cover, and BackCover Texts on the back
cover. Both covers must also clearly and legibly identify you as the
publisher of these copies. The front cover must present the full title
with all words of the title equally prominent and visible. You may add
other material on the covers in addition. Copying with changes limited
to the covers, as long as they preserve the title of the Document and
satisfy these conditions, can be treated as verbatim copying in other
respects.

If the required texts for either cover are too voluminous to fit
legibly, you should put the first ones listed (as many as fit
reasonably) on the actual cover, and continue the rest onto adjacent
pages.

If you publish or distribute Opaque copies of the Document numbering
more than 100, you must either include a machine readable Transparent
copy along with each Opaque copy, or state in or with each Opaque copy a
computernetwork location from which the general networkusing public has
access to download using publicstandard network protocols a complete
Transparent copy of the Document, free of added material. If you use the
latter option, you must take reasonably prudent steps, when you begin
distribution of Opaque copies in quantity, to ensure that this
Transparent copy will remain thus accessible at the stated location
until at least one year after the last time you distribute an Opaque
copy (directly or through your agents or retailers) of that edition to
the public.

It is requested, but not required, that you contact the authors of the
Document well before redistributing any large number of copies, to give
them a chance to provide you with an updated version of the Document.

4\. MODIFICATIONS 

You may copy and distribute a Modified Version of the Document under the
conditions of sections 2 and 3 above, provided that you release the
Modified Version under precisely this License, with the Modified Version
filling the role of the Document, thus licensing distribution and
modification of the Modified Version to whoever possesses a copy

of it. In addition, you must do these things in the Modified Version:

A. Use in the Title Page (and on the covers, if any) a title distinct
from that of the Document, and from those of previous versions (which
should, if there were any, be listed in the History section of the
Document). You may use the same title as a previous version if the
original publisher of that version gives permission.

B. List on the Title Page, as authors, one or more persons or entities
responsible for authorship of the modifications in the Modified Version,
together with at least five of the principal authors of the Document
(all of its principal authors, if it has fewer than five), unless they
release you from this requirement.

C. State on the Title page the name of the publisher of the

Modified Version, as the publisher.

D. Preserve all the copyright notices of the Document.

E. Add an appropriate copyright notice for your modifications adjacent
to the other copyright notices.

F. Include, immediately after the copyright notices, a license notice
giving the public permission to use the Modified Version under the terms
of this License, in the form shown in the Addendum below.

G. Preserve in that license notice the full lists of Invariant Sections
and required Cover Texts given in the Document's license notice.

H. Include an unaltered copy of this License.

I. Preserve the section Entitled "History", Preserve its Title, and add
to it an item stating at least the title, year, new authors, and
publisher of the Modified Version as given on the Title Page. If there
is no section Entitled "History" in the Document, create one stating the
title, year, authors, and publisher of the Document as given on its
Title Page, then add an item describing the Modified Version as stated
in the previous sentence.

J. Preserve the network location, if any, given in the Document for
public access to a Transparent copy of the Document, and likewise the
network locations given in the Document for previous versions it was
based on. These may be placed in the "History" section. You may omit a
network location for a work that was published at least four years
before the Document itself, or if the original publisher of the version
it refers to gives permission.

K. For any section Entitled "Acknowledgements" or "Dedications",
Preserve the Title of the section, and preserve in the section all the
substance and tone of each of the contributor acknowledgements and/or
dedications given therein.

L. Preserve all the Invariant Sections of the Document, unaltered in
their text and in their titles. Section numbers or the equivalent are
not considered part of the section titles.

M. Delete any section Entitled "Endorsements". Such a section may not be
included in the Modified Version.

N. Do not retitle an existing section to be Entitled "Endorsements" or
to conflict in title with any Invariant Section.

O. Preserve any Warranty Disclaimers. If the Modified Version includes
new frontmatter sections or appendices that qualify as Secondary
Sections and contain no material copied from the Document, you may at
your option designate some or all of these sections as invariant. To do
this, add their titles to the list of Invariant Sections in the Modified
Version's license notice. These titles must be distinct from any other
section titles.

You may add a section Entitled "Endorsements", provided it contains
nothing but endorsements of your Modified Version by various partiesfor
example, statements of peer review or that the text has been approved by
an organization as the authoritative definition of a standard.

You may add a passage of up to five words as a FrontCover Text, and a
passage of up to 25 words as a BackCover Text, to the end of the list of
Cover Texts in the Modified Version. Only one passage of FrontCover Text
and one of BackCover Text may be added by (or through arrangements made
by) any one entity. If the Document already includes a cover text for
the same cover, previously added by you or by arrangement made by the
same entity you are acting on behalf of, you may not add another; but
you may replace the old one, on explicit permission from the previous
publisher that added the old one.

The author(s) and publisher(s) of the Document do not by this License
give permission to use their names for publicity for or to assert or
imply endorsement of any Modified Version.

5\. COMBINING DOCUMENTS 

You may combine the Document with other documents released under this
License, under the terms defined in section 4 above for modified
versions, provided that you include in the combination all of the
Invariant Sections of all of the original documents, unmodified, and
list them all as Invariant Sections of your combined work in its license
notice, and that you preserve all their Warranty Disclaimers.

The combined work need only contain one copy of this License, and
multiple identical Invariant Sections may be replaced with a single
copy. If there are multiple Invariant Sections with the same name but
different contents, make the title of each such section unique by adding
at the end of it, in parentheses, the name of the original author or
publisher of that section if known, or else a unique number. Make the
same adjustment to the section titles in the list of Invariant Sections
in the license notice of the combined work.

In the combination, you must combine any sections Entitled "History" in
the various original documents, forming one section Entitled "History";
likewise combine any sections Entitled "Acknowledgements", and any
sections Entitled "Dedications". You must delete all sections Entitled
"Endorsements".

6\. COLLECTIONS OF DOCUMENTS 

You may make a collection consisting of the Document and other documents
released under this License, and replace the individual copies of this
License in the various documents with a single copy that is included in
the collection, provided that you follow the rules of this License for
verbatim copying of each of the documents in all other respects.

You may extract a single document from such a collection, and distribute
it individually under this License, provided you insert a copy of this
License into the extracted document, and follow this License in all
other respects regarding verbatim copying of that document.

7\. AGGREGATION WITH INDEPENDENT WORKS 

A compilation of the Document or its derivatives with other separate and
independent documents or works, in or on a volume of a storage or
distribution medium, is called an "aggregate" if the copyright resulting
from the compilation is not used to limit the legal rights of the
compilation's users beyond what the individual works permit.

When the Document is included in an aggregate, this License does not
apply to the other works in the aggregate which are not themselves
derivative works of the Document.

If the Cover Text requirement of section 3 is applicable to these copies
of the Document, then if the Document is less than one half of the
entire aggregate, the Document's Cover Texts may be placed on covers
that bracket the Document within the aggregate, or the electronic
equivalent of covers if the Document is in electronic form. Otherwise
they must appear on printed covers that bracket the whole aggregate.

8\. TRANSLATION 

Translation is considered a kind of modification, so you may distribute
translations of the Document under the terms of section 4. Replacing
Invariant Sections with translations requires special permission from
their copyright holders, but you may include translations of some or all
Invariant Sections in addition to the original versions of these
Invariant Sections. You may include a translation of this License, and
all the license notices in the Document, and any Warranty Disclaimers,
provided that you also include the original English version of this
License and the original versions of those notices and disclaimers. In
case of a disagreement between the translation and the original version
of this License or a notice or disclaimer, the original version will
prevail.

If a section in the Document is Entitled "Acknowledgements",
"Dedications", or "History", the requirement (section 4) to Preserve its
Title (section 1) will typically require changing the actual title.

9\. TERMINATION 

You may not copy, modify, sublicense, or distribute the Document except
as expressly provided for under this License. Any other attempt to copy,
modify, sublicense or distribute the Document is void, and will
automatically terminate your rights under this License. However, parties
who have received copies, or rights, from you under this License will
not have their licenses terminated so long as such parties remain in
full compliance.

10\. FUTURE REVISIONS OF THIS LICENSE 

The Free Software Foundation may publish new, revised versions of the
GNU Free Documentation License from time to time. Such new versions will
be similar in spirit to the present version, but may differ in detail to
address new problems or concerns. See http://www.gnu.org/copyleft/.

Each version of the License is given a distinguishing version number. If
the Document specifies that a particular numbered version of this
License "or any later version" applies to it, you have the option of
following the terms and conditions either of that specified version or
of any later version that has been published (not as a draft) by the
Free Software Foundation. If the Document does not specify a version
number of this License, you may choose any version ever published (not
as a draft) by the Free Software Foundation.

ADDENDUM: How to use this License for your documents

To use this License in a document you have written, include a copy of
the License in the document and put the following copyright and license
notices just after the title page:

 Copyright (c) YEAR YOUR NAME.

Permission is granted to copy, distribute and/or modify this document
under the terms of the GNU Free Documentation License, Version 1.2 or
any later version published by the Free Software Foundation; with no
Invariant Sections, no FrontCover Texts, and no BackCover Texts. A copy
of the license is included in the section entitled "GNU Free
Documentation License".

If you have Invariant Sections, FrontCover Texts and BackCover Texts,
replace the "with...Texts." line with this:

 with the Invariant Sections being LIST THEIR TITLES, with the
FrontCover Texts being LIST, and with the BackCover Texts being LIST.

If you have Invariant Sections without Cover Texts, or some other
combination of the three, merge those two alternatives to suit the
situation.

If your document contains nontrivial examples of program code, we
recommend releasing these examples in parallel under your choice of free
software license, such as the GNU General Public License, to permit
their use in free software.

[^1]: See WhatIs.com Definitions:
    http://whatis.techtarget.com/sDefinition/0,290660,sid9\_gci211714,00.html

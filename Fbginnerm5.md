Numeric Data Types 
===================

FreeBasic has all the standard Numeric data types that you would expect
for a Basic compiler. Table 2.1 lists all the numeric data types that
FreeBasic supports. In the list below, you will notice that Integer and
Long are grouped together. This is because a Long is just an alias for
Integer. They are exactly the same data type.

  -------------- --------------------------- --------------------------
  Numeric Data   Types Size                  Limits

  Byte           8-bit, signed, 1 byte       -128 to 127

  Double         64-bit,                     -2.2E-308 to +1.7E+308
                                             
                 floating point, 8 bytes     

  Integer        (Long) 32-bit,              -2,147,483,648 to
                                             
                 signed, 4 bytes             2,147,483,647

  LongInt         64-bit,                    -9,223,372,036,854,
                                             
                 signed, 8 bytes             775,808
                                             
                                             to
                                             
                                             9,223,372,036,854,
                                             
                                             775,807

  Short          16-bit, signed, 2 bytes     -32,768 to 32,767

  Single         32-bit,                     1.1 E-38 to 3.43 E+38
                                             
                 floating point, 4 bytes     

  UByte          8-bit, unsigned, 1 byte     0 to 255

  UInteger       32-bit, unsigned, 4 bytes   0 to 4,294,967,295

  ULongInt       64-bit, unsigned, 8 bytes   0 to 18,446,744,073,709,
                                             
                                             551,615

  Ushort         16-bit, unsigned, 2 bytes   0 to 65365
  -------------- --------------------------- --------------------------

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

The floating point data types, Single and Double, are able to store
numbers with decimal digits. Keep in mind that floating-point numbers
are subject to rounding errors, which can accumulate over long
calculations. You should carry more than the number of decimal digits
than you need to ensure the greatest accuracy.

Using Different Number Formats 
-------------------------------

Besides decimal numbers, FreeBasic is able to recognize numbers in
hexadecimal, binary and octal formats. Table 3.4 lists the number base
and format to use.

  --------------------- -------------------
  Decimal               myVar =254
  --------------------- -------------------
  Hexadecimal           myVar =&HFE
  --------------------- -------------------
  Binary                myVar =&B11111110
  --------------------- -------------------
  Octal                 myVar =&O376
  --------------------- -------------------
  Exponential Numbers   myVar =243E10
  --------------------- -------------------
  --------------------- -------------------

<div class="caption">

Table 2.4: Format of Number Bases

</div>

Hexadecimal Numbers 
--------------------

Hexadecimal is a base 16 numbering scheme and have digits in the range
of 0 to F. Hexadecimal numbers are commonly used as constant values in
the Windows API and many third party libraries as it is a compact way to
represent a large value. To indicate a hexadecimal number, use the &H
prefix.

Binary Numbers 
---------------

Binary is a base 2 numbering scheme and have digits in the range of 0
and 1. Binary is the language of the computer. Although we can enter
numbers and letters into the computer, it all must be translated into
binary before the computer can understand it. To indicate a binary
number, use the &B prefix.

Octal Numbers 
--------------

Octal is a base eight numbering scheme and have digits in the range of 0
to 7. Octal numbers were very popular in early computer systems, but
aren’t used much today except in some specialized applications. To
indicate an octal number, use the &O prefix.

Exponential Numbers 
--------------------

You can use exponential numbers in your program by adding the E suffix
followed by the power. To use the number 105, you would write the number
as 10E05. You can directly set a double or single type variable using
the exponent format. You can also use negative exponents such as 10E-5,
which when printed to the screen would like 1.e004.

Exercises

1\) What data type would be the best to store the number 196? 

2\) What data type would be the best to store the number 2.134? 

3\) What data type is the best for general usage on 32-bit systems? 

4\) What is the difference between signed and unsigned data types? 

5\) What prefix would you use to designate a binary number? 

6\) What prefix would you use to designate a hexadecimal number? 

7\) What Alphabetic letters are allowed in a hexadecimal number? 

8\) What would the hexadecimal number 1AF be in decimal form?

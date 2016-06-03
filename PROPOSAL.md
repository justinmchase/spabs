# Proposal to Include Spabs
Leo Bartkus (leo.bartkus@gmail.com)

Justin Chase (justin.m.chase@gmail.com)

2nd June 2016


## Abstract
There is a debate between the relative merits of spaces and tabs in software coding languages. 
Many people prefer one over the other for various reasons. This proposal attempts to end this
argument by defining new unicode characters that would combine the perceived benefits of both
characters into one simple solution.

The solution is to introduce two new characters known as Spabs, a portmanteau of Space and Tab.
The two Spab characters are SPAB START and SPAB END. They function identically to a space visually
but give code text editors hints when deleting, navigating and automatically indenting code, rather
than requiring every code editor to store this information in external configuration files.

### 1 Introduction
A code editor supporting Spabs would, when the user executes an indention command, insert a single SPAB START
character, then any number of filling SPACE characters and then a SPAB END character.

Below is a table of different characters injected based on the users configured number of spaces:

Number of Spaces | Characters Inserted
-----------------|--------------------
1                | SPACE
2                | SPAB START, SPAB END
3                | SPAB START, SPACE, SPAB END
4                | SPAB START, SPACE, SPACE, SPAB END
N                | SPAB START, SPACE, ..., SPACE, SPAB END

Visually to a person looking at the code it would appear to have spaces, Spabs would appear as spaces.
However, when Spabs are present and a dedent command is sent, the editor would delete the trailing SPAB START - END span.

If a corresponding SPAB START or SPAB END character cannot be found the characters would be treated as simple space character.



### 2 Suitability for Inclusion


### 3 Evidence of Use in Running Text


### 4 Character Properties


Property   | Suggested Value
-----------|----------------
Code point | FF01
Name       | SPAB START
General Category | So
Canonical Combining Class | 0
Bidirectional Class | ON
Decomposition Type/Decomposition Mapping |
Numeric Type |
Numeric Value |
Bidi Mirrored | N
Unicode 1 Name |
ISO Comment |
Simple Uppercase Mapping | 
Simple Lowercase Mapping | 
Simple Titlecase Mapping | 

Property   | Suggested Value
-----------|----------------
Code point | FF02
Name       | SPAB END
General Category | So
Canonical Combining Class | 0
Bidirectional Class | ON
Decomposition Type/Decomposition Mapping |
Numeric Type |
Numeric Value |
Bidi Mirrored | N
Unicode 1 Name |
ISO Comment |
Simple Uppercase Mapping |
Simple Lowercase Mapping |
Simple Titlecase Mapping |


### 4.1 Collation Order


### 5 The UnicodeIECsymbol Font


### 6 Anticipated Objections


### 7 Drawing the Symbols


### 7.1 Severability


### 8 Sponsors


### 9 Summary and Conclusion


## References

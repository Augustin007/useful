# __useful__
_A module filled with many useful functions and modules in various subjects._

Simple resources and modules for a cleaner looking program

These are all simple functions that pop up a lot in programming, nothing particularily difficult or brilliant, 
but geared to cut down a lot of little bits of code that can become quite messy. These have no requirements.

While these codes have a long way to go to be perfect, they can be quite helpful

### validation
_version 1.1.2_

Validation includes various modules for getting input and preparing clean output, as well quick checks for types.

_note: it imports the datetime module, as well as namedtuple and deque from collections_ 

While I would recommend getting aquainted with the code by sifting through it, here is a quick introduction:

Usable functions in validation: YesOrNo, datetime (_note: datetime can be accessed through validation, but is built into python, and is not by me_), deque (_see note on datetime_), floatinput, floatlistinput, fromrepr, getYesOrNo, intinput, intlistinput, is_float, is_floatlist, is_function, is_integer, is_intlist, isbool, makelist, namedtuple (_see note on datetime_), tryfloat, tryint, trynumber, trytype, validdate, validinput, and validquery

makelist makes a list from any sort of input, this works well with any sort of iterable, but non-iterables usually wind up being a list with a single value, 

is_intlist checks if an input is a list of integers... this includes a single integer, a string containing integers spaced out, a file containing integers spaced out, a string in the format of a list, a list, tuple, or other iterable that contains only integers.

is_floatlist does something similar, it takes the same thing, but checks whether the values can be converted to floats.

is_function tests whether a variable is a function.

is_integer checks if an object can be converted to an integer without losing any value

is_float checks if an object can be converted to a float.

isbool checks if type(s) is bool.

fromrepr is supposed to be the opposite of repr, but still needs some work.

tryint converts s into an integer if is_integer(s)

trytype trys to convers an object into a specified type, else returning original value

intinput continues to ask for input until the input is an integer... useless in a gui environment, but quite useful in shell scripts.

etc.

## mathematics
_version 1.1.2_

Contains a lot of useful mathematical stuff

_note, imports the whole math module, imports validation_

Useable functions in mathematics: AngleType, Composite, DegreesToRadians, Expression, Heron, LawofCos, LawofSin, Phi, Prime, PrimeOrComposite, RadiansToDegrees, TriangleType, basenum, cbrt, create, e, eq, factor, findgcd, fromNumBaseFormat, fsum, gcd2, i, icbrt, irrational, irt, isTriangle, j, k, kappa, lcf, ln, log, makefraction, phi, pi, pow, prepare, psi, quaternion, rho, rt, sigma, summation, validation, var, Φ, κ, π, ρ, ς, σ, τ, φ, and ψ

Also useable is the entire math module, as well as the statistics Decimal (as num) and Fraction (as fraction)

Includes several constants, variables with both their english and greek names. 
Includes a quaternion class, for using quaternions. 
A basenum class, for working in different number systems. 
Triangle stuff, angles, valid triangle, law of cosines and law of sines functions. 
Prime and composites functions. 
Factoring numbers. 
Least commmon factor functions.

I am constructing an 'expression' class for algebraic expressions... still in progress. 

## formatting
_version 1.2.1_

Contains a few stuff for formatting output. (and a few other odds and ends that I'm not very sure how they got there)


Useable functions in formatting: ComposeNumber, Syllables, a_an, cap, colors, endingpuncuation, greek_letters, inwordpunctuation, multline, phrasepuncuation, punctuate, scour, subscript, translate, unformat, validation, vowels, and write

ComposeNumber makes the written version of the number ex:(ComposeNumber(10) returns 'ten')

a_an takes the next word as an argument, and returns 'a' or 'an' as the next word demands.

unformat removes any caps from text. It also takes any written numbers and makes them regular numbers in the text, as well as written greek letters.

scour removes all instances of something from a list or string

write adds commas to numbers.

cap capitalizes the first letter of the input string.

multline is an class in progress that is supposed to cocinate and deal with strings that can span various lines as if they were single line 

so, in theory:

' 3 '   '12'   ' 3 12'

'---' + '--' = '-----'

' 4 '   '13'   ' 4 13'

etc.

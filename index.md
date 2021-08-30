# Usefulpy

![Usefulpy Logo](https://github.com/Augustin007/Augustin007/blob/main/UsefulPY_with_quote.png)

Filled with simple resources and modules for a cleaner looking program, Usefulpy is a module filled with many useful functions and modules in various subjects geared to cut down and simplify some little bits of code that can become messy or repetitive.

So instead of checking, say
```python
float(x) == int(float(x))
```

You can check it as
```python
is_integer(x)
```

Which calls 
```python
def is_integer(s):
    '''Check if an object is an integer can be turned into an integer without
losing any value'''
    try: return int(float(s)) == float(s)
    except: return False
```

Simple, but works well and can be used in a variety of situations. This also allows you to quickly write the check without having to go back and make a module, interupting your flow of thought; or without marking it down for later creation, and then forget it (happens to me all the time).

While I would recommend getting aquainted with the code by sifting through it by hand, here is a quick introduction:

## Sections

### validation

Validation includes various tools for getting input and preparing clean output, as well quick checks for types. The main idea is to check whether something fits in a category.

A couple of its most important sections:

#### Integer/Float Tools:
 - `is_integer`/`is_float`: return `True` if s is an integer/float or can be converted into one.
 - `intinput`/`floatinput`: continue to ask for input until input is an integer/float... Useless in a gui environment but useful in shell scripts
 - `tryint`/`tryfloat`: converts to an `int`/`float` if `is_integer`/`is_float`
 - `trynumber`: tries to convert something into some sort of number (this includes complex.
 - `is_intlist`/`is_floatlist`: checks if a list or a string with spaces is composed only of integers/floats.
 - `intlistinput`/`floatlistinput`: continues to ask for input until input can be converted to a list of integers/floats

#### Custumizable Tools:
 - `validquery`: return `True` if an object can be converted to a type.
 - `validinput`: continue asking for input until the input can be converted to a certain type. This can be used for multiple inputs at once. It has a lot of possible arguments.
 - `trytype`: converts something to a type if `validquery` for the object and the type returns `True`

#### Some of the Other Tools:
 - `YesOrNo`: return `True` or `False` for most variations of yes and no: returns `None` otherwise.
 - `getYesOrNo`: take inputs until `YesOrNo` returns either `True` or `False`
 - `isbool`: return `type(s)==bool`
 - `is_function`: returns `True` if the object is a function.

and more...

### mathematics

Contains a lot of useful mathematical stuff.

The `mathematics` section is divided into several programs, though `from usefulpy.mathematics import *` imports all of the functions from all of them.
- `constants`: a ton of mathematical constants... That's really all it is.
- `mathfunc`: builds a mathfunc class which wraps a function and allows it to be added, subtracted, multiplied, divided, nested and exponentiated (is that a word) and can then apply algorithms to algebraicly simplify and find derivatives of resulting functions. Trig functions now have a radians or degrees setting.
- `nmath`: short for 'new math', this simply does work both to flexibly combine `math` and `cmath`, allow for custom types, and to implement things like prime sieves, and a triangle class that solves missing values of an input triangle.
- `basenum`: a class that saves numbers in any base counting system.
- `quaternion`: a quaternion class

These are the smaller programs that are not imported with the `mathematics` `__init__`.
- `vector`: Little bits of linear algebra **In progress**

#### nmath

`nmath` (new math) recreates and combines the `cmath` and `math` modules.

##### Most Important parts
 - `phase`, `polar`, `rect`, `ceil`, `comb`, `copysign`, `dist`, `erf`, `erfc`, `expm1`, `fabs`, `factorial`, `floor`, `fmod`, `frexp`, `fsum`, `gamma`, `hypot`, `ldexp`, `lgamma`, `modf`, `nextafter`, `perm`, `prod`, `remainder`, `trunc`, `ulp`, `sqrt`, `isqrt`, `exp`, `isclose`, `isfinite`, `isinf`, `isnan`, `ln`, `log`, `acos`, `acosh`, `asin`, `asinh`, `atan`, `atanh`, `asec`, `asech`, `acsc`, `acsch`, `acot`, `acoth`, `cos`, `cosh`, `sin`, `sinh`, `tan`, `tanh`, `sec`, `sech`, `csc`, `csch`, `cot`, `coth`, `cis`: functions that call `math` and `cmath` versions (I realize some of these math/cmath versions don't exist) but most are modified to work both for real and complex numbers, instead of only one at a time. These have also mostly turned into mathfunc and modified to also try to call a object's methods if it cannot be find (so `cos(x)` tries to call `x.__cos__` if `x` is not valid for `math` and `cmath` versions. (NOTE: Many of these were shifted into mathfunc in version 0.2.0)
 - `convert`: converts a value from a variable `frm` to `to`.
 - `radians`/`degrees`/`grad`: functions that set the default nmath trigonometric setting to radians or degrees (default is radians)
 - `rt`, `irt`, `cbrt`, `icbrt`, `square`, `cube`, `tesser`: quick root and power functions not in `math` and `cmath`
 - `mathfunc`/`trig_func`/`inverse_trig_func`: wrapper for function, so you can add, subtract, and derive functions! (`cos+sin` returns a function that does `cos(x)+sin(x)`)
 - A triangle class that allows you input three keyword arguments from a, b, c, alpha, beta, gamma, (including 1 side) and if 1 (not 2) real, valid triangle can be formed from these values it generates the rest. Also functions such as LawOfCos and Heron which do basic trig and grometric stuff. 
(Note: only works in radians)
 - `Prime`/`Composite`: return `True` if prime/composite
 - `Factor`: return a list containing the factors of any given number
 - `lcm`/`gcd`: least common multiple

#### basenum
A basenum class:
```python
>>> x = basenum('3a2', 16)
>>> x
3a2₁₆
>>> y = x/2
>>> y
1d1₁₆
>>> float(x)
930.0
>>> int(y)
465
>>> basenum('101', 2)
101₂
>>> _.convert(4)
11₄
>>> _+basenum('10.1', 2)
13.2₄
>>> float(_)
7.5
>>> 
```

#### quaternion
A quaternion class:
```python
>>> quaternion(1, 2, 3, 4)
(1+2i+3j+4k)
>>> quaternion(1+3j)
(1+3j)
>>> 
```
This class has a full range of functions and methods implimented... have fun!

### formatting

#### Data
- `vowels`: a string with all the vowels
- `endingpuncuation`/`phrasepuncuation`/`inwordpunctuation`: strings containing punctuation marks
- `greek_letters`: a dictionary containing written out greek letters and their character counterparts
- `subscript`: a dictionary with subscript number characters.
- `colors`(`colors.fg`/`colors.bg`): Data for character formatting.


#### Important Functions
- `cap`: Yes, I am aware there is a similar method for str, which capitalizes the first character and lowercases the rest, this one only capitalizes the first
- `punctuate`: adds a punctuation and strips of old punctuation
- `a_an`: returns `'a'` or `'an'` depending on the nextword argument
- `translate`/`scour`: translate `.replace`s a string with all keys in a list, scour removes all instances of something in a list/str
- `write`/`ComposeNumber`/`syllables`/`unformat`: write adds commas to string numbers, syllables counts syllables in a word/phrase, compose number writes out an input integer (`ComposeNumber(100)` returns `'one hundred'`, unformat .lowers the text, replaces any written out greek letters (for example: pi with π) or written out numbers (`unformat('two hundred forty three thousand six hundred twelve')` returns `'243612'`.

#### Multline class
Formatting includes a `multline` class, still a bit confusing and in its early stages but, cocinates and deals with strings that can span various lines as if they were single line/matrix. 

```
' 3 '   '12'   ' 3 12'
'---' + '--' = '-----'
' 4 '   '13'   ' 4 13'
```

Now supports some pretty neat slicing.

(of course, in the IDLE this would look different)

## Decorators

Decorators just has a few decorators. Nothing much to see here.

## IDE

A usefulpy IDE, in progress

```python
>>> import usefulpy
>>> usefulpy.ide()
In [0] : 1+1i-2j+4k

Out[0] : (1+1i-2j+4k)

In [1] : cos(tau/4)

Out[1] : 6.123233995736766e-17

In [2] : _0

Out[2] : (1+1i-2j+4k)

In [3] : _1

Out[3] : 6.123233995736766e-17

In [4] : 1+i+j+k

Out[4] : (1+1i+1j+1k)

In [5] : cos(_)

Out[5] : (1.5747529115583139-1.3300177322185731i-1.3300177322185731j-1.3300177322185731k)

In [6] : sin(__)

Out[6] : (2.452532348883716+0.8539945649192698i+0.8539945649192698j+0.8539945649192698k)

In [7] : __**2+_**2

Out[7] : (0.9999999999999964)

In [8] : ___

Out[8] : (1.5747529115583139-1.3300177322185731i-1.3300177322185731j-1.3300177322185731k)

In [9] : _==_5

Out[9] : True

In [10] : Out[8]

Out[10] : (1.5747529115583139-1.3300177322185731i-1.3300177322185731j-1.3300177322185731k)

In [11] : In[0]

Out[11] : '1+1i-2j+4k'

In [12] : 1.0

Out[12] : 1

In [13] : __defaults__['#'] = float

In [14] : 1

Out[14] : 1.0

In [15] : acos(1)

Out[15] : 0

In [16] : arccos(1)

Traceback (most recent call last):
  File "/Users/mac/Documents/usefulpy/IDE/usefulpy_IDE.py", line 95, in ide
    exec(corrected_input, namespace)
  File "<string>", line 1, in <module>
NameError: name 'arccos' is not defined

In [16] : a = 2

In [17] : a

Out[17] : 2 

In [18]: quit()

{'a':2}
>>> #returns dictionary of scope.
```

## gui

Includes a wrapper around tkinter, which can be frustrating to work with, to make it simpler and a set of programs called py3d, for a 3d space in the built-in tkinter canvas.
![Rotating Cube](https://github.com/Augustin007/Augustin007/blob/main/Cube_rot.gif)

#### py3d

A pure-python 3d system... I'd like to shift some of this into C or C++

## Versions
Versions include 0.0.0, 0.0.1, 0.1.0, 0.1.1, 0.1.2, 0.1.3, 0.1.4, 0.1.5, 0.2.0
###### [Usefulpy 0.0.0](https://github.com/Augustin007/usefulpy/releases/tag/v0.2.0):

![mini_usefulpy_logo](https://github.com/Augustin007/Augustin007/blob/main/Mini_usefulpy.png)
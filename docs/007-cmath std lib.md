The `<cmath>` header in C++ is part of the C++ Standard Library and provides a set of functions to perform common mathematical operations and computations. These functions are the C++ versions of the functions provided in the C language header `<math.h>`, but they are placed in the `std` namespace in C++.

Here's an overview of some of the most commonly used classes and functions inside `<cmath>`:

### Trigonometric Functions:

* `sin()`: Return the sine of an angle (in radians).
* `cos()`: Return the cosine of an angle (in radians).
* `tan()`: Return the tangent of an angle (in radians).
* `asin()`: Return the arc sine (inverse sine) of a number.
* `acos()`: Return the arc cosine (inverse cosine) of a number.
* `atan()`: Return the arc tangent (inverse tangent) of a number.
* `atan2()`: Return the arc tangent of y/x in the interval [-π, π] radians.

### Hyperbolic Functions:

* `sinh()`: Return the hyperbolic sine.
* `cosh()`: Return the hyperbolic cosine.
* `tanh()`: Return the hyperbolic tangent.
* `asinh()`: Return the inverse hyperbolic sine.
* `acosh()`: Return the inverse hyperbolic cosine.
* `atanh()`: Return the inverse hyperbolic tangent.

### Exponential and Logarithmic Functions:

* `exp()`: Compute the exponential function.
* `frexp()`: Decompose a floating-point number.
* `ldexp()`: Generate a floating-point number.
* `log()`: Compute the natural logarithm.
* `log10()`: Compute the base-10 logarithm.
* `modf()`: Decompose a floating-point number into integer and fractional parts.
* `exp2()`: Compute the binary exponential function.
* `log2()`: Compute binary logarithm.
* `log1p()`: Compute natural logarithm of one plus a value.

### Power Functions:

* `pow()`: Raise to power.
* `sqrt()`: Compute the square root.
* `cbrt()`: Compute the cubic root.

### Rounding and Remainder Functions:

* `ceil()`: Round up to the nearest integer.
* `floor()`: Round down to the nearest integer.
* `<msreadoutspan class="msreadout-line-highlight msreadout-inactive-highlight">fmod()</msreadoutspan>`: Compute the remainder of division.
* `trunc()`: Truncate to an integer value.
* `round()`: Round to the nearest integer.

### Other Functions:

* `fabs()`: Compute the absolute value.
* `fma()`: Perform a floating-point multiply-add.
* `hypot()`: Compute the hypotenuse of a right-angle triangle.
* `fmax()`,`fmin()`: Return the maximum or minimum of two numbers.

And there are several other specialized functions as well. It's always a good idea to check the documentation or reference for `<cmath>` when looking for a particular mathematical operation or function.

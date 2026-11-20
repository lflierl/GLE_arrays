GLE arrays v6.4 tests
=====================

Run each script separately from this directory with the v6.4 Windows CLI
build.

Core tests:
- array_create_strings.gle
  * reads string elements with labels[index]
  * replaces existing string elements
  * grows an array by assigning a string at a new index
  * retains mixed string/numeric element types
- array_math_power.gle
  * array ^ scalar (fractional, negative, and positive exponents)
  * scalar ^ array
  * array ^ array (element-wise)
  * ordinary scalar exponentiation remains unchanged
- array_power_non_numeric_error.gle
  * expected error: array exponentiation rejects string elements

String-array syntax:
    labels = C("one", "two", "three")
    print(labels[1])
    labels[2] = "second label"

Power syntax:
    roots = a^0.5
    inverse = a^(-1)
    squares = a^2
    pairwise = a^exponents

Power operations are element-wise. Array-array exponentiation requires equal
array lengths. Numeric array operations continue to reject non-numeric
elements. The source arrays are not modified by arithmetic expressions.

Array indices remain one-based. Assigning beyond the current end grows the
array; skipped positions retain the existing numeric-zero fill behaviour.

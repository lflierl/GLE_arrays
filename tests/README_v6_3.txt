GLE arrays v6.3 array construction tests
=========================================

Run each script from this directory with the v6.3 Windows CLI build.

Core tests:
- array_create_c.gle
  * C() with more than five arguments
  * concatenating scalars and existing arrays
  * flattening nested arrays
- array_create_rep.gle
  * REP(value, count) for scalars and arrays
  * zero repetitions (empty array)
- array_create_strings.gle
  * checks that C() and REP() preserve string elements
- array_create_plot_smoke.gle
  * combines C(), REP(), and ARRAYDATA plotting

Expected console output for array_create_c.gle:

    3
    6
    6
    9
    5
    4
    5
    9
    9

Expected console output for array_create_rep.gle:

    4
    28
    7
    6
    1
    3
    1
    3
    0

Expected console output for array_create_strings.gle:

    3
    3

Expected console output for array_create_plot_smoke.gle:

    4
    30
    6
    5
    4

The plot smoke test should show two datasets, both sourced from native
arrays. The two REP error scripts are separate because each is expected
to terminate with an error:

- array_create_negative_rep_error.gle
- array_create_fractional_rep_error.gle

Design notes:
- C() accepts one or more arguments, has no five-argument ceiling, and
  concatenates arrays by flattening their contents.
- REP(value, count) repeats a scalar or repeats an entire input array.
- Both constructors preserve GLE cell types rather than coercing values
  to numbers, so string construction is already supported internally.
- Maximum constructed array length: 1,000,000 elements.

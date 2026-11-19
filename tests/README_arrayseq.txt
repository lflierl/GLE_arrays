SEQ tests (v6)
==============

Run these tests from the tests directory with the v6 CLI build:

    gle.exe array_seq_ascending.gle
    gle.exe array_seq_descending.gle
    gle.exe array_seq_fractional_step.gle
    gle.exe array_seq_exact_fractional_endpoint.gle
    gle.exe array_seq_single_value.gle
    gle.exe arraydata_seq_integration.gle

The following tests are expected to report an error:

    gle.exe array_seq_zero_step_error.gle
    gle.exe array_seq_wrong_direction_error.gle

Syntax:

    a = SEQ(start, end)
    a = SEQ(start, end, step)

With two arguments, the step defaults to +1 for an ascending sequence and -1
for a descending sequence. An explicit step must be non-zero and point towards
the end value. The start value is always included. The end value is included
only when reached by a complete step (within a small floating-point tolerance).

Examples:

    a = SEQ(1, 5)          ! 1, 2, 3, 4, 5
    a = SEQ(5, 1)          ! 5, 4, 3, 2, 1
    a = SEQ(0, 1, 0.1)     ! 0, 0.1, ..., 1
    a = SEQ(0, 1, 0.3)     ! 0, 0.3, 0.6, 0.9

SEQ returns a native numeric array and can be combined with array arithmetic or
passed directly to ARRAYDATA. The maximum generated sequence length is 1,000,000.

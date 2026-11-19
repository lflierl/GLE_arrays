ARRAYDATA tests (v6)
====================

Run these tests from the tests directory with the v6 CLI build:

    gle.exe arraydata_basic.gle
    gle.exe arraydata_multiple.gle
    gle.exe arraydata_file_first.gle
    gle.exe arraydata_array_first.gle

The two mixed-data tests verify that file-based DATA and ARRAYDATA can coexist
in one graph, regardless of command order. The file-based DATA command should
automatically select the next free dataset identifier.

The following tests are expected to report an error:

    gle.exe arraydata_length_mismatch_error.gle
    gle.exe arraydata_uninitialized_error.gle

ARRAYDATA syntax:

    arraydata d1 x_array y_array

Both arguments must be initialized numeric arrays of equal, non-zero length.
The dataset is a normal GLE dataset and can be styled with the usual commands,
for example:

    d1 line
    d1 marker

This initial implementation intentionally supports only x/y numeric arrays.

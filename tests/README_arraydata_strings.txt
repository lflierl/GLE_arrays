ARRAYDATA string-array support (v6.5)
======================================

ARRAYDATA continues to store numeric coordinates internally. It now also
accepts one categorical string dimension:

    categories = C("one", "two", "three")
    values = C(1, 2, 3)

    begin graph
        ARRAYDATA d1 categories values
    end graph

String values are mapped to integer category positions in order of first
appearance. The original strings are retained and displayed as tick labels.
Repeated strings share the same category position.

The string array may be either the x array or the y array; the other array
must be numeric. A single ARRAYDATA command cannot currently use strings
for both dimensions. Arrays containing a mixture of numeric and string
elements are rejected with a clear error. Existing numeric ARRAYDATA
behaviour is unchanged.

Tests:
- arraydata_string_x.gle
- arraydata_string_y.gle
- arraydata_string_repeated.gle

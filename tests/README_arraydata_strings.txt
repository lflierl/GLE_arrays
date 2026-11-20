ARRAYDATA string-array support and shared categories (v6.5)
===========================================================

ARRAYDATA keeps numeric coordinates internally and accepts one categorical
string dimension:

    laboratories = C("PTB", "NRC", "BAM")
    results = C(152, 2520, 253)

    begin graph
        ARRAYDATA d1 laboratories results
        d1 marker cross
        xsubticks off
    end graph

Strings are mapped to integer category positions in order of first appearance.
The original strings are used as tick labels. Repeated strings share a position.

Multiple ARRAYDATA datasets may use string arrays on the same axis. Their
categories share one graph-wide mapping: categories already seen retain their
positions and previously unseen categories are appended. This also allows an
ARRAYDATA dataset to supply error magnitudes for another dataset:

    ARRAYDATA d1 laboratories results
    ARRAYDATA d2 laboratories errors
    d1 err d2

A single graph currently supports categorical strings on either x or y, but not
both axes simultaneously. Existing axis-name data (for example, xnames from d1)
cannot be combined with ARRAYDATA-managed category labels on that axis. Mixed
numeric/string elements within one array are rejected.

Tests:
- arraydata_string_x.gle
- arraydata_string_y.gle
- arraydata_string_repeated.gle
- arraydata_string_shared_axis.gle
- arraydata_string_error_bars.gle

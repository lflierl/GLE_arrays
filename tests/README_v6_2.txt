GLE arrays v6.2 smoke test
===========================

Run from this directory with the v6.2 Windows CLI build:

    gle.exe v6_2_smoke.gle

The script combines:
- SEQ(start, end, step), including a fractional step
- scalar/array arithmetic
- array statistics and indexing
- ARRAYDATA using lowercase variable names
- file-based DATA in the same graph, after ARRAYDATA
- standard graph titles and dataset styling

Expected console values from the sequence/arithmetic checks:

    4
    0
    0.3
    0.6
    0.9
    7.6

The graph should contain three datasets: d1 and d3 from arrays, and d2
from arraydata_file.dat. No sorting tests are included because sorting
was already tested separately in v5.

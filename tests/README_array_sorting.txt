GLE native array sorting — v5 tests
===================================

Branch: array-math-v5
Repository: https://github.com/lflierl/GLE_arrays

Function
--------
  b = SORT(a)       ascending (default)
  b = SORT(a, 1)    ascending
  b = SORT(a, -1)   descending

SORT returns a new native numeric array. It does not modify the source
array. The direction argument, when supplied, must be exactly 1 or -1.

Test scripts
------------
- array_sort_ascending.gle: default ascending order and source preservation
- array_sort_direction.gle: explicit ascending/descending and source preservation
- array_sort_already_sorted.gle: already sorted input
- array_sort_reverse_sorted.gle: reverse-sorted input
- array_sort_single_element.gle: one-element input
- array_sort_mixed_numeric.gle: whole and fractional numeric values
- array_sort_invalid_direction_error.gle: expected error for direction 0

Run
---
In PowerShell, from the extracted test folder:

  & "C:\path\to\gle.exe" ".\array_sort_ascending.gle"

Replace the executable path with the gle.exe from your development build.

The invalid-direction test is expected to fail with the documented error;
a successful execution is not a pass for that test.

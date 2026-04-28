# DevTools Part 2 - Debugging

## Screenshots

[result-calculateSum](../../expand/screenshots/result-calculateSum.png)

[result-dataType](../../expand/screenshots/result-dataType.png)

[fix](../../expand/screenshots/fix.png)

## Questions

# DevTools Part 2

**What was the bug?**
The bug was that the values from the two input fields were being read as strings instead of numbers. Because of that, JavaScript used string concatenation when adding them, so values like `2` and `3` became `"23"` instead of `5`.

**How would you fix it?**
I would convert both input values to numbers before passing them into the calculation. One way to fix it is to wrap each `.value` with `Number(...)` so the program performs numeric addition instead of string concatenation.

## Part 2 (Questions 1–11): More Scoping Practice

1. **What will happen at line 12 and why?**
   - **Printed**: `3`
   - **Error**: No error.
   - **Why**: `i` is declared with `var`, which is **function-scoped**. After the loop ends, `i === prices.length === 3`, so `console.log(i)` prints 3.

2. **What will happen at line 13 and why?**
   - **Printed**: `150`
   - **Error**: No error.
   - **Why**: `discountedPrice` is declared with `var` inside the loop, but `var` is **function-scoped**, so it still exists after the loop. Its last assigned value is \(300 \times (1 - 0.5) = 150\).

3. **What will happen at line 14 and why?**
   - **Printed**: `150`
   - **Error**: No error.
   - **Why**: `finalPrice` was declared with `var` at the top of the function (function-scoped). Each loop iteration updates it, and the last update is 150, so line 14 prints 150.

4. **What will this function return? Why?**
   - **Return value**: `[50, 100, 150]`
   - **Error**: No error.
   - **Why**: The loop computes each discounted (and rounded) price and pushes it into `discounted`, then returns that array.

5. **What will happen at line 12 and why?**
   - **Printed**: Nothing.
   - **Error**: Yes — `ReferenceError: i is not defined`.
   - **Why**: Here `i` is declared with `let` in the `for` loop header, so it is **block-scoped to the loop** and cannot be accessed after the loop ends.

6. **What will happen at line 13 and why?**
   - **Printed**: Nothing.
   - **Error**: Yes — `ReferenceError: discountedPrice is not defined`.
   - **Why**: `discountedPrice` is declared with `let` inside the loop block, so it is **block-scoped** and not accessible outside the loop.

7. **What will happen at line 14 and why?**
   - **Printed**: `150`
   - **Error**: No error.
   - **Why**: `finalPrice` is declared with `let` outside the loop (function block scope), so it is accessible at line 14. After the loop, its last value is 150.

8. **What will this function return? Give a brief explanation.**
   - **Return value**: `[50, 100, 150]`
   - **Error**: No error.
   - **Why**: `discounted` and `finalPrice` exist for the whole function, the loop fills the array, and the function returns it.

9. **What will happen at line 11 and why?**
   - **Printed**: Nothing.
   - **Error**: Yes — `ReferenceError: i is not defined`.
   - **Why**: `i` is declared with `let` in the `for` loop header, so it is **block-scoped to the loop** and not available at line 11 (outside the loop).

10. **What will happen at line 12 and why?**
   - **Printed**: `3`
   - **Error**: No error.
   - **Why**: `length` is declared with `const` in the function scope, so it’s accessible after the loop. `prices.length` is 3.

11. **What will this function return? Give a brief explanation.**
   - **Return value**: `[50, 100, 150]`
   - **Error**: No error.
   - **Why**: `discounted` is a `const` array (you can still `push` into it), `discountedPrice` is a `const` inside the loop (new each iteration), and the function returns the filled `discounted` array.

## Data Types (Objects)

12. Given the `student` object:

- **A. Access the value of `name`**: `student.name`
- **B. Access the value of `Grad Year`**: `student['Grad Year']`
- **C. Call the `greeting` function**: `student.greeting()`
- **D. Access the `name` inside `Favorite Teacher`**: `student['Favorite Teacher'].name`
- **E. Access index 0 of `courseLoad`**: `student.courseLoad[0]`

## Basic Operators & Type Conversion

For each expression, here is the **output** and a brief **why**.

13. Arithmetic

- **`'3' + 2`** → `'32'` (string concatenation because `+` with a string makes the other operand a string)
- **`'3' - 2`** → `1` (`-` forces numeric conversion: `3 - 2`)
- **`3 + null`** → `3` (`null` converts to `0`)
- **`'3' + null`** → `'3null'` (`null` becomes `'null'` and concatenates)
- **`true + 3`** → `4` (`true` converts to `1`)
- **`false + null`** → `0` (`false` → `0`, `null` → `0`)
- **`'3' + undefined`** → `'3undefined'` (`undefined` becomes `'undefined'` and concatenates)
- **`'3' - undefined`** → `NaN` (`undefined` converts to `NaN`, and `3 - NaN` is `NaN`)

14. Comparison

- **`'2' > 1`** → `true` (`'2'` converts to number `2`, and `2 > 1`)
- **`'2' < '12'`** → `false` (both are strings, so it compares lexicographically: `'2'` is greater than `'1'`)
- **`2 == '2'`** → `true` (`==` does type coercion, `'2'` becomes `2`)
- **`2 === '2'`** → `false` (`===` requires same type; number vs string)
- **`true == 2`** → `false` (`true` → `1`, and `1 == 2` is false)
- **`true === Boolean(2)`** → `true` (`Boolean(2)` is `true`, and both are boolean)

15. **Difference between `==` and `===`**:
  - **`==`** compares values **after type coercion** (it may convert types).
  - **`===`** compares **both type and value** (no type coercion).

## Functions (Callbacks)

17. If we call `modifyArray([1,2,3], doSomething)`, the result is:

- **Return value**: `[2, 4, 6]`
- **Why**: The loop calls `doSomething` on each element. `doSomething(num)` returns `num * 2`, so each element is doubled and pushed into `newArr`.

## setTimeout / Event Loop

19. For the `printNums()` code, the output is:

- **Output order**:
  1. `1`
  2. `4`
  3. `3`
  4. `2`
- **Why**: `1` and `4` run immediately. `setTimeout(..., 0)` runs after the current call stack finishes (so it prints `3` next). The `1000ms` timeout prints `2` last.

## Part 1 (Questions 1–7): Variables & Scoping

1. **(var) What is printed by line 9? Does an error occur? Why?**
   - **Printed**: `values added:  20`
   - **Error**: No error.
   - **Why**: `add` is `true`, so the `if (add)` block runs, `result` becomes \(10 + 10 = 20\), and line 9 logs it.

2. **(var) What is printed by line 13? Does an error occur? Why?**
   - **Printed**: `final result:  20`
   - **Error**: No error.
   - **Why**: `var` is **function-scoped**, not block-scoped. Even though `result` is declared inside the `if` block, it is still accessible later in the function at line 13.

3. **Why should you not use `var`?**
   - **Answer**: You should generally avoid `var` because it is **not block-scoped** (it’s function-scoped) and can be **redeclared**, which makes it easier to accidentally reuse/overwrite variables and cause hard-to-find bugs. `let`/`const` follow block scope and are safer.

4. **(let) What is printed by line 9? Does an error occur? Why?**
   - **Printed**: `values added:  20`
   - **Error**: No error at line 9.
   - **Why**: The `if` block runs, `result` becomes 20, and line 9 logs it.

5. **(let) What is printed by line 13? Does an error occur? Why?**
   - **Printed**: Nothing.
   - **Error**: Yes — `ReferenceError: result is not defined` (when line 13 runs).
   - **Why**: `let` is **block-scoped**, so `result` only exists inside the `if (add) { ... }` block. Line 13 is outside that block, so `result` cannot be accessed there.

6. **(const) What is printed by line 9? Does an error occur? Why?**
   - **Printed**: Nothing.
   - **Error**: Yes — `TypeError: Assignment to constant variable.` (at line 7).
   - **Why**: `const result = 0;` creates a constant binding, so `result = num1 + num2;` tries to **reassign** `result`, which is not allowed. The program errors before line 9 executes.

7. **(const) What is printed by line 13? Does an error occur? Why?**
   - **Printed**: Nothing.
   - **Error**: Yes — the same `TypeError` from line 7 prevents execution from reaching line 13.
   - **Why**: Once the reassignment error happens, the function stops and no later `console.log` runs.

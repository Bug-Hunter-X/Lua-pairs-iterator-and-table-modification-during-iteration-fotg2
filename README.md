# Lua pairs iterator and table modification

This repository demonstrates a potential issue with Lua's `pairs` iterator when combined with table modification within the iteration loop.  The `pairs` iterator does not guarantee any specific order of iteration, and modifying the table during iteration can lead to elements being skipped or processed multiple times.

The `bug.lua` file contains an example of this issue: a recursive function that iterates through a nested table.  Because the table isn't modified in this specific example, there are no errors. However, if the function were to add, remove, or modify elements, the outcome may be unpredictable.

The `bugSolution.lua` file offers a safer alternative using a copy of the table, eliminating the risk of issues during iteration.
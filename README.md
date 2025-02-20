# VHDL Integer Overflow Bug
This repository demonstrates a common error in VHDL: integer overflow in a counter.  The `buggy_counter.vhdl` file contains a counter that does not handle overflow, leading to unexpected behavior once it reaches its maximum value (15 in this case). The `fixed_counter.vhdl` provides a solution.

## Bug Description
The `buggy_counter` entity uses an integer type for the counter. When the counter reaches its maximum value (15), incrementing it leads to undefined behavior.  The VHDL standard does not explicitly define what happens in such cases. 

## Solution
The solution uses a modulo operator to wrap the counter back to 0 after it reaches 15. This ensures predictable behavior and avoids the overflow issue.

## How to reproduce
1. Synthesize and simulate `buggy_counter.vhdl`. Observe the behavior when the counter exceeds 15.
2. Synthesize and simulate `fixed_counter.vhdl`. Note the correct wraparound behavior.

# VHDL Counter Bug: Missing 'else' Statement

This repository demonstrates a common but subtle bug in VHDL code related to a missing `else` statement within a conditional process.  The bug involves a simple counter that might not increment correctly under specific circumstances.

## The Bug

The `buggy_counter.vhdl` file contains the buggy VHDL code.  The issue lies within the `process` block.  The conditional statement (`if internal_count = 15 then ...`) handles the counter rollover from 15 to 0. However, the lack of an `else` statement means that if `internal_count` is not equal to 15, the counter is not updated, leading to a stalled or incorrect count.

## The Solution

The `fixed_counter.vhdl` file provides a corrected version of the VHDL code.  An `else` statement is added to ensure that the counter increments in all cases except when the reset signal is active.

## How to Reproduce

1.  Simulate the `buggy_counter.vhdl` using your favorite VHDL simulator (e.g., ModelSim, GHDL).
2.  Observe that the counter's behavior is not as expected. 
3.  Simulate the `fixed_counter.vhdl` to verify the solution's correctness.

This example highlights the importance of careful code structure and the attention to detail needed to write robust VHDL code.
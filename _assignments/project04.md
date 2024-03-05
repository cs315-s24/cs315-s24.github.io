---
layout: assignment
due: 2024-03-20 23:59:59 -0800
github_url: https://classroom.github.com/a/_lJu_a5L
published: true
---

## Requirements 

1. You will write an emulator in C for a subset of the RISC-V Instruction Set Architecture (ISA). 
1. You do not have to emulate the entire instruction set; just enough to emulate `fib_rec`, `get_bitseq`, `is_pal`, `max3`, `quadratic`, `sort`, and `to_upper`. 
1. You will use your implementation of `sort`/`find_max_index` and `str_to_int`/`int_to_str`. The other assembly implementations are given.
1. Your emulator will need the logic (decoding and emulating instructions) and state (`rv_state`) from lab04
1. Your emulator will support dynamic analysis of instruction execution. Here are the metrics you will collect:
    1. \# of instructions executed (`i_count`)
    1. \# of I-type and R-type instructions executed (`ir_count`)
    1. \# of LD instructions executed (`ld_count`)
    1. \# of ST instructions executed (`st_count`)
    1. \# of jump instructions executed including `j`, `jal`, `jalr` (`j_count`)
    1. \# of conditional branches taken (`b_taken`)
    1. \# of conditional branches not taken (`b_not_taken`)
1. Your emulator will include an implementation of a processor cache simulator for the following cache types: 
    1. A direct mapped cache with a block size on 1 word (given)
    1. A direct mapped cache with a block size of 4 words
    1. A 4-way set associative cache with a block size of 1 word and LRU slot replacement
    1. A 4-way set associative cache with a block size of 4 words and LRU slot replacement

## Given
1. In lecture and lab, we will: 
    1. illustrate how to decode machine code and execute the operations specified
    1. illustrate a direct-mapped cache and describe the data structures and algorithms required for a set-associative cache
    1. We have written a [Guide to Cache Memory]({{ site.url }}/guides/cache-memory.html) to help you develop your cache implementation
1. In-class coding will be pushed to Github. You will provide the rest of the code yourself
1. Watch CampusWire for updated test cases for the emulation targets

## Grading Rubric
**Automated testing**

70 pts: Automated tests

**Interactive grading**

10 pts: code walkthrough including, but not limited to, your implementation of dynamic analysis and the instruction cache.

**Coding Style**

20 pts: Clean repo, consistent naming and indentation, no dead code, no unnecessarily complex code
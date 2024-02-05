---
layout: assignment
due: 2024-02-26 23:59:59 -0800
github_url: https://classroom.github.com/a/ba5wc5CO
---

## Requirements

1. You will develop RISC-V assembly language implementations of the following problems, and print the results to ensure that both the C implementation and your RISC-V implementation compute the correct answer.
1. Your executables must be named as follows, and must be compiled with a `Makefile`
1. We will test your projects using autograder

**pack_bytes**

Given four 1-byte values (unsigned), you will combine them into a single 32-bit signed integer value.

    $ ./pack_bytes
    usage: pack_bytes <b3> <b2> <b1> <b0>

    $ ./pack_bytes 1 2 3 4
    C: 16909060
    Asm: 16909060

    $ ./pack_bytes 255 255 255 255
    C: -1
    Asm: -1

**unpack_bytes**

Given a signed 32 bit integer value, unpack each byte as an unsigned value:

    $ ./unpack_bytes 1000000
    C: 0 15 66 64
    Asm: 0 15 66 64

    $ ./unpack_bytes -2
    C: 255 255 255 254
    Asm: 255 255 255 254

**get_bitseq** (this will be developed in class)

Given a 32-bit unsigned integer, extract a sequence of bits and return as an unsigned integer. Bits are numbered from 0 at the least-significant place to 31 at the most-significant place. Here is the usage:

`get_bitseq <value> <start_bit> <end_bit> `

    $ ./get_bitseq 94117 12 15 
    C: 6
    Asm: 6

    $./get_bitseq 94117 4 7
    C: 10
    Asm: 10

**get_bitseq_signed**

Given a 32-bit unsigned integer, extract a sequence of bits and return as a signed integer. Bits are numbered from 0 at the least-significant place to 31 at the most-significant place. When computing the signed return value you can assume the end_bit is the most significant bit of the signed bit range. You need to sign-extend this value to become a 32-bit 2's complement signed value. Here is the usage:

`get_bitseq_signed <value> <start_bit> <end_bit>`

    $ ./get_bitseq_signed 94117 12 15 C: 6
    Asm: 6

    $./get_bitseq_signed 94117 4 7
    C: -6
    Asm: -6

**merge**

Given the array length followed by an array containing two sub-arrays in sorted order, merge combines the sub-arrays

    $./merge 6 1 3 5 2 4 6
    C: 1 2 3 4 5 6
    Asm: 1 2 3 4 5 6

**merge_sort**

Given the array length followed by array values, merge_sort recursively sorts the array in ascending order.

    $ ./merge_sort 6 6 4 1 2 5 3
    C: 1 2 3 4 5 6
    Asm: 1 2 3 4 5 6

## Given

The starter repo contains C implementations for each of the programs

## Rubric

1. 80 points: automated test cases
1. 5 points: clean repo (no build products) which compiles and links successfully
1. 15 points: code quality: consistent formatting, no dead or redundant code, no unnecessarily complex code, readable comments

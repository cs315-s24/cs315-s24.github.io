---
layout: assignment
due: 2024-01-29 23:59:59 -0800
github_url: https://classroom.github.com/a/haEgkczv
published: true
---

## Requirements

You will install an emulated RISC-V environment on your laptop using [these instructions](https://github.com/usfca-cs-tools/docs/blob/main/risc-v-setup-git.md)

## Rubric

You must demonstrate that you can do the follow actions with your qemu/debian image
1. Start qemu running debian with start.sh
1. ssh into your debian guest
1. Create hello.c with a terminal-based editor (micro/vim/etc.)
1. Compile hello.c with gcc (`gcc -o hello hello.c`)
1. Run hello
1. Clone your lab01 github repo with ssh

Here is a hello.c:

```c
#include <stdio.h>

int main(int argc, char **argv) {
    printf("Hello, CS315!\n");
    return 0;
}
```

---
layout: assignment
due: 2024-01-24 23:59:59 -0800
github_url: https://classroom.github.com/a/haEgkczv
published: true
---

## Requirements

You will install an emulated RISC-V environment on your laptop using [these instructions](https://github.com/usfca-cs-tools/docs/blob/main/risc-v-setup-ubuntu.md)

## Rubric

You must demonstrate that you can do the follow actions with your qemu/ubuntu image
1. Start qemu running ubuntu with start.sh
1. ssh into your ubuntu guest
1. Create hello.c with a terminal-based editor (micro/vim/etc.)
1. Compile hello.c with `make`
1. Run hello
1. Clone your github repo with ssh

Here is a hello.c:

```c
#include <stdio.h>

int main(int argc, char **argv) {
    printf("Hello, CS315!\n");
    return 0;
}
```

Here is a sample `Makefile`:

```make
PROG = lab01

OBJS = lab01.o

%.o: %.c
	gcc -c -g -o $@ $<

$(PROG): $(OBJS)
	gcc -g -o $@ $^

clean:
	rm -rf $(PROG) $(OBJS)
```
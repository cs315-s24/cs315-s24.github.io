---
layout: assignment
due: 2024-01-25 23:59:59 -0800
github_url: https://classroom.github.com/a/nFEK7nSD
published: true
---

## Requirements

You will install an emulated RISC-V environment on your laptop using [these instructions](https://github.com/usfca-cs-tools/docs/blob/main/riscv-setup-ubuntu.md)

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
    printf("Hello, CS 315!\n");
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

## Autograder 

To set up the autograder on your Ubuntu guest

1. Clone the repo which contains the code
    ```
    cd
    git clone git@github.com:/phpeterson-usf/autograder
    ```
1. Clone the repo which contains the test cases (these may be updated during the semester)
    ```
    git clone git@github.com:/cs315-s24/tests
    ```
1. Edit `~/.bashrc` using a text editor (micro, vim, nano) and adding the line
    ```
    export PATH=~/autograder:$PATH
    ```
    Be careful not to add spaces around the `=`

## BeagleV-Ahead boards

1. The CS department has purchased a handful of [BeagleV-Ahead boards](https://www.beagleboard.org/boards/beaglev-ahead) for students to connect to using `ssh`
1. The BeagleV-Ahead boards run Ubuntu and connect to the CS department home directories, just like the `vlab` and `clab` VMs. Therefore your repos are available there.
1. If your laptop gets lost/stolen/broken, you can `ssh beagle` (the hostname is subject to change) to connect to one of the boards
1. You'll need to run the autograder setup steps from above in order to test your solutions
1. The BeagleV-Ahead boards are shared between Prof. Benson's CS 631 sections and our CS 315 sections. This may create contention -- we'll see.

## Rubric

100 pts as shown by the `grade` script
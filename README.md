# CS-537-Project-3-Memory-Management-solved

Download Here: [CS 537 Project 3: Memory Management solved](https://jarviscodinghub.com/assignment/project-3-memory-management-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

Overview
There is only a single part to this project:

The Null Pointer and Other Tricks: to be done in our xv6 hacking environment. Before you begin, we highly recommend that you watch two videos from a previous discussion section. The first video will be relevant starting at minute 28:45. The second video starts out relevant, but there is a Question and Answer section starting at time 31:10 which isn’t incredibly useful for this project and you may want to skip.
Notes
This project can be done with a single partner. Copying code (from other groups) is considered cheating. Read this for more info on what is OK and what is not!

Handing It In
The handin directory is ~cs537-1/handin/SECTION/login/p3 where login is your login and SECTION is your unofficial discussion section (e.g, 301).

Copy all of your source files (but not .o files, please, or binaries!) into the xv6/ subdirectory of your p3 directory. A simple way to do this is to copy everything into the destination directory directory, then type make to make sure it builds, and then type make clean to remove unneeded files.

Into your p3 directory, please make a README file. In there, describe what you did a little bit. The most important bit, at the top, however, should be the authorship of the project, particularly if you had a partner. Include both partner’s names and CS logins to receive credit; please put the README in BOTH partners’ directories; put the code in just one. Do not put any code in the other person’s handin directory!

You are required to submit a number of user programs that you can use for showing that your kernel handles a number of interesting cases correctly. You should place these files in the user directory of your xv6 source code and you should modify makefile.mk to include these new user programs. When we test your project, we will tests that are very similar to these.

null.c : This short user program should simply dereference a null pointer; the expected behavior is that this program should segfault.
null-syscall.c : pass a null pointer to a system call (of your choice); this bad argument should not cause a segfault in kernel.
badaddress-syscall.c : pass an invalid address (i.e., an address that is between the stack and heap in your address space) to a syscall; this invalid address should be caught without a segfault in kernel.
small-stack.c : call a function that allocates only a small number of variables on the stack (less than 1 page worth). You should ensure that the function can use (write-read) variables allocated on the stack; also examine the address of stack-allocated variable and make sure that address looks “reasonable”.
stack-growth.c : call a nested-series of functions (e.g., call A() which calls B() which calls C() and so forth…); each function should have less than 1 page of local variables, but the sum of all the local variables should be much greater than 1 page. You should ensure that the functions can use variables allocated on stack and examine the addresses of stack-allocated variable to make sure they look “reasonable”.
fault.c : access an invalid address (that is not part of stack or heap); this should cause a segfault.
malloc.c : allocate a bunch of memory on the heap using multiple calls to malloc() and ensure that the process can access it.
overcommit-stack.c and overcommit-heap.c: keep growing the stack and heap until the virtual address space is overcommitted (i.e., the stack and heap meet in the middle; it is fine if you keep a single unallocated page as a buffer between the stack and heap or if you do not, as long as the two cannot share a page). A failure of some type should occur once memory is overcommitted. For overcommit-stack.c, a request to grow the stack should fail; for overcommit-heap.c, a request to grow the heap should fail.

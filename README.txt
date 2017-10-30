This directory contains:

myAllocator.c: a first-fit allocator
myAllocator.h: its header file

myAllocatorTest1.c: a test program for my allocator 

myAllocatorTest2.c: a test program for allocator nextFit

malloc.c: a replacement for malloc that uses my allocator
test1.c: a test program that uses this replacement malloc

Makefile: a fairly portable "makefile", targets "all" and "clean"

To compile: 
 $ make 
To clean:
 $ make clean

The cygwin runtime uses malloc() and brk() extensively.  It is
interesting to compare the output of test1 & myAllocatorTest1.  All
those extra allocated regions are being used by cygwin's libraries!

By using make to create objects, a myAllocatorTest2 object will be created to test nextFit implemenatiation.

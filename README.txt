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


********************Section added to README**************************
By using make to create objects, a myAllocatorTest2 object will be
created to test nextFit implementation.

For nextFit implementation, I used a BlockPrefix_t global variable called
currPrefix in order to keep track of the last prefix that was stored
so we did not have to start from the beginning in order to check for the
next available space. Then, I checked that the next prefix has not
been used yet so we can continue using it.


*Note: For this lab, I received assistance from Luis Casillas who has
already taken this class on previous semesters.

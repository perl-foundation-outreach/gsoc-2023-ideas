MIR backend for MoarVM's Just In Time compiler
==================================

Description
-----------

MoarVM currently has 2 JIT compilers, the Lego JIT and the expression JIT.
The original Lego JIT uses predefined building blocks (hence Lego) to generate machine code matching the MoarVM bytecode.
This is simple, but since building blocks are independent of each other, it results in lots of unnecessary memory traffic.
The newer expression JIT is much smarter, by taking an abstract definition of the ops as input and uses a register allocator to avoid unnecessary memory access, but it does not yet support everything the Lego JIT does.
Both JIT compilers were written by the same author who has since found less and less time to finish the transition to the expression JIT or implement more interesting optimizations.
Just using LLVM JIT has been suggested numerous time, but for various reason that's not a good match for MoarVM.

On the other hand [MIR](https://github.com/vnmakarov/mir) is a very promising Just in Time compiler that is suited very well for MoarVM's needs.
It is very fast, features proven optimizations, has a more healthy bus factor and could replace not only the JIT backend, but also dyncall/libffi for NativeCall.

Expected outcomes
-----------------

An implementation taking at least the Lego JIT's graph and producing machine code from it.
Integration into our build system.


Required skills
---------------

A firm grasp of C99.


Rating
------

Medium.


Possible mentors
----------------

Stefan Seifert <nine@detonation.org>

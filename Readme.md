# MMult

These are a collection of matrix matrix multiplication kernels. Two reference kernels, written in C, are provided, as well as a C test harness.
The other kernels are written in x86 assembly (using the MSVC x64 calling convention) that leverage AVX and FMA instructions on the YMM registers.
This project was motivated as an exercise in writing assembly and experimenting with the AVX instructions by hand.

Release:
ml64 /c kern1.asm
ml64 /c kern2.asm
cl /arch:AVX2 /fp:fast /MD mmtest.c util.c /link kern1.obj kern2.obj

ml64 /c /Zi /Zd kern1.asm
ml64 /c /Zi /Zd kern2.asm
cl /arch:AVX2 /fp:fast /MDd /Zi mmtest.c util.c /link /DEBUG:FULL kern1.obj kern2.obj
# The Baabnq Programming Language

### Introduction
The Baabnq Programming Language is a low level development platform, made to target custom processors and architectures. Baabnq doesn't compile to a conventional assembler, instead it's designed for S1monsAssembly, an extremely simplistic assembler that can be retargeted with little effort. In addition to this, Baabnq is modular and separated from other systems, being able to leave certain features completely out of the program and thus the subsequent assembly. 


Caution: Baabnq can become very unmanageable if used without care. This is also the reason baabnq is not recommended for very large projects.

### Installation
1. Make sure Python3 and Git are installed
2. Clone the Baabnq repository:             ```git clone https://github.com/PyVa-exe/Baabnq```
3. Clone the S1monsAssembly repository:     [```git clone https://github.com/PyVa-exe/S1monsAssembly4-VM-v2```](https://github.com/PyVa-exe/S1monsAssembly4-VM-v2)

### Compiling and Running

###### Create a ```main.baabnq``` file (here an example with 'Hello World'):
```c
use 'libs/string.baabnq';
new 'Hello World' _ptr;
push _ptr;
sub String::PrintString;
```

###### Compile:
```bash
python Compiler.py --input main.baabnq --output out.s1
```
In order for this to compile, "libs/string.baabnq" needs to be present in the working directory.

###### Run with Virtual Machine:
```bash
python "S1monsAssembly4 Virtual Machine v2.py" --file out.s1
```

The virtual machine simulates a processor, running S1monsAssembly.
A virtual machine like this one, is often used for testing and debugging and can be found the S1monsAssembly repository, from installation step 3.
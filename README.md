# lua#(lua-sharp)
A fast, safe and light Interpreted programming language.

## Introduction
`lua` is one of the most popular programming language in game-programming. But, lua's language features is not much suitable for the game programming(Especially in game script). Now, the most common game programming language is `C#`. You can use `Mono` to interact with C/C++ and run a `C#` code in interpret mode. `C# Mono` also has lots of disadvantages. For example, it has a poor interacting efficiency with C/C++. Its interacting mode is not easy like `lua`. So, I write the `lua#` 

`lua#` take advantages in both `lua` and `C#`. `lua` use table/metatable to implement Object-oriented programming, that cost a lots of memory. `lua#` improve a `class` keyword like `C#`, and it avoid the performance loss of type casting in byte-code interpret mode. In language features, `lua#` is more like `C#` than `lua`, you can easily take it if you has the programming experience with `C#`.

`lua#` project managment like `Java`. A lua# project will be processed to a zipped file and the lua# code will be compile to lua# VM bytecode with extension '.lpk'. `lua#` compiler has  a more advanced that can compile the `.lpk` bytecode to the machine code(Now it is available for `x86` and `aarch64` platform.

lua# is in order to make the best game proggramming language in the world! But you also can use lua# in other programming situations。

## How To Install


## Setup a easy lua# interpretor
``` C
#include <stdio.h>
#include <stdlib.h>
#include <luasharp.h>

int main(int args, char* argv[])
{
    ls_StateConfigure config = {
        // ...
        .using_std = 1,
        .entry_point = "main",
    };
    ls_State* vm = lsV_newstate(&config);
    lsV_loadfile(vm, argv[0]);
    
    char buffer[512];
    if (lsA_getmessage(vm, &buffer)) {
        printf("lua# error: %d\n", buffer);
    }
    
    lsV_run(vm);
    
    return 0;
}
```

## Learn lua#

**Tags:** #_Done
**MetaTags:** #Programación  #ToLink 
- - -

La historia desde el código fuente hasta un binario ejecutable, incluyendo la creación y uso de una biblioteca estática.
## Código Fuente (.c)

``` c
cat main.c

#include <stdio.h>
#include "function.h"

int global_var = 42;

int main() {
    int local_var = 10;
    print_message(global_var, local_var);
    return 0;
}
```

``` c
cat function.c

#include <stdio.h>

void print_message(int global, int local) {
    printf("Global: %d, Local: %d\n", global, local);
}
```

``` c
cat funciton.h

#ifndef FUNCTION_H
#define FUNCTION_H

void print_message(int global, int local);

#endif
```
## 1. Preprocesador (.i)
##### El preprocesador de C expande las directivas \#include, reemplaza macros y genera un archivo .i.


``` bash
gcc -E main.c -o main.i
gcc -E function.c -o function.i
```

``` c
cat main.i:

Expansion of stdio.....

extern int printf(const char *format, ...);

int global_var = 42;

int main() {
    int local_var = 10;
    print_message(global_var, local_var);
    return 0;
}
```

``` c
cat function.i:

Expansion of stdio.....

void print_message(int global, int local) {
    printf("Global: %d, Local: %d\n", global, local);
}
```

## 2. Ensamblador (.s)
##### El compilador convierte el código preprocesado a instrucciones en lenguaje ensamblador.


``` bash
gcc -S main.i -o main.s
gcc -S function.i -o function.s
```

``` asm
cat main.s:

.global main
main:
    pushq   %rbp
    movq    %rsp, %rbp
    movl    $42, -4(%rbp)
    movl    $10, %edi
    movl    -4(%rbp), %esi
    call    print_message
    movl    $0, %eax
    popq    %rbp
    ret
```

``` asm
cat function.s:

.global print_message
print_message:
    pushq   %rbp
    movq    %rsp, %rbp
    movl    %edi, -4(%rbp)
    movl    %esi, -8(%rbp)
    leaq    .LC0(%rip), %rdi
    movl    -4(%rbp), %esi
    movl    -8(%rbp), %edx
    call    printf
    nop
    popq    %rbp
    ret

.LC0:
    .string "Global: %d, Local: %d\n"
```

## 3. Objeto (.o)
##### El ensamblador convierte las instrucciones de ensamblador en código máquina y genera archivos .o que contienen la tabla de símbolos y el código binario.

```bash
gcc -c main.s -o main.o
gcc -c function.s -o function.o
```

### Tabla de Símbolos en `main.o`:


```bash
nm -C main.o

main.o:
0000000000000000 D global_var
0000000000000000 T main
                 U print_message
```

| Nombre        | Tipo | Alcance | Dirección Virtual | Tamaño  | Estado             |
| ------------- | ---- | ------- | ----------------- | ------- | ------------------ |
| global_var    | int  | Global  | 0x1000            | 4 bytes | Inicializado       |
| main          | int  | Global  | 0x2000            | N/A     | Resuelto           |
| print_message | void | Externo | N/A               | N/A     | Referencia Externa |
### Tabla de Símbolos en `function.o`:

``` bash
nm -C funciton.o

function.o:
                 U printf
0000000000000000 T print_message
```

| Nombre        | Tipo | Alcance | Dirección Virtual | Tamaño | Estado             |
| ------------- | ---- | ------- | ----------------- | ------ | ------------------ |
| print_message | void | Global  | 0x3000            | N/A    | Resuelto           |
| printf        | func | Externo | N/A               | N/A    | Referencia Externa |

## 4. Creación de Biblioteca Estática (.a)
##### Los archivos objeto se agrupan en una biblioteca estática, que puede reutilizarse en diferentes programas sin necesidad de recompilación.

``` bash
ar rcs libfunction.a function.o
```

``` bash
ar t libfunction.a:

function.o
```

``` bash
nm libfunction.a:

function.o:
0000000000000000 T print_message
                 U printf
```

## 5. Enlace con Biblioteca Estática (.out)
##### El linker combina los archivos objeto y las bibliotecas estáticas para generar el ejecutable final, resolviendo las referencias externas en el proceso.

```bash
gcc main.o -L. -lfunction -o programa
```

### Tabla de Símbolos en `programa`:

``` bash
nm programa

000000000000401c B __bss_start
                 w __cxa_finalize@GLIBC_2.2.5
0000000000004008 D __data_start
0000000000004008 W data_start
0000000000004010 D __dso_handle
0000000000003de0 d _DYNAMIC
000000000000401c D _edata
0000000000004020 B _end
0000000000001190 T _fini
0000000000003fe8 d _GLOBAL_OFFSET_TABLE_
0000000000004018 D global_var
                 w __gmon_start__
000000000000201c r __GNU_EH_FRAME_HDR
0000000000001000 T _init
0000000000002000 R _IO_stdin_used
                 w _ITM_deregisterTMCloneTable
                 w _ITM_registerTMCloneTable
                 U __libc_start_main@GLIBC_2.34
0000000000001139 T main
                 U printf@GLIBC_2.2.5
0000000000001161 T print_message
0000000000001040 T _start
0000000000004020 D __TMC_END__
```

| Nombre        | Tipo | Enlazado | Dirección Real | Estado   |
| ------------- | ---- | -------- | -------------- | -------- |
| global_var    | int  | Interno  | 0x400020       | Resuelto |
| main          | int  | Interno  | 0x400000       | Resuelto |
| print_message | void | Interno  | 0x400100       | Resuelto |
| printf        | func | Dinámico | libc.so        | Resuelto |
- - - 
## ***Sources:***
- [In 54 Minutes, Understand the whole C and C++ compilation process](https://www.youtube.com/watch?v=ksJ9bdSX5Yo&list=WL&index=13&pp=gAQBiAQB)
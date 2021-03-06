# libpolynomial

`libpolynomial` is a C library of a polynomial [ADT](https://en.wikipedia.org/wiki/Abstract_data_type) that supports

- addition
- subtraction
- multiplication
- differentiation
- integration

and other useful operations.

## Installation

To install the library to the default directory (`/usr/local`) run:

```shell
$ make install
```

You can customize the directory to which it is installed by overriding `$PREFIX`:

```shell
$ PREFIX=/home/foo make install
```

## Usage

1. Include the `polynomial.h` header in your program and use the library functions accordingly.

    ```c
    #include <polynomial.h>

    int main(int argc, char **argv)
    {
        Polynomial *p = polynomial_new(2);
        polynomial_set_coefficient(p, 0, 7);
        polynomial_set_coefficient(p, 1, 2);
        polynomial_set_coefficient(p, 2, 3.5);

        Polynomial *q = polynomial_new(3);
        polynomial_set_coefficient(q, 0, 1);
        polynomial_set_coefficient(q, 1, 3);
        polynomial_set_coefficient(q, 2, 0.2);
        polynomial_set_coefficient(q, 3, 4);

        Polynomial *r = polynomial_add(p, q);

        polynomial_destroy(&p);
        polynomial_destroy(&q);
        polynomial_destroy(&r);

        return 0;
    }
    ```

2. Link the program against the static library and compile it.

    ```bash
    $ gcc foo.c -lpolynomial -o foo
    ```

## Development

`gcc` is the only build dependency. To build the library run:

```bash
$ make
```

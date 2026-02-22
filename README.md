*This project has been created as part of the 42 curriculum by ddamiba.*

# libft

## Description

**libft** is a custom C library built from scratch as part of the 42 school curriculum. The goal is to re-implement a selection of standard C library functions — as well as some additional utility functions not found in the standard library — in order to build a deep understanding of how they work at a low level.

The library is intended to be reused across future 42 projects as a personal toolkit, growing over time as new functions are added. It currently includes a core set of memory and string manipulation functions, character checks and conversions, integer/number output utilities, single linked list utilities, a re-implementation of `printf`, and a `get_next_line` utility — each organized as their own indepent modules.

---

## Library Contents

### Character Check Functions
| Function | Description |
|---|---|
| `ft_isalpha` | Returns non-zero if `c` is an alphabetic character |
| `ft_isdigit` | Returns non-zero if `c` is a decimal digit |
| `ft_isalnum` | Returns non-zero if `c` is alphanumeric |
| `ft_isascii` | Returns non-zero if `c` fits in the ASCII character set |
| `ft_isprint` | Returns non-zero if `c` is a printable character |
| `ft_isspace` | Returns non-zero if `c` is a whitespace character |

### Character Case Conversion
| Function | Description |
|---|---|
| `ft_toupper` | Converts a lowercase letter to uppercase |
| `ft_tolower` | Converts an uppercase letter to lowercase |

### Memory Functions
| Function | Description |
|---|---|
| `ft_memset` | Fills a memory area with a constant byte |
| `ft_bzero` | Sets a memory area to zero |
| `ft_memcpy` | Copies a memory area (no overlap handling) |
| `ft_memmove` | Copies a memory area (handles overlapping regions) |
| `ft_calloc` | Allocates memory for an array and zeroes it |
| `ft_memchr` | Scans memory for a byte value |
| `ft_memcmp` | Compares two memory areas byte by byte |

### String Functions
| Function | Description |
|---|---|
| `ft_strlen` | Returns the length of a string |
| `ft_strdup` | Returns a newly allocated copy of a string |
| `ft_strndup` | Returns a newly allocated copy of at most `n` bytes of a string |
| `ft_strchr` | Returns a pointer to the first occurrence of a character in a string |
| `ft_strrchr` | Returns a pointer to the last occurrence of a character in a string |
| `ft_strncmp` | Compares at most `n` bytes of two strings |
| `ft_strlcpy` | Copies a string into a sized buffer, always null-terminating |
| `ft_strlcat` | Appends a string to a sized buffer, always null-terminating |
| `ft_strnstr` | Finds a substring within a length-limited string |
| `ft_substr` | Returns a freshly allocated substring |
| `ft_strjoin` | Returns a freshly allocated concatenation of two strings |
| `ft_strtrim` | Returns a copy of a string with leading/trailing characters from a set removed |
| `ft_split` | Splits a string by a delimiter character, returning a null-terminated array |
| `ft_strmapi` | Applies a function to each character of a string, returning a new string |
| `ft_striteri` | Applies a function to each character of a string in place |

### Conversion Functions
| Function | Description |
|---|---|
| `ft_atoi` | Converts a string to an `int` |
| `ft_atol` | Converts a string to a `long` |
| `ft_atoll` | Converts a string to a `long long` |
| `ft_itoa` | Returns a freshly allocated string representing an integer |

### Output Functions
| Function | Description |
|---|---|
| `ft_putchar_fd` | Writes a character to a file descriptor |
| `ft_putstr_fd` | Writes a string to a file descriptor |
| `ft_putendl_fd` | Writes a string followed by a newline to a file descriptor |
| `ft_putnbr_fd` | Writes an integer to a file descriptor |
| `ft_putnbr_base` | Writes an integer in a given base to stdout |

### Linked List Functions
| Function | Description |
|---|---|
| `ft_lstnew` | Creates a new list node |
| `ft_lstadd_front` | Adds a node at the beginning of a list |
| `ft_lstadd_back` | Adds a node at the end of a list |
| `ft_lstsize` | Returns the number of nodes in a list |
| `ft_lstlast` | Returns the last node of a list |
| `ft_lstdelone` | Deletes and frees a single node |
| `ft_lstclear` | Deletes and frees the current and following nodes passed to it |
| `ft_lstiter` | Applies a function to every node's content |
| `ft_lstmap` | Applies a function to every node's content, building a new list |

### ft_printf (submodule — `ft_printf/`)

A re-implementation of the standard `printf` function. Supports the following format specifiers: `%c`, `%s`, `%p`, `%d`, `%i`, `%u`, `%x`, `%X`, and `%%`. Returns the total number of characters printed, or `-1` on error.

### get_next_line (submodule — `get_next_line/`)

A function that reads one line at a time from a file descriptor, retaining state between calls via a static buffer. Supports multiple file descriptors simultaneously. The buffer size is configurable at compile time via the `BUFFER_SIZE` macro.

---

## Instructions

### Requirements

- GCC (or compatible C compiler)
- GNU Make
- A Unix-like environment (Linux or macOS)

### Compilation

To build the full library and its independent submodules `ft_printf` and `get_next_line` :

```bash
make
```

This will produce `libft.a` in the project root as well as `libftprintf.a` and `get_next_line.a` in their respective directories

To clean object files:

```bash
make clean
```

To remove all compiled files including the library archive:

```bash
make fclean
```

To do a full rebuild:

```bash
make re
```

### Using the Library

To use `libft` in your own project, include the header and link against the archive:

```c
#include "libft.h"
```

```bash
gcc your_file.c libft.a -o your_program
```

To also use `ft_printf`, include its header and link `ft_printf/libftprintf.a`. For `get_next_line`, link `get_next_line/get_next_line.a` and include `get_next_line/get_next_line.h`.

You can customize the `get_next_line` buffer size at compile time:

```bash
gcc -D BUFFER_SIZE=64 your_file.c get_next_line/get_next_line.a -o your_program
```

---

## Resources

- [C Standard Library Reference — cppreference.com](https://en.cppreference.com/w/c)
- [The C Programming Language — Kernighan & Ritchie (K&R)](https://en.wikipedia.org/wiki/The_C_Programming_Language)
- [man pages for standard C functions](https://www.man7.org/linux/man-pages/)
- [42 Docs — libft subject]

> No AI was utilized during the development of this project.
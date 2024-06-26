# Evaluator Variables

The evaluator supports the following variable types:

| Type   | Description                                                                                           | Minimum              | Maximum              |
|--------|-------------------------------------------------------------------------------------------------------|----------------------|----------------------|
| bool   | boolean (`true` or `false`) | n/a                  | n/a                  |
| int    | signed 32-bit integer                                                                                 | -2147483648          | 2147483647           |
| uint   | unsigned 32-bit integer                                                                               | 0                    | 4294967295           |
| int64  | signed 64-bit integer                                                                                 | -9223372036854775808 | 9223372036854775807  |
| uint64 | unsigned 64-bit integer                                                                               | 0                    | 18446744073709551615 |
| double | double-precision floating point                                                                       | 1.7E-308             | 1.7E+308             |
| date   | date/time                                                                                             | 1601-01-01 00:00:00  | 9999-12-31 23:59:59  |
| str    | string                                                                                                | n/a                  | n/a                  |
| path   | path                                                                                                  | n/a                  | n/a                  |
| map    | value container                                                                                       | n/a                  | n/a                  |

When you initialise a variable, some types are inferred automatically:

| Example                | Initialises as |
|------------------------|----------------|
| x = true;              | bool           |
| x = false;             | bool           |
| x = 15;                | uint           |
| x = -15;               | int            |
| x = 5000000000;        | uint64         |
| x = -5000000000;       | int64          |
| x = 1185.15;           | double         |
| x = "string";          | str            |
| x = \[a = 1; b = 2;\]; | map            |

There are two ways you can explicity initialise a variable as a certain type. This is required for *date* and *path* variables which are always initialised from strings.

- You can use the **[As](/Manual/reference/evaluator/as.md)** operator, for example `d = "2023-08-20" as date;`
- You can use the `:` operator, for example `d: date = "2023-08-20";`

For example, to initialise a variable as a path as opposed to a plain string:

    p = "C:\Windows" as path;
    p = p + "System32";
    Output(p);

    --> "C:\Windows\System32"

Note in the above example that the final string contains a backslash between "Windows" and "System32" - that's because it was initialised as a *path* variable, and adding strings to *path* variables adds path separators automatically.

See the documentation for the **[As](/Manual/reference/evaluator/as.md)** operator for more details on explicit initialisation. The `:` operator uses the same type keywords as the **As** operator does.

The evaluator will implicitly convert variable types if needed. For example, if you call a function that's documented as taking an *int* but you pass it a *uint*, and *int64* or even a *str*, the value will be converted automatically (assuming such a conversion is possible, of course).

You can use the **[typeof](/Manual/reference/evaluator/typeof.md)** function to determine a variable's type.

### Variable names

Ordinary variables must begin with a letter; after that, they can contain any number of letters, numbers or symbols like `_` and `$`.

The evaluator also lets you access external variables that begin with a `$` sign. For example, a function that uses `@set name Jon` and then invokes evaluator code would be able to access that variable using the name `$name`. External variables scoped to tabs and Listers can be accessed, for example `$glob:name` would let you get or set a globally scoped variable from within the evaluator.

Normally, attempting to use the value of a variable that doesn't exist causes an error, however for compatibility reasons, variables that begin with a `$` allow this - if they haven't been previously defined they'll simply return an empty string.

You can also access environment variables from evaluation code as you can in normal functions. For example,

    Output(%PROGRAMFILES%);
    --> C:\Program Files

You can set environment variables from evaluation code too but note that this only affects the environment inside Opus itself - globally the rest of the system won't see the changed value.

### Numeric constants

You can express numeric constants in a number of ways:

- Plain decimal numbers such as `15` or `-15`.
- Hexadecimal numbers such as `0xe`.
- Size values such as `5kb`, `21gb`, `1.75tb` (note: only supports binary units.)
- Date units using suffixes `h` (hour), `m` (minute), `s` (second), `d` (day), `M` (month) and `y` (year) when adding to or subtracting from dates.
- Fractional numbers such as `1185.15`.
- `true` and `false` are also available as boolean constants.
- `pi` is predefined as the value of π.

### Value containers

A *value container* is a variable that can contain other variables - similar to a *struct* in C++ or a *map* in JavaScript.

Value containers are defined using the `[ ]` operator. The square brackets act like a *scope* - within the brackets, variables you assign will become members of the container. For example,

    // defines an empty container
    x = [ ];

    // defines a container with three members
    x = [ a = 5; b = 10; c = "hello!"; ];

After a value container is created and / or initialised, you can access its member variables (or add new ones) using the `.` operator.

    Output(x.c);
    --> hello!

    x.c = Left(x.c, 5) + " world!";
    Output(x.c);
    --> hello world!

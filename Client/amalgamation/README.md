# Client source amalgamation

This folder contains tooling for exporting the client codebase as a single,
monolithic source file (either `.cpp` or `.h`).

## How it works

`create_amalgamated_source.py` scans the `Client` tree for C/C++ source and
header files and concatenates them into one file. The resulting file keeps
track of the original boundaries with clear `BEGIN/END` markers and `#line`
directives so that line numbers still map back to their source files.

By default, running the script produces `ClientAmalgamated.cpp` in this folder:

```bash
python create_amalgamated_source.py
```

You can choose a different output name or extension (for example to create a
giant header instead of a translation unit):

```bash
python create_amalgamated_source.py --output ClientAmalgamated.hpp
```

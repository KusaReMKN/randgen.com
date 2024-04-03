# RANDGEN

Random number generator for MS-DOS

## How to Build

`MASM`, `LINK`, and `EXE2BIN` are required to build.  These programs are
available in binary form from [microsoft/MS-DOS].

```
MASM RANDGEN;
LINK RANDGEN;
EXEW2BIN RANDGEN RANDGEN.COM
```

## Usage

```
RANDGEN [length]
```

The **RANDGEN** command writes *`length`* bytes of random data to
standard output.  *`length`* can be a value in the range 0–65535,
inclusive.  If *`length`* is greater than 65535, the remainder divided
by 65536 is used.  If *`length`* is omitted or 0 is specified, 65535
bytes of random data are written.

## Implementation Note

The **RANDGEN** command uses the 16‐bit version of the XorShift
algorithm, and uses the current time to seed the random numbers.

## Exit Status

The **RANDGEN** command exits 0 on success, and >0 if an error occurs.

[microsoft/MS-DOS]: https://github.com/microsoft/MS-DOS

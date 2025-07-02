# swi-prolog-z3 (Fork with Array Support)

This is a fork of [`turibe/swi-prolog-z3`](https://github.com/turibe/swi-prolog-z3) with extended support for arrays and improvements in Prolog-Z3 interoperability.

## Main Changes

- Added support for `array(...)` types in the type checker (`type_inference.pl`)
- Extended and improved tests in `z3_unit_tests.pl`
- Updated `z3_utils.pl`, `z3.pl`, and C integration code
- General utilities cleanup and reorganization

## Building the Native Module (`.so`)

The file `z3_swi_foreign.so` **is not included in the repository** for portability reasons. It must be regenerated manually whenever changes are made to the C source (`z3_swi_foreign.c`).

### How to generate `z3_swi_foreign.so`

Using the command:

```bash
swipl-ld -shared -o z3_swi_foreign.so z3_swi_foreign.c -lz3
```

Make sure the `libz3-dev` package is installed:

```bash
sudo apt install libz3-dev
```

> 🔧 Alternatively, regenerate the file from within SWI-Prolog:
>
> ```prolog
> ?- [z3_swi_foreign].
> ?- make.
> ```

**Note:** The compiled `.so` file is only valid on the architecture where it was generated (e.g., Linux x86_64).

---

# Original Documentation

(Code remains unchanged below this section)

...

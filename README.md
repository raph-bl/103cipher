# 103cipher

A Hill cipher implementation in Python. The key is turned into a square matrix of ASCII codes; the message is encrypted by matrix multiplication and decrypted with the inverse key matrix. Matrix algebra (determinant, cofactors, inversion) is implemented from scratch, with no external library.

## Usage

```bash
./103cipher message key flag
./103cipher -h
```

| Argument | Description |
|---|---|
| `message` | The message (ASCII) to encrypt, or the space-separated numbers to decrypt |
| `key` | The encryption key, made of ASCII characters |
| `flag` | `0` to encrypt, `1` to decrypt |

Exits with `84` on invalid arguments or on a non-invertible key matrix.

## Examples

Encrypting:

```bash
$ ./103cipher "Hello World!" "Bonjour" 0
Key matrix:
66 111 110
106 111 117
114 0 0

Encrypted message:
27770 19203 19737 22542 24309 24867 30504 21978 22557 21490 23088 23580
```

Decrypting:

```bash
$ ./103cipher "27770 19203 19737 22542 24309 24867 30504 21978 22557 21490 23088 23580" "Bonjour" 1
Key matrix:
0.0 0.0 0.009
0.151 -0.142 0.044
-0.143 0.143 -0.05

Decrypted message:
Hello World!
```

## Requirements

Python 3, standard library only.

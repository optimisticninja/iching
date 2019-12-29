# iching

`iching` is an encoder/decoder with an optional substitution cipher using hexagrams from the book *[I Ching](https://en.wikipedia.org/wiki/I_Ching)*. It maps base64 values to *I Ching* hexagrams.

## Requirements

* CMake
* Boost >=1.66
  * `system`
  * `program_options`

## Building

```shell
$ mkdir build
$ cd build
$ cmake ..
$ make
```

## Usage

```bash
I Ching Hexagram Encoder/Decoder
Options:
  -h [ --help ]                 Print help messages
  -e [ --encode ] arg           Encode message
  -d [ --decode ] arg           Decode message
  -s [ --substitution-cipher ]  Use substitution cipher
  -k [ --key ] arg              Key for decoding substitution cipher
```

### Encoding Text

You may redirect any program output to a file by simply adding `> file.extension` to any command below.


```bash
$ ./iching -e "secret"
====  ======================================  ==================================
==============  ========  ========  ==================  ========  ========  ====
====  ======================================  ========  ==================  ====
====  ========  ==================  ========  ========  ========================
==============  ========  ========  ============================  ==============
====  ==================  ========  ========  ========  ========  ========  ====
```

### Encoding a File
```bash
$ ./iching -e $(cat filename.extension)
====  ==================  ==================  ==================================
====  ========  ============================  ========  ========  ==============
==========================================================================  ====
==============  ========  ========  ==================  ==================  ====
==============  ========  ========  ========  ========  ========  ========  ====
============================================  ==================  ==============
...
```

### Encoding with Substitution Cipher
```bash
$ ./iching -se "secret"
KEY: EzLPYjRkayhnTCv47SgoFV5MOqb+/6emNlD231JWIXUiBKfAupwc0rQ8xHsZd9Gt
======================================================  ========================
====  ==================  ==================  ========  ========  ========  ====
====  ========  ============================  ============================  ====
====  ========  ========  ========  ========  ========  ========  ==============
====  ========  ============================  ========  ========================
========================  ========  ==================  ========  ========  ====
```

### Decoding
```bash
$ ./iching -d $(cat filename.extension) > filename.decoded-extension
```

### Decoding with Substitution Cipher
```bash
$ ./iching -k "D1uZzJYgiEAdehLlT285c0OVCK7mXSkf/vQy4N+IbWR96GPn3wsMaBptrUjxoHqF" \
           -d $(cat filename.extension) > filename.decoded-extension
```

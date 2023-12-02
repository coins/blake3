# BLAKE3 WASM

BLAKE3 implementation extracted from [the reference implementation](https://github.com/BLAKE3-team/BLAKE3/blob/master/c/blake3.c) and compiled to WebAssembly.

## Usage
```js
import {blake3} from 'https://bitvm.github.io/blake3/blake3.js'

const preimage = new Uint8Array([97, 98, 99])    // Our preimage is "abc"
const digest = blake3(preimage)

console.log(digest)
```


## Development
The following command compiles the sources to wasm:
```sh
clang src/blake3.cpp -O2 --no-standard-libraries -mbulk-memory --target=wasm32 -Wl,--no-entry -o blake3.wasm
```

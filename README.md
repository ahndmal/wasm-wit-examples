
Examples of WIT (.wit) files for use with WebAssmbly

- wit bindgen: https://github.com/bytecodealliance/wit-bindgen
- component model: https://github.com/WebAssembly/component-model
- WIT reference: https://component-model.bytecodealliance.org/design/wit.html

## Wasmtime runtime

Install wasmtime:

```bash
curl https://wasmtime.dev/install.sh -sSf | bash
```

WIT can be handled by:
1. cargo component
2. wit-bindgen

## Cargo Component

Install cargo-component:

```bash
cargo install --locked cargo-component
```

Install wasm-tools:

```
cargo install --locked wasm-tools
```

### Makefile

bind:
    cargo component bindings
build:
    cargo component build
run:

## WIT Bindgen

```
rustup target add wasm32-wasip2
```

In order to compile a wasi dynamic library, the following must be added to the Cargo.toml file:

```
[lib]
crate-type = ["cdylib"]
```

Projects can then depend on wit-bindgen by executing:

```
cargo add wit-bindgen
```
Build
```
cargo build --target wasm32-wasip2
```






    wasmtime run --invoke 'hello-world()' ./target/wasm32-wasip1/debug/add.wasm
show wasm file:
  wasm-tools component wit target/wasm32-wasip1/release/add.wasm

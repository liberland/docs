# Rust API docs

Liberland Blockchain Node contains thorough in-code documentation.

## Seeing Rust API docs locally

Assuming you have your development environment setup (see [Build, Run & Test
guide](./dev.md)), execute following in main `liberland_substrate` repo
directory:

```
cargo doc --open --no-deps -p pallet-llm -p pallet-liberland-legislation -p pallet-liberland-initializer
```
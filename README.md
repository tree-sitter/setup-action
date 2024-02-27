# Tree-sitter library & CLI setup

## Options

```yaml
install-cli:
  description: Install the CLI
  default: true
install-lib:
  description: Install the library
  default: true
tree-sitter-ref:
  description: A tree-sitter commit, tag, or branch
  default: master
rust-toolchain:
  description: Rust toolchain
  default: stable
```

## Example configuration

```yaml
name: Generate

on:
  pull_request:

jobs:
  generate:
    name: Generate parser
    runs-on: ubuntu-latest
    steps:
      - uses: tree-sitter/setup-action@v1
        with:
          install-lib: false
      - run: tree-sitter generate
```

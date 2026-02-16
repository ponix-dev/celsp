# celsp

A [Language Server Protocol](https://microsoft.github.io/language-server-protocol/) implementation for the [Common Expression Language](https://github.com/google/cel-spec) (CEL), powered by [cel-core](https://github.com/ponix-dev/cel-core).

## Features

- **Diagnostics** - Real-time parse and type checking errors as you type
- **Hover** - Type information and function documentation
- **Completion** - Autocompletion for variables, functions, and message fields
- **Semantic tokens** - Accurate syntax highlighting
- **Protovalidate** - CEL validation support in `.proto` files

## Installation

### From source

```bash
cargo install celsp
```

### From GitHub releases

Pre-built binaries are available on the [releases page](https://github.com/ponix-dev/celsp/releases) for:

- Linux (x86_64)
- macOS (x86_64, aarch64)

## Configuration

Create a `settings.toml` file in your project to configure the CEL environment:

```toml
[env]
variables = { x = "int", name = "string" }
extensions = ["strings", "math"]

[env.proto]
descriptors = ["path/to/descriptor.binpb"]
```

The language server walks the file tree upward to discover `settings.toml`.

## Editor Setup

celsp works with any LSP-compatible editor. Configure your editor to run `celsp` as the language server for CEL files and `.proto` files.

## Development

```bash
# Run all tests
mise run test

# Install locally
mise run install
```

## License

Licensed under either of:

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

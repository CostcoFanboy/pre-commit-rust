# pre-commit-rust

Rust hooks for [pre-commit](https://pre-commit.com/).

## Usage

Add this to your `.pre-commit-config.yaml`:

```yaml
- repo: https://github.com/CostcoFanboy/pre-commit-rust
  rev: master  # Use the latest tag or commit hash
  hooks:
    - id: fmt
    - id: clippy
```

## Available Hooks

### cargo-check
Checks the package for compile errors without producing binaries.
```yaml
- id: cargo-check
```

### fmt (rustfmt)
Formats Rust code according to style guidelines. This hook runs in check mode and will fail if code is not formatted.
```yaml
- id: fmt
```

### clippy
Runs the Clippy linter with strict settings, treating warnings as errors.
```yaml
- id: clippy
```

### test
Runs the test suite using `cargo test`.
```yaml
- id: test
```

### audit
Checks for known security vulnerabilities in dependencies. **Requires `cargo-audit` to be installed.**

Install with:
```bash
cargo install cargo-audit
```

Then add to your config:
```yaml
- id: audit
```

## Example Configuration

Here's a complete example using all available hooks:

```yaml
- repo: https://github.com/CostcoFanboy/pre-commit-rust
  rev: master
  hooks:
    - id: cargo-check
    - id: fmt
    - id: clippy
    - id: test
    - id: audit
```

## Requirements

- Rust toolchain (rustc, cargo, rustfmt, clippy)
- `cargo-audit` (optional, only needed for the audit hook)

## License

See [LICENSE](LICENSE) file.

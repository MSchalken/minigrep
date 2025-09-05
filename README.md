# minigrep 🔎

A tiny, educational `grep`-like command‑line tool written in Rust.  
Built by following the *The Rust Programming Language* book’s minigrep project and structured to be easy to read, test, and extend.

> Search for a query string within a text file—case-sensitive by default, with optional case-insensitive mode via an environment variable.

---

## Features

- ✅ Simple CLI: `minigrep <query> <path>`
- ✅ Case‑sensitive search by default  
- ✅ Optional case‑insensitive search via `CASE_INSENSITIVE` environment variable  
- ✅ Clean separation between CLI (`main.rs`) and logic (`lib.rs`)  
- ✅ Unit tests for the search functionality

---

## Getting Started

### Prerequisites

- Rust toolchain (stable). Install via rustup.

Check your toolchain:

```bash
rustc --version
cargo --version
```

### Build

```bash
# From the repository root
cargo build
# Or build optimized
cargo build --release
```

---

## Usage

```bash
# Run from the project root
cargo run -- <QUERY> <FILE_PATH>
```

- `<QUERY>` — the string to search for (no quotes needed unless it contains spaces)
- `<FILE_PATH>` — path to the file to search

### Examples

```bash
# Case-sensitive search
cargo run -- to poem.txt

# Using the compiled binary after build
./target/debug/minigrep to poem.txt
```

**Example output (case-sensitive):**
```
To rust, or not to Rust
to boldly go
```

### Case-Insensitive Search

Enable case-insensitive matching with the `CASE_INSENSITIVE` environment variable:

**Unix/macOS (bash/zsh):**
```bash
CASE_INSENSITIVE=1 cargo run -- to poem.txt
```

**Windows PowerShell:**
```powershell
$env:CASE_INSENSITIVE=1; cargo run -- to poem.txt
```

**Windows CMD:**
```cmd
set CASE_INSENSITIVE=1
cargo run -- to poem.txt
```

---

## Testing

Run unit tests (defined in `lib.rs`):

```bash
cargo test
```

---

## Attribution

This project is based on the *minigrep* example from *The Rust Programming Language* (aka “The Rust Book”), Chapter 12: *An I/O Project: Building a Command Line Program*. It’s a great read if you want to understand every line of this implementation.

- The Rust Book (free online): https://doc.rust-lang.org/book/

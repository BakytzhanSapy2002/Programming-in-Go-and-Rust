# PGRE 2212 — Annotated sample programs for Labs 1–24 (Weeks 1–12)

Programming in Go and Rust Environments. One working, heavily commented sample program for every laboratory work from Week 1 to Week 12.
Қазақша қысқаша: әр лабораториялық жұмыс үшін толық түсіндірмелері (ағылшынша және қазақша) бар жұмыс істейтін үлгі код.

## How to use these files
1. Open a lab folder in VS Code and read the **header comment** of the main file: it explains what the lab teaches, how to run it, and shows the **real expected output**.
2. Read the code from top to bottom. Comments explain **every important part**: why a construct is used, what the compiler checks, and common mistakes.
3. Run the program, then change something (a number, a condition, remove `mut`, remove `pub`, ...) and read the compiler message.
4. Do **not** copy the code into your own lab solution. Use it to understand the idea, then write your own version (see the course AI/academic-integrity rule).


## Bilingual comments (English + Қазақша)
Every comment inside the code (except the file header, which has a Kazakh one-line summary) is followed by its Kazakh translation:
```
// `defer` postpones a call until main ends. ...        <- English
// KZ: `defer` шақыруды main аяқталғанша кейінге ...    <- Қазақша
```
* A line that starts with `// KZ:` (or `# KZ:` in Cargo.toml) is the Kazakh translation of the comment just above it.
* For a comment written at the end of a code line, the Kazakh translation is on the next line.
* The translations are plain comments: they do not change how the programs work.
* Code terms (`mut`, `pub`, `goroutine`, `channel`, `trait`, ...) are kept in English on purpose, so that students learn the real keywords.

## Requirements
* Go 1.22 or newer (`go version`). Rust with cargo (`cargo --version`), edition 2021 projects.
* Commands are written for Windows PowerShell; they also work on Linux/macOS (use `curl` instead of `curl.exe`).

## Index
| Lab | Week | Topic | Folder | Main command |
|---|---|---|---|---|
| 1 | week01 | Install toolchains and build first programs in Go and Rust | `lab01_go + lab01_rust` | `go run .  |  cargo run` |
| 2 | week01 | Compare basic compilation and execution workflows | `lab02_go + lab02_rust` | `go run . / go build  |  cargo run --release` |
| 3 | week02 | Apply Go identifier and naming rules | `lab03_go` | `go run .` |
| 4 | week02 | Write Go expressions, type conversions and input/output | `lab04_go` | `"36.6" | go run .` |
| 5 | week03 | Implement branching, loops and functions in Go | `lab05_go` | `go run .` |
| 6 | week03 | Process arrays, slices, maps and strings in Go | `lab06_go` | `go run .` |
| 7 | week04 | Define methods on Go structures | `lab07_go` | `go run .` |
| 8 | week04 | Implement an interface and package API in Go | `lab08_go` | `go run .  (+ go doc ./shapes)` |
| 9 | week05 | Handle errors in a Go application | `lab09_go` | `go run .` |
| 10 | week05 | Create a Go module and manage dependencies | `lab10_go` | `go run .  (+ go list -m all)` |
| 11 | week06 | Run concurrent Go tasks with goroutines | `lab11_go` | `go run .` |
| 12 | week06 | Coordinate goroutines using channels and cancellation | `lab12_go` | `go run .` |
| 13 | week07 | Build a simple Go HTTP server | `lab13_go` | `go run .  (then curl.exe in another terminal)` |
| 14 | week07 | Implement and test a Go API endpoint | `lab14_go` | `go test -v ./...` |
| 15 | week08 | Apply Rust identifier, type and pattern rules | `lab15_rust` | `cargo run` |
| 16 | week08 | Build a typed Rust command-line program | `lab16_rust` | `cargo run -- 10 + 5` |
| 17 | week09 | Trace Rust ownership, moves and copying | `lab17_rust` | `cargo run` |
| 18 | week09 | Refactor code to manage allocations and ownership | `lab18_rust` | `cargo run  |  cargo run --bin before` |
| 19 | week10 | Write functions using immutable and mutable borrowing | `lab19_rust` | `cargo run` |
| 20 | week10 | Resolve borrow-checker errors and explain lifetimes | `lab20_rust` | `cargo run  (+ rustc broken_examples\*.rs)` |
| 21 | week11 | Define Rust structs, enums and methods | `lab21_rust` | `cargo run` |
| 22 | week11 | Implement a trait and handle Option and Result | `lab22_rust` | `cargo run` |
| 23 | week12 | Organize source code into Rust modules | `lab23_rust` | `cargo run` |
| 24 | week12 | Create and manage a Cargo package | `lab24_cargo` | `cd app; cargo run  |  cd textkit; cargo test` |

## Folder layout
```
weekNN/labNN_go/        Go module: go.mod + main.go (+ extra files or packages)
weekNN/labNN_rust/      Cargo project: Cargo.toml + src/main.rs (+ more modules)
week10/lab20_rust/broken_examples/   programs that DO NOT compile on purpose (read the error codes)
week12/lab24_cargo/     two Cargo packages: textkit (library) and app (program that uses it)
```

## Notes
* Every program was compiled and run; the "EXPECTED OUTPUT" in each header is the real output.
* Goroutine/timing labs print results in a deterministic way (sorted or indexed), so the output is always the same.
* Lab 10: the `go get github.com/google/uuid` step needs internet and is described in the file header (not part of the offline sample).
* Lab 24: `cargo add rand` needs internet; the sample uses a local `path` dependency, which works offline.

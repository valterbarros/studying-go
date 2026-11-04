### Note

This repo was moved from another repo to see original history see: https://github.com/valterbarros/algorithms/compare/234188d1e5948c0c713667a8d54efb84905aa574...dc0ea14f4a5aa486c5c46ee30f0d5eb8486ecf0b

### Study notes

Some notes about go and important links
  - [Links](./notes/LINKS.md)
  - [Commands](./notes/COMMANDS.md)
  - [Samples of go with notes](https://github.com/valterbarros/algorithms/wiki)
  - [Go algortihm implementations](https://github.com/valterbarros/algorithms/tree/main/data-structures-galego/algorithms_go)

## Go Algorithms – Usage Guide

This folder contains Go implementations about basics like arrays, strings, etc
You can use these as learning material or as a base for your own projects.

### Run menu with algorithms
```sh
./running.sh
```

### Generate .md files
> That projects has a script to extract comments and code from .go files and put on a .md file <br>

example:

```shell
go run ./cmd/parser/main.go -file-run variables
```

Generate all files:

```shell
go run ./cmd/parser/main.go -file-run "*"
```

### Testes
generate big file

```shell
go run ./cmd/fixturegen -lines 20000 -out tests/fixtures/source.huge.source
```

run testes

```shell
go test ./parser
```

### Running with VS Code

You can also run and debug algorithms or tests directly in [Visual Studio Code](https://code.visualstudio.com/):

1. Open this folder in VS Code.
2. Go to the Run and Debug panel (or press `Ctrl+Shift+D`).
3. Choose one of the pre-configured launch options, such as running a specific algorithm or running tests.
4. You can set breakpoints and step through the code for easier debugging.

### Structure

- `main.go`: Entry point to run algorithms by category and name.
- `samples/*` - is just algorithms of learning go
- `parser/*` - is the engine to parse go files to .md

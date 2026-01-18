# HACKING

This program is written in the **Go programming-language** (**Golang**).

## Source-Code File-System Structure

The following shows the file-system structure that this program's source-code follows:

* 📂 `.`
  * 📂 `cfg/` — configurations
  * 📂 `lib/` — libraries
  * 📂 `srv/` — services
  * 📂 `www/` — HTTP handlers
  * 📄 `HACKING.md` — this file
  * 📄 `README.md`
  * 📄 `go.mod`
  * 📄 `go.sum`
  * 📄 `main.go` — contains the `main()` function.

## Go Version

The **version** of Golang that this program's source-code uses is specified in its `go.mod` file

## Coding Style

In general use `gofmt`, with the exception of when things need to be aligned across multiple lines to increase human-legibility of the source-code.

## Error Handling

In general, do _not_ used the Go built-in packages for **error handling**.
I.e., in general, do not use the Go built-in `"errors"` package, and the `fmt.Errorf()` function from the Go built-in `"fmt"` package.

Instead use the following package for **error handling**:

* https://codeberg.org/reiver/go-erorr

## Logging

In general, do _not_ used the Go built-in packages for **logging**.

Instead use the following package for **logging**:

* https://codeberg.org/reiver/go-log

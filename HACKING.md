# HACKING

This program is written in the **Go programming-language** (**Golang**).

## Source-Code File-System Structure

The following shows the file-system structure that this program's source-code follows:

* 📂 `.`
  * 📂 `cfg/` — configurations
  * 📂 `lib/` — libraries
  * 📂 `srv/` — services
  * 📂 `www/` — HTTP handlers
  * 📄 `go.mod`
  * 📄 `go.sum`
  * 📄 `HACKING.md` — this file
  * 📄 `README.md`

## Go Version

The **version** of Golang that this program's source-code uses is defined in its `go.mod` file

## Coding Style

In general use `gofmt`, with the exception of when things need to be aligned across multiple lines to increase human-legibility of the source-code.

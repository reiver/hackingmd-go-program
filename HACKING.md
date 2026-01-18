# HACKING

This program is written in the **Go programming-language** (**Golang**).

## Source-Code File-System Structure

The following shows the file-system structure that this program's source-code follows:

* 📂 `.`
  * 📂 `cfg/` — configurations
  * 📂 `lib/` — libraries
  * 📂 `srv/` — services
    * 📂 `log/` — logging service
  * 📂 `www/` — HTTP handlers
  * 📄 `HACKING.md` — this file
  * 📄 `README.md`
  * 📄 `go.mod`
  * 📄 `go.sum`
  * 📄 `main.go` — contains the `main()` function.

## Go Version

The **version** of Golang that this program's source-code uses is specified in its `go.mod` file.

For example, if a `go.mod` file was:

```
module example.com/joeblow/myprogram

go 1.25.7

require github.com/gorilla/websocket v1.5.0
```

Then the _Go version_ would be `1.25.7`.

However, that was just a fictitious example.
To discover the **version** of Golang that this program's source-code uses, look at this program's source-code's `go.mod` file.

## Go Module Name

The **module name** of this program's source-code is specified in its `go.mod` file.

For example, if a `go.mod` file was:

```
module example.com/joeblow/myprogram

go 1.25.7

require github.com/gorilla/websocket v1.5.0
```

Then the _module name_ would be `example.com/joeblow/myprogram`.

However, that was just a fictitious example.
To discover the **module name** that this program's source-code uses, look at this program's source-code's `go.mod` file.

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

## Imports

Imports have 3 groups.
For example:

```golang
import (
	"fmt"
	"io"

	"codeberg.org/reiver/go-erorr"
	"codeberg.org/reiver/go-log"
	"github.com/microcosm-cc/bluemonday"
	"github.com/yuin/goldmark"

	"srchost.tld/prgm/cfg"
	"srchost.tld/prgm/src/log"
)
```

(Note that in this example, `"srchost.tld/prgm"` represents the that program _module name_.
In the actual source-code for this program, you would use this program's actual _module name_ — which is specified in this program's `go.mod` file.)

The **top group** in an `import` is for Go built-in packages.

The **bottom group** in an `import` is for packages in this program's source-code.

The **middle group** in an `import` is for _all other_ imports.

## Coupling

### `lib/` Coupling

* Source-Code in this program's source-code's `lib/` directory **MAY** `import` Go built-in packages.
* Source-Code in this program's source-code's `lib/` directory **MAY** `import` 3rd party packages.
* Source-Code in this program's source-code's `lib/` directory **MAY** `import` other things in this program's source-code's `lib/` directory.
* Source-Code in this program's source-code's `lib/` directory **MUST NOT** import any package in this program's source-code that is outside of the `lib/` directory.
  * For example, source-code in this program's source-code's `lib/` directory **MUST NOT** important anything from this program's source-code's `cfg/`, `srv/` `www/`, etc directories.

### `srv/` Coupling

* Source-Code in this program's source-code's `srv/` directory **MAY** `import` Go built-in packages.
* Source-Code in this program's source-code's `srv/` directory **MAY** `import` 3rd party packages.
* Source-Code in this program's source-code's `srv/` directory **MAY** `import` this program's source-code's `cfg/` directory.
* Source-Code in this program's source-code's `srv/` directory **MAY** `import` packages from this program's source-code's `lib/` directory.
* Source-Code in this program's source-code's `srv/` directory **MUST NOT** `import` any other package from this program's source-code.

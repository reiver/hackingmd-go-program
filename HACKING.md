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

The **version** of Golang that this program's source-code uses is specified in its `go.mod` file.

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


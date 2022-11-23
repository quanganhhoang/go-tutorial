# Go Notes

Go code is grouped into packages, and packages are grouped into modules

## Go commands

`go mod init <module_path>` -- creates a go.mod file to track dependencies

`go mod edit -replace go-tutorial/greetings=../greetings`

`go mod tidy` -- synchronize module dependencies

`go run .`

`go test -v`

`go build` compiles the packages, along with their dependencies, but it does not install the results

`go install` compiles and installs the packages

`go list -f '{{.Target}}'` prints the install path

`go env -w GOBIN=/path/to/your/bin` to change the install target

`go get golang.org/x/example` -- add a dependency

`go work init` -- create a `go.work` file for a workspace containing the modules in the `hello` directory

`go work use [-r] [directory]` -- adds a new module to `go.work` file

`go work edit` edits the `go.work` file

`go work sync` syncs dependencies from the workspace's build list into each of the workspace modules

## Notes
- Any Go function can return multiple values
- A function whose name starts with a lowercase letter is accessible only to code in its own package i.e. it is not exported
- []string -> a slice of string. If size is omitted in the brackets, the slice can be dynamically changed
- Init a map with the following syntax: `make(map[key-type]value-type)`
- Test function names have the form `Test<Name>`
- `rune` in Go is a data type that stores codes that represent Unicode characters
- Struct tags such as json:"artist" specify what a field’s name should be when the struct’s contents are serialized into JSON
    ```
    type album struct {
        ID     string  `json:"id"`
        Title  string  `json:"title"`
        Artist string  `json:"artist"`
        Price  float64 `json:"price"`
    }
    ```
- Declare a type constraint as an interface
  ```
  type Number interface {
    int64 | float64
  }
  ```

### defer

### panic

### recover

### pointer

### goroutine

### channel

## Go standard lib
- strings
- errors
- log
- unicode

## Accessing a relational database


## Developing a RESTful API with Go and Gin


## Generics


## Fuzzing
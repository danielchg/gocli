# Cobra tutorial (Golang CLI)

## Getting started

First of all install cobra framework

```bash
go get github.com/spf13/cobra/cobra
```

Initialize the boilerplate

```bash
cobra init --pkg-name=github.com/danielchg/gocli
```

Add new option `say` to our CLI

```bash
cobra add say
```

Add subcommand `say hello`

```bash
cobra add hello
```

and edit the content of the file `cmd/hello.go` with the following in the function init

```go
func init() {
    sayCmd.AddCommand(helloCmd)
}
```

and also teh conten of the Run

```go
Run: func(cmd *cobra.Command, args []string) {
    fmt.Println("Hello World!")
},
```

## Build

```bash
go build .
```

## Run

```bash
./gocli say hello
Hello World!
```

## Links

[Tutorial](https://ordina-jworks.github.io/development/2018/10/20/make-your-own-cli-with-golang-and-cobra.html)

[Cobra framework](https://github.com/spf13/cobra)

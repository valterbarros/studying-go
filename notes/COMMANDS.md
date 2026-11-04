## Command line

[Readme](../README.md) / Command line

```bash
// Remove not used modules from go.mod

go mod tidy
```

```bash
// Build app and send to go root folder

go install
```

```bash
// Build the app but don't install the packages

go build
```

```bash
// Build the app and install the packages
// get install path go list -f '{{.Target}}'

go install
```

```bash
// Execute tools like linters stringer etc
// install with go get -tool [name]
go tool [name]
```

```bash
// Updates a dependency
go get [name]
```


```bash
// run app

go run [name]
```

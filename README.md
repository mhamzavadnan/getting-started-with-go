# Getting Started with Go

A tutorial-based Go application following the official [Go Getting Started Guide](https://go.dev/doc/tutorial/getting-started).

## Table of Contents

- [Description](#description)
- [Prerequisites](#prerequisites)
- [What You'll Learn](#what-youll-learn)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Understanding the Code](#understanding-the-code)
- [Working with External Packages](#working-with-external-packages)
- [Usage](#usage)
- [Development](#development)
- [Learning Resources](#learning-resources)

## Description

This project demonstrates fundamental Go programming concepts and best practices, including:
- Setting up a Go module with `go.mod`
- Writing and organizing Go code
- Working with external packages (using `rsc.io/quote` as an example)
- Managing dependencies with Go modules
- Project structure and build automation

The application imports the `rsc.io/quote` package to display an inspirational message about Go's communication philosophy.

## Prerequisites

- **Go 1.25.5 or higher** - [Download and install Go](https://go.dev/doc/install)
- **A code editor** - VSCode (free), GoLand (paid), or Vim (free) recommended
- **A command terminal** - PowerShell/cmd on Windows, any terminal on Linux/Mac
- **Git** - For version control (optional but recommended)
- **Some programming experience** - Basic understanding of functions and programming concepts

## What You'll Learn

By exploring this project, you will:

1. ✅ Install Go and set up your development environment
2. ✅ Write your first Go program
3. ✅ Use the `go` command to run and build code
4. ✅ Create and manage a Go module with `go.mod`
5. ✅ Import and use external packages from the Go ecosystem
6. ✅ Understand Go's package system and project organization
7. ✅ Work with dependency tracking and module authentication

## Project Structure

```
getting-started-with-go/
├── cmd/
│   └── go-practice/
│       └── main.go          # Main application entry point
├── internal/                 # Internal packages (private to this project)
├── tests/                    # Test files
├── bin/                      # Compiled binaries
├── go.mod                    # Go module dependencies
├── go.sum                    # Dependency checksums
├── Makefile                  # Build automation
└── README.md                 # This file
```

## Getting Started

### Step 1: Install Go

If you haven't already, [download and install Go](https://go.dev/doc/install) for your operating system.

Verify the installation:

```bash
go version
```

You should see output like: `go version go1.25.5 windows/amd64`

### Step 2: Clone This Repository

```bash
git clone https://github.com/mhamzavadnan/getting-started-with-go.git
cd getting-started-with-go
```

### Step 3: Understand the Module

This project uses a Go module for dependency management. The `go.mod` file defines:

- **Module path**: `github.com/mhamzavadnan/go-practice`
- **Go version**: `1.25.5`
- **Dependencies**: `rsc.io/quote v1.5.2`

The `go.mod` file tracks modules that provide packages your code imports. This file stays with your code, including in source control.

### Step 4: Download Dependencies

Go will automatically download dependencies when you run or build the code. To explicitly download them:

```bash
go mod download
```

To add new dependencies or clean up unused ones:

```bash
go mod tidy
```

## Understanding the Code

The main application is located in [`cmd/go-practice/main.go`](cmd/go-practice/main.go):

```go
package main

import "fmt"
import "rsc.io/quote"

func main() {
    fmt.Println(quote.Go())
}
```

### Code Breakdown:

1. **`package main`** - Declares the main package. The main package is special in Go - it defines an executable program.

2. **`import "fmt"`** - Imports the `fmt` package from the standard library for formatted I/O operations.

3. **`import "rsc.io/quote"`** - Imports an external package that provides inspirational quotes.

4. **`func main()`** - The main function is the entry point of the program. When you run a Go program, the main function executes automatically.

5. **`quote.Go()`** - Calls the `Go()` function from the quote package, which returns:
   > "Don't communicate by sharing memory, share memory by communicating."

## Working with External Packages

This project demonstrates how to find and use external packages:

### Finding Packages

1. Visit [pkg.go.dev](https://pkg.go.dev) - Go's package discovery site
2. Search for packages (e.g., "quote")
3. Review documentation and available functions
4. Note the module path (e.g., `rsc.io/quote`)

### Adding Packages to Your Code

1. Import the package in your Go file:
   ```go
   import "rsc.io/quote"
   ```

2. Use functions from the package:
   ```go
   fmt.Println(quote.Go())
   ```

3. Run `go mod tidy` to download and add the dependency:
   ```bash
   go mod tidy
   ```

Go will:
- Locate and download the module
- Add it to `go.mod` as a requirement
- Create/update `go.sum` for authentication
- Download the latest compatible version by default

## Usage

### Running the Application

The simplest way to run the program:

```bash
go run cmd/go-practice/main.go
```

**Expected Output:**
```
Don't communicate by sharing memory, share memory by communicating.
```

The `go run` command compiles and runs the program in one step. This is perfect for development and testing.

### Building the Application

To build the executable:

```bash
go build -o bin/go-practice cmd/go-practice/main.go
```

Then run the compiled binary:

```bash
# On Windows
.\bin\go-practice.exe

# On Linux/macOS
./bin/go-practice
```

### Using Makefile

If you have Make installed, you can use the Makefile for common tasks:

```bash
# Build the application
make build

# Run the application
make run

# Run tests
make test

# Clean build artifacts
make clean
```

## Dependencies

This project uses the following external dependencies:

- **[rsc.io/quote](https://pkg.go.dev/rsc.io/quote) v1.5.2** - Provides inspirational Go-related quotes
  - This package demonstrates how to import and use external modules
  - It's part of the official Go tutorial for learning dependency management
  
View all dependencies in [`go.mod`](go.mod). The `go.sum` file contains checksums for module authentication.

## Development

### Adding New Dependencies

To add a new dependency:

```bash
go get <package-name>
```

To tidy up dependencies and remove unused ones:

```bash
go mod tidy
```

### Running Tests

```bash
# Run all tests
go test ./...

# Run tests with verbose output
go test -v ./...

# Run tests with coverage
go test -cover ./...
```

### Code Formatting

Format your code using:

```bash
go fmt ./...
```

### Code Linting

Run static analysis:

```bash
go vet ./...
```

## Learning Resources

Continue your Go journey with these official resources:

### Official Documentation
- 📘 [Go Getting Started Tutorial](https://go.dev/doc/tutorial/getting-started) - The official tutorial this project follows
- 📘 [A Tour of Go](https://go.dev/tour/) - Interactive introduction to Go
- 📘 [Go Documentation](https://go.dev/doc/) - Complete Go documentation
- 📘 [Effective Go](https://go.dev/doc/effective_go) - Tips for writing clear, idiomatic Go
- 📘 [Go by Example](https://gobyexample.com/) - Hands-on introduction using annotated examples

### Package Discovery
- 🔍 [pkg.go.dev](https://pkg.go.dev) - Search and browse Go packages
- 📚 [Standard Library](https://pkg.go.dev/std) - Go's built-in packages

### Go Modules
- 📦 [Go Modules Reference](https://go.dev/ref/mod) - Complete guide to Go modules
- 📦 [Managing Dependencies](https://go.dev/doc/modules/managing-dependencies) - Dependency management guide

### Next Steps
After completing this tutorial, try:
- 🚀 [Create a Go Module](https://go.dev/doc/tutorial/create-module) - Build your own reusable package
- 🚀 [Getting Started with Multi-Module Workspaces](https://go.dev/doc/tutorial/workspaces) - Work with multiple modules
- 🚀 [Developing a RESTful API with Go and Gin](https://go.dev/doc/tutorial/web-service-gin) - Build a web service

## Contributing

This is a learning project following the official Go tutorial. Contributions are welcome!

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Ideas for Contributions

- Add more examples using different packages
- Improve documentation and explanations
- Add tests for the application
- Create additional learning exercises

## License

This is a practice project for learning Go, following the official [Go Getting Started Tutorial](https://go.dev/doc/tutorial/getting-started).

## Author

Created by [mhamzavadnan](https://github.com/mhamzavadnan) as part of learning Go programming.

---

## Quick Reference

### Common Go Commands

```bash
# Run the program
go run cmd/go-practice/main.go

# Build an executable
go build -o bin/go-practice cmd/go-practice/main.go

# Download dependencies
go mod download

# Add missing and remove unused modules
go mod tidy

# Verify dependencies
go mod verify

# Run tests
go test ./...

# Format code
go fmt ./...

# Run static analysis
go vet ./...

# View Go environment
go env

# Get help
go help
```

### Useful Resources

| Resource | Description |
|----------|-------------|
| [go.dev](https://go.dev) | Official Go website |
| [pkg.go.dev](https://pkg.go.dev) | Package documentation |
| [Go Playground](https://go.dev/play/) | Try Go in your browser |
| [Go Blog](https://go.dev/blog/) | Official Go blog |
| [Stack Overflow](https://stackoverflow.com/questions/tagged/go) | Go questions and answers |

---

**Happy Coding! \ud83d\ude80**

*"Don't communicate by sharing memory, share memory by communicating."* - Go Proverb

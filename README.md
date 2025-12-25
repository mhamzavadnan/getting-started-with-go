# Getting Started with Go

A comprehensive Go application for learning and practicing Go programming fundamentals.

## Description

This project is designed as a learning resource for Go developers, demonstrating best practices in:
- Project structure and organization
- External package management with Go modules
- Build automation with Makefiles
- Testing and development workflows

The application uses the `rsc.io/quote` package to display inspirational quotes, serving as a practical example of dependency management in Go.

## Prerequisites

- Go 1.25.5 or higher
- Git (for version control)

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

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/mhamzavadnan/getting-started-with-go.git
   cd getting-started-with-go
   ```

2. Download dependencies:
   ```bash
   go mod download
   ```

## Usage

### Running the Application

To run the application directly:

```bash
go run cmd/go-practice/main.go
```

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

- [rsc.io/quote](https://pkg.go.dev/rsc.io/quote) - A package for inspirational quotes

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

- [Official Go Documentation](https://go.dev/doc/)
- [Go by Example](https://gobyexample.com/)
- [Effective Go](https://go.dev/doc/effective_go)
- [Go Modules Reference](https://go.dev/ref/mod)

## Contributing

This is a learning project. Feel free to:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This is a practice project for learning Go.

## Author

[mhamzavadnan](https://github.com/mhamzavadnan)

---

**Happy Coding! 🚀**

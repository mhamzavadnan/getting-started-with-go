# go-practice

A simple Go application for learning and practicing Go programming fundamentals.

## Description

This project is a basic Go application that demonstrates the use of external packages and Go module management. It uses the `rsc.io/quote` package to display a greeting message.

## Prerequisites

- Go 1.25.5 or higher
- Git (for version control)

## Project Structure

```
go-practice/
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
   git clone https://github.com/mhamzavadnan/go-practice.git
   cd go-practice
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

## Dependencies

- [rsc.io/quote](https://pkg.go.dev/rsc.io/quote) - A package for inspirational quotes

## Development

### Adding New Dependencies

To add a new dependency:

```bash
go get <package-name>
```

### Running Tests

```bash
go test ./...
```

## License

This is a practice project for learning Go.

## Author

[mhamzavadnan](https://github.com/mhamzavadnan)

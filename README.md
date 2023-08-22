# Go-Python-Interoperability

# Running a Go Function from a Python Script

This README provides step-by-step instructions on how to run a Go function from a Python script. We'll create a minimal Go project with a function and a Python script to execute that function.

## Prerequisites

Before proceeding, make sure you have the following installed on your system:

- Go programming language ([Download Go](https://golang.org/))
- Python 3

## Steps

### 1. Create a New Go File

#### 1.1. Create a new Go file, for example, `test.go`, using a text editor or an integrated development environment (IDE).

#### 1.2. Add the following Go code to `test.go`:

    ```go
    package main

    import "fmt"

    func GolangFunction1() {
        fmt.Println("Running Golang Function 1")
    }

    func main() {
        fmt.Println("Hello from main function")
        GolangFunction1()
    }

### 2. Create a New Go File

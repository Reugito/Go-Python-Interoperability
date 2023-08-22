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

Now, let's compile the Go file into an executable binary.

#### 2.1. Open a terminal and navigate to the directory containing test.go.

    cd /path/to/your/directory
            
#### 2.2. Compile the Go code

Run the following command to compile the Go code into an executable binary named mytestapp:

    go build -o mytestapp test.go
    
The -o flag specifies the output file name (mytestapp in this case), and test.go is the source file.

#### 3. Create a Python Script
    
Now, we'll create a Python script that will call the Go function.

### 3.1. Create a New Python File

Create a new Python file, for example, test.py, using a text editor or an integrated development environment         (IDE).

### 3.2. Add Python Code

 Add the following Python code to test.py:
 

    import subprocess

    def run_go_function(function_name):
        try:
            # Execute the Go binary and capture its output
            result = subprocess.check_output(['./mytestapp', function_name], stderr=subprocess.STDOUT, text=True)

            # Print the output
            print(result)
        except subprocess.CalledProcessError as e:
            # Handle any errors that occur during execution
            print(f"Error: {e}")

    if __name__ == "__main__":
        # Call your Go functions here
        run_go_function("GolangFunction1")


#### 4. Run the Python Script

Now, let's run the Python script to call the Go function.

### 4.1. Open a Terminal

Open a terminal and navigate to the directory containing test.py and the mytestapp binary.

### 4.2. Run the Python Script

Run the Python script using the following command:

    python3 test.py
    
The Python script will execute GolangFunction1 from the Go binary and print its output.


#### Troubleshooting

If you encounter permission issues, ensure that the Go binary (mytestapp) has execute permission. You can use the chmod command to set the execute permission:

    chmod +x mytestapp
    
If you encounter issues with function execution, double-check the function name in both your Go code and Python script to ensure they match.

If you need to call a different Go function, modify the Python script to pass the appropriate function name as an argument to the Go binary.

That's it! You have successfully run a Go function from a Python script.
        



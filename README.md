# [Z]ZIG PROGRAMMING LANGUAGE

## ZIG Overview

Zig is a general-purpose programming language designed for robustness, optimal performance, and simplicity. It emphasizes low-level control, safety, and minimal runtime overhead. Zig is particularly useful for systems programming, embedded systems, and game development.

## How ZIG Runs

Zig compiles source code into executable binaries. It provides a simple and deterministic build system, allowing developers to manage their projects without external dependencies. Zig includes built-in tools for testing, formatting, and package management, making it an efficient choice for modern development workflows.

## Choosing an IDE

Many developers choose to write Zig code using a basic text editor, but more specialized integrated development environments (IDEs) can enhance productivity. Some of the most popular choices include:

- Visual Studio Code
- Code::Blocks
- Eclipse
- NetBeans

### Preferred IDE

My preferred IDE is Visual Studio Code due to its rich ecosystem of extensions, lightweight design, and ease of use.

## Install Zig on Windows 11 (64-BIT)

Follow these steps to install Zig on a Windows 11 (64-bit) system:

1. Visit the [Zig download page](https://ziglang.org/download/).
2. Download the program for your OS version (e.g., `zig-windows-x86_64`).
3. Extract the contents of the downloaded file.
4. Rename and move the folder to `D:\ProgramFiles\zig-windows-x86_64` for better organization.

## Setting Up Zig Environment Variable

Set up the environment variable for Zig by running the following command in PowerShell:

```powershell
[Environment]::SetEnvironmentVariable("Path", [Environment]::GetEnvironmentVariable("Path", "Machine") + ";D:\ProgramFiles\zig-windows-x86_64", "Machine")
```

This ensures that Zig is accessible from the command line.

## Steps to Run a Test Project: "Hello World!"

If the installation is completed correctly, you should be able to invoke the Zig compiler from your shell. Let's create and run your first Zig program:

1. Navigate to your projects directory and initialize a Zig project:

    ```sh
    mkdir hello-world
    cd hello-world
    zig init
    ```

2. This command creates the following files:

    ```sh
    info: created build.zig
    info: created build.zig.zon
    info: created src/main.zig
    info: created src/root.zig
    info: see `zig build --help` for a menu of options
    ```

3. Modify `src/main.zig` to include the following code:

    ```zig
    test "simple test" {
        std.debug.print("Running simple test...\n", .{});
        // existing code here ...
    }

    test "use other module" {
        std.debug.print("Running use other module test...\n", .{});
        // existing code here ...
    }

    test "fuzz example" {
        std.debug.print("Running fuzz example test...\n", .{});
        // existing code here ...
    }

    const std = @import("std");

    /// This imports the separate module containing `root.zig`. Take a look in `build.zig` for details.
    const lib = @import("hello-world_lib");

    test "print hello world" {
        std.debug.print("Hello World!\n", .{});
    }
    ```

4. Compile and run the project:

    ```powershell
    PS D:\ZigProjects\hello-world> zig run ./src/main.zig
    All your codebase are belong to us.
    Run `zig build test` to run the tests.
    PS D:\ZigProjects\hello-world> zig build test
    test
    └─ run test stderr
    Running simple test...
    Running use other module test...
    Running fuzz example test...
    Hello World!
    ```

## Explanation of Steps

1. **Project Initialization**: The `zig init` command initializes a new Zig project, creating necessary files like `build.zig`, `build.zig.zon`, `src/main.zig`, and `src/root.zig`.
2. **Code Modification**: Test cases are added to `main.zig` to verify different functionalities. The `std.debug.print` statements are used to print messages to the terminal, helping confirm that the tests are being executed.
3. **Running the Project**: The `zig run ./src/main.zig` command compiles and runs the main Zig file, printing specified messages to the terminal.
4. **Running Tests**: The `zig build test` command runs the defined test cases, printing debug messages and verifying the expected outcomes.

## Conclusion

This guide provides a comprehensive overview of setting up and running a simple Zig project with test cases. By following these steps, you can:

- Initialize a new Zig project.
- Modify the code to include test cases.
- Run the project and tests to verify its functionality.

This process serves as a foundation for exploring more advanced features and capabilities of the Zig programming language.


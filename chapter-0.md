---
title: "Chapter 0 - Getting Started"
weight: 1
date: 2020-08-14 13:04:30
description: "Ziglearn - A Guide / Tutorial for the zig programming language. Install and get started with ziglang here."
---

# Welcome

[Zig](https://ziglang.org) is a general-purpose programming language and toolchain for maintaining __robust__, __optimal__, and __reusable__ software.

Warning: the latest major release is 0.6 - Zig is still pre-1.0; usage in production is still not recommended and you may run into compiler bugs.

To follow this guide, we assume you have:
   * Prior experience programming
   * Some understanding of low-level programming concepts

Knowing a language like C, C++, Rust, Go, Pascal or similar will be helpful for following this guide. You should have an editor, terminal and internet connection available to you. This guide is unofficial and unaffiliated with the project, and is designed to be read in order from the start.

# Installation

**This guide assumes you're using a master build** of Zig as opposed to the latest major release, which means downloading a binary from the site or compiling from source; **the version of Zig in your package manager is likely outdated**. This guide does not support the 0.6 build of Zig.

1.  Download and extract a prebuilt master binary of zig from:
```
https://ziglang.org/download/
```

2. Add zig to your path
   - linux, macos, bsd

      Add the location of your zig binary to your `PATH` environment variable. For an installation, add `export PATH=$PATH:~/zig/zig` or similar to your `/etc/profile` (system-wide) or `$HOME/.profile`. If these changes do not apply immediately, run the line from your shell.
   - windows

      a) System wide (admin powershell)

      ```powershell
      [Environment]::SetEnvironmentVariable(
         "Path",
         [Environment]::GetEnvironmentVariable("Path", "Machine") + ";C:\your-path\zig-windows-x86_64-your-version",
         "Machine"
      )
      ```

      b) User level (powershell)

      ```powershell
      [Environment]::SetEnvironmentVariable(
         "Path",
         [Environment]::GetEnvironmentVariable("Path", "User") + ";C:\your-path\zig-windows-x86_64-your-version",
         "User"
      )
      ```

      Close your terminal and create a new one.

3. Verify your install with `zig version`. The output should be `0.6.0+` followed by some hex digits.

4. (optional, third party) For completions and go-to-definition in your editor, install the Zig Language Server from:
```
https://github.com/zigtools/zls/
```

# Hello World

Create a file called `main.zig`, with the following contents:

```zig
const std = @import("std");

pub fn main() void {
    std.debug.print("Hello, {}!\n", .{"World"});
}
```
###### (note: make sure your file is using spaces for indentation, LF line endings and UTF-8 encoding!)

Use `zig run main.zig` to build and run it. In this example `Hello, World!` will be written to stderr, and is assumed to never fail.
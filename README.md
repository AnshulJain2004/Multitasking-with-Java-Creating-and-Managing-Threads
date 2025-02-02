# Multitasking with Java: Creating and Managing Threads

This repository demonstrates how to create and manage threads in Java through two different approaches:

1. **By extending the `Thread` class**  
2. **By implementing the `Runnable` interface**

## Table of Contents
- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
  - [Extending `Thread` Class](#extending-thread-class)
  - [Implementing `Runnable` Interface](#implementing-runnable-interface)
- [Usage](#usage)
  - [Running the Demo](#running-the-demo)
- [Prerequisites](#prerequisites)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction

In Java, there are multiple ways to create and manage threads. This repository contains four classes that showcase the two most common techniques:

- **Using the `Thread` class**  
- **Using the `Runnable` interface**  

Both examples illustrate:
- How to start threads using the `start()` method
- How to pause a thread using `sleep()`
- How to wait for threads to complete using the `join()` method

---

## Project Structure

The files in this repository are organized as follows:

```
.
├── src
│   └── main
│       └── java
│           └── org
│               └── example
│                   ├── CustomRunnable.java
│                   ├── CustomThread.java
│                   ├── ThreadDemo.java
│                   └── ThreadDemo1.java
└── README.md
```

1. **CustomThread.java**  
   - Defines a class `CustomThread` that extends `Thread`.  
   - Overrides the `run()` method to simulate work (countdown) and sleeping.

2. **CustomRunnable.java**  
   - Defines a class `CustomRunnable` that implements `Runnable`.  
   - Implements the `run()` method with similar behavior as `CustomThread`.

3. **ThreadDemo.java**  
   - Demonstrates how to create and start threads by directly extending the `Thread` class.  
   - Uses `join()` to wait for the threads to finish before continuing the main thread execution.

4. **ThreadDemo1.java**  
   - Demonstrates how to create and start threads by implementing the `Runnable` interface.  
   - Also uses `join()` to coordinate the completion of threads.

---

## How It Works

### Extending `Thread` Class
- You create a subclass of `Thread` (`CustomThread`) and override the `run()` method.
- In the `ThreadDemo` class, you instantiate `CustomThread` objects and call `start()` on them.  
- This approach is straightforward but prevents you from extending any other class since Java only supports single inheritance.

### Implementing `Runnable` Interface
- You create a class (`CustomRunnable`) that implements the `Runnable` interface.
- In the `ThreadDemo1` class, you instantiate `CustomRunnable` objects and pass them to new `Thread` objects, then call `start()`.
- This approach is more flexible because you can still extend another class if needed.

Both classes showcase:
- **Thread creation** via `start()`
- **Thread sleeping** via `Thread.sleep(milliseconds)`
- **Waiting for thread completion** with `join()`
- **Handling interruptions** with `InterruptedException`

---

## Usage

### Running the Demo

1. **Clone or download this repository**  
   ```bash
   git clone https://github.com/your-username/Multitasking-with-Java-Creating-and-Managing-Threads.git
   ```
2. **Open the project in your IDE** (e.g., IntelliJ, Eclipse, VSCode) or navigate to the project root directory from your command line.

3. **Compile and Run**:
   - Ensure you have a Java JDK (version 8 or above) installed.
   - You can run the demos by executing:
     ```bash
     # For ThreadDemo
     cd src/main/java/org/example
     javac ThreadDemo.java CustomThread.java
     java org.example.ThreadDemo

     # For ThreadDemo1
     javac ThreadDemo1.java CustomRunnable.java
     java org.example.ThreadDemo1
     ```

   Alternatively, run them directly from your IDE by locating the `main()` method inside **ThreadDemo** or **ThreadDemo1** and selecting **Run**.

---

## Prerequisites

- **Java JDK 8 or higher**  
  Make sure Java is installed and configured in your `PATH` environment variable.

---

## Contributing

Contributions are welcome! If you’d like to contribute:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and test thoroughly.
4. Submit a pull request describing your changes.

---

## License

This project is licensed under the [MIT License](LICENSE).  
Feel free to use and modify the code as you wish.

---

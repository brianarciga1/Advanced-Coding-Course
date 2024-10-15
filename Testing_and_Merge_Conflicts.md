## Lab: Testing and Resolving Merge Conflicts in Swift (Terminal-based)

### Objective

In this lab, you and your partner will work together to create a simple counter program in Swift. Each of you will implement different parts of the program and write unit tests. You'll also intentionally introduce and resolve a merge conflict to understand how to handle them effectively.

### Prerequisites

- Basic knowledge of Git (creating repositories, branching, committing)
- Familiarity with Swift basics (functions, classes)
- Terminal/command-line skills
- Swift Package Manager (SPM) installed

---

### Step 1: **Set Up the Git Repository**

1. One partner will create a new Git repository on GitHub. The other partner should clone the repository onto their machine.
   
   **Commands**:
   - Partner 1:
     ```bash
     git init
     git remote add origin <repo-url>
     git push -u origin main
     ```
   - Partner 2:
     ```bash
     git clone <repo-url>
     ```

2. Navigate into the repository:
   ```bash
   cd repository-name
   ```

### Step 2: **Create a Swift Package**

1. **Initialize the Swift package**:
   
   Inside the repository directory, initialize a Swift package using Swift Package Manager (SPM):

   ```bash
   swift package init --type executable
   ```

Type the `ls` command to see your files. You should have a new `Package.swift` file. Ensure `Package.swift` has a test target
First, open your `Package.swift` file and ensure it has a test target. The `Package.swift` file should look something like this:

```swift
import PackageDescription

let package = Package(
    name: "repository-name",
    products: [
        .library(
            name: "repository-name",
            targets: ["repository-name"]),
    ],
    dependencies: [
        // List dependencies here.
    ],
    targets: [
        .target(
            name: "repository-name",
            dependencies: []),
        .testTarget(
            name: "repository-nameTests",
            dependencies: ["repository-name"]),
    ]
)
```

Make sure the testTarget is included with the correct naming!

2. **Check Directory Structure**:
   After initializing, your repository should look like this:

   ```bash
   .
   ├── Package.swift
   ├── README.md
   ├── Sources/
   │   └── repository-name/
   │       └── main.swift
   └── Tests/
       └── repository-nameTests/
           └── repository-nameTests.swift
   ```

   - **Package.swift**: This is the file that defines your package and its dependencies.
   - **Sources/**: This folder contains your application code.
   - **Tests/**: This folder contains your unit test files.

### Step 3: **Implement the Counter Program**

1. **Edit `main.swift`**:
   
   Add a simple counter to the `main.swift` file.

   ```swift
   class Counter {
       var value: Int = 0

       func increment() {
           value += 1
       }

       func decrement() {
           value -= 1
       }
   }

   // Code to test the Counter
   var counter = Counter()
   counter.increment()
   print("Counter value after increment: \(counter.value)")
   ```

2. **Commit the changes**:
   
   Partner 1 should commit the changes:

   ```bash
   git add Sources/repository-name/main.swift
   git commit -m "Add basic Counter implementation"
   git push origin main
   ```

### Step 4: **Create a Feature Branch and Add Tests**

1. **Create a new branch** for tests. Each partner will create their own branch:
   
   - Partner 1:
     ```bash
     git checkout -b feature-tests-1
     ```

   - Partner 2:
     ```bash
     git checkout -b feature-tests-2
     ```

2. **Add tests to `repository-nameTests.swift`**:

   Each partner will add their tests in the `Tests/repository-nameTests/CounterTests.swift` file.

   - **Partner 1’s Tests**:

     ```swift
     import XCTest
     @testable import repository_name

     final class CounterTests: XCTestCase {
         func testIncrement() {
            var counter = Counter()
            counter.increment()
            print("Counter value after increment: \(counter.value)")  // Print the counter value
            XCTAssertEqual(counter.value, 1, "Counter increment failed")
          }
     }
     ```

   - **Partner 2’s Tests**:

     ```swift
     import XCTest
     @testable import repository_name

     final class CounterTests: XCTestCase {
         func testDecrement() {
            var counter = Counter()
            counter.decrement()
            print("Counter value after decrement: \(counter.value)")  // Print the counter value
          XCTAssertEqual(counter.value, -1, "Counter decrement failed")
          }
     }
     ```

3. **Commit and push**:
   
   Each partner should commit their test code and push to their feature branch.

   - Partner 1:
     ```bash
     git add Tests/repository-nameTests/CounterTests.swift
     git commit -m "Add increment test"
     git push origin feature-tests-1
     ```

   - Partner 2:
     ```bash
     git add Tests/repository-nameTests/CounterTests.swift
     git commit -m "Add decrement test"
     git push origin feature-tests-2
     ```

### Step 5: **Introduce a Merge Conflict**

1. Both partners will now try to merge their feature branches into the `main` branch, which will create a merge conflict in `CounterTests.swift`.

   - Partner 1:
     ```bash
     git checkout main
     git pull origin main
     git merge feature-tests-1
     ```

   - Partner 2:
     ```bash
     git checkout main
     git pull origin main
     git merge feature-tests-2
     ```

### Step 6: **Resolve the Merge Conflict**

1. When Partner 2 tries to merge, there will be a conflict in `CounterTests.swift`.

   The conflict markers in the file will look something like this:

   ```text
   <<<<<<< HEAD
   func testIncrement() {
        var counter = Counter()
        counter.increment()
        print("Counter value after increment: \(counter.value)")  // Print the counter value
        XCTAssertEqual(counter.value, 1, "Counter increment failed")
    }
   =======
   func testDecrement() {
        var counter = Counter()
        counter.decrement()
        print("Counter value after decrement: \(counter.value)")  // Print the counter value
        XCTAssertEqual(counter.value, -1, "Counter decrement failed")
    }
   >>>>>>> feature-tests-2
   ```

2. **Resolve the conflict** by keeping both changes and removing the conflict markers:

   ```swift
   func testIncrement() {
        var counter = Counter()
        counter.increment()
        print("Counter value after increment: \(counter.value)")  // Print the counter value
        XCTAssertEqual(counter.value, 1, "Counter increment failed")
    }

   func testDecrement() {
        var counter = Counter()
        counter.decrement()
        print("Counter value after decrement: \(counter.value)")  // Print the counter value
        XCTAssertEqual(counter.value, -1, "Counter decrement failed")
    }
   ```

3. **Commit the merged changes**:

   ```bash
   git add Tests/repository-nameTests/CounterTests.swift
   git commit -m "Resolved merge conflict in CounterTests"
   git push origin main
   ```

### Step 7: **Run and Demonstrate the Tests**

1. After resolving the conflict and pushing the merged code, run the tests using Swift Package Manager (SPM).

   **From the root directory** of your project (where `Package.swift` is located), run:

   ```bash
   swift test
   ```

2. If everything is set up correctly, you should see the tests passing:

   ```bash
   Test Suite 'All tests' started at 2024-10-14 10:00:00.
  Test Suite 'repository_nameTests' started at 2024-10-14 10:00:00.
  Test Case 'CounterTests.testIncrement' started.
  Counter value after increment: 1
  Test Case 'CounterTests.testIncrement' passed (0.001 seconds).
  Test Case 'CounterTests.testDecrement' started.
  Counter value after decrement: -1
  Test Case 'CounterTests.testDecrement' passed (0.001 seconds).
  Test Suite 'repository_nameTests' passed at 2024-10-14 10:00:00.
  Executed 2 tests, with 0 failures in 0.002 seconds
   ```

---

### Final Notes:

- **Handling Merge Conflicts**: Merge conflicts are a natural part of collaborative development. Learning how to resolve them is a crucial skill. This lab simulates a simple conflict resolution process.
  
- **Unit Testing**: Unit tests ensure the integrity of your code. Swift Package Manager makes it easy to add and run tests from the terminal.

---

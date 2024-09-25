# **Collaborative Calculator Lab**

## **Objective**
In this lab, your group will:
- Create a GitHub repository.
- Use branches to collaboratively build a simple calculator program in Swift.
- The calculator will perform addition, subtraction, multiplication, division, exponentiation, and find the remainder.

## **Requirements**
- GitHub account
- Xcode installed on your Mac
- Group of 2-3 students (Partners)

---

## **1. Set Up Your GitHub Repository**

### **Step 1: Create the Repository**
1. One partner should create a new repository on GitHub. 
   - Navigate to [GitHub](https://github.com/) and create a new repository named something like `GroupCalculator`.
   - Initialize the repository with a **README** file.
   - Share the repository with your partners by inviting them as collaborators under **Settings** > **Collaborators**.
   
### **Step 2: Clone the Repository**
1. Each partner should clone the repository to their local machine.
   - Open your terminal and run the following command:
     ```bash
     git clone https://github.com/your-group/GroupCalculator.git
     ```
   - Navigate into the cloned directory:
     ```bash
     cd GroupCalculator
     ```

### **Step 3: Create Your Branch**
1. Each partner must create their own branch for their section of the calculator.
   - Use this command to create and switch to your branch:
     ```bash
     git checkout -b <branch-name>
     ```
     Example:
     ```bash
     git checkout -b add-subtract
     ```
   - Push your branch to GitHub:
     ```bash
     git push origin <branch-name>
     ```

---

## **2. Writing the Calculator Program**

### **Calculator Requirements**
The program will allow users to select an operation (add, subtract, multiply, divide, exponent, remainder) and then enter two numbers. Based on the operation chosen, it will perform the calculation and return the result.

### **Step 1: Common Code (Main Menu)**

Each team needs to include the following code to display the menu in their `calculator.swift` file:
```swift
import Foundation

// Menu function to display options to the user
func showMenu() {
    print("""
    Select an operation:
    1: Add
    2: Subtract
    3: Multiply
    4: Divide
    5: Exponent
    6: Remainder
    """)
}

showMenu() //displays menu

```

The code should prompt users to enter their two numbers like this:
<img width="1048" alt="image" src="https://github.com/user-attachments/assets/dc5c0a21-935d-40a4-9baa-eb585729180e">



### **Step 2: Partner 1 - Addition and Subtraction**
1. On your branch, implement the **addition** and **subtraction** functions:
   ```swift
   func add(_ a: Double, _ b: Double) -> Double {
       return a + b
   }

   func subtract(_ a: Double, _ b: Double) -> Double {
       return a - b
   }

   // In the switch statement:
   case 1:
       print("Result: \(add(num1, num2))")
   case 2:
       print("Result: \(subtract(num1, num2))")
   ```
2. Commit your changes:
   ```bash
   git add calculator.swift
   git commit -m "Added addition and subtraction functions"
   ```

### **Step 3: Partner 2 - Multiplication and Division**
1. On your branch, implement the **multiplication** and **division** functions:
   ```swift
   func multiply(_ a: Double, _ b: Double) -> Double {
       return a * b
   }

   func divide(_ a: Double, _ b: Double) -> Double {
       guard b != 0 else {
           print("Cannot divide by zero!")
           return 0
       }
       return a / b
   }

   // In the switch statement:
   case 3:
       print("Result: \(multiply(num1, num2))")
   case 4:
       print("Result: \(divide(num1, num2))")
   ```
2. Commit your changes:
   ```bash
   git add calculator.swift
   git commit -m "Added multiplication and division functions"
   ```

### **Step 4: Partner 3 - Exponent and Remainder**
1. On your branch, implement the **exponent** and **remainder** functions:
   ```swift
   func exponent(_ base: Double, _ power: Double) -> Double {
       return pow(base, power)
   }

   func remainder(_ a: Double, _ b: Double) -> Double {
       return a.truncatingRemainder(dividingBy: b)
   }

   // In the switch statement:
   case 5:
       print("Result: \(exponent(num1, num2))")
   case 6:
       print("Result: \(remainder(num1, num2))")
   ```
2. Commit your changes:
   ```bash
   git add calculator.swift
   git commit -m "Added exponent and remainder functions"
   ```

---

## **3. Merging and Finalizing the Program**

### **Step 1: Merge Branches**
1. Once all partners have completed their sections, one partner should merge all the branches:
   - Switch to the main branch:
     ```bash
     git checkout main
     ```
   - Merge each branch:
     ```bash
     git merge add-subtract
     git merge multiply-divide
     git merge exponent-remainder
     ```

2. Resolve any merge conflicts (if any) and test the program to ensure all parts are functioning correctly.

3. Push the final version to GitHub:
   ```bash
   git push origin main
   ```

---

## **4. Submitting Your Work**

1. Make sure your final version is pushed to the main branch of the repository.
2. Call your instructor to check that the repository contains:
   - **Working calculator functions** for all operations.
   - **Correctly merged code** from all partners.
3. Your instructor will verify your repository on GitHub.

---

### **Congratulations!**
You've successfully collaborated using GitHub, implemented a simple calculator in Swift, and managed branches to organize your work. 🎉

---

This version is a complete step-by-step lab that includes repository creation, branching, merging, the entire calculator code, and submission instructions for your students.

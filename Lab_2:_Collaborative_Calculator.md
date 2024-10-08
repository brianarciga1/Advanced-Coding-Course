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
## Output
```
Select an operation:
1: Add
2: Subtract
3: Multiply
4: Divide
5: Exponent
6: Remainder

1 //user entered operation 1

Please enter your two numbers:
2
3

Result: 5.0
```
The code should also account for invalid input:
## Output
```
Select an operation:
1: Add
2: Subtract
3: Multiply
4: Divide
5: Exponent
6: Remainder

a //user entered operation 

Invalid input. Please enter valid numbers
```

### **Step 2: Partner 1 - Addition and Subtraction**
1. On your branch, implement the **addition** and **subtraction** functions:
2. Commit your changes:
   ```bash
   git add calculator.swift
   git commit -m "Added addition and subtraction functions"
   ```

### **Step 3: Partner 2 - Multiplication and Division**
1. On your branch, implement the **multiplication** and **division** functions:
2. Commit your changes:
   ```bash
   git add calculator.swift
   git commit -m "Added multiplication and division functions"
   ```

### **Step 4: Partner 3 - Exponent and Remainder**
1. On your branch, implement the **exponent** and **remainder** functions:
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
2. Do not push your executable
3. Call me to check that the repository contains:
   - **Working calculator functions** for all operations.
   - **Correctly merged code** from all partners.
4. I will ask you to demo your code in the terminal

---

### **Congratulations!**
You've successfully collaborated using GitHub, implemented a simple calculator in Swift, and managed branches to organize your work. 🎉

---

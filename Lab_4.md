# Lab Title: AI Search Program in Xcode with GitHub Collaboration

## Objective
Students will work in groups to create an AI search program in Swift using Xcode. They will learn how to structure a project, create a simple search algorithm, and collaborate using GitHub. This lab will help students understand the basics of search functionality and version control.

### Group Size
3 Students

---

## Lab Requirements

### Set Up Xcode Project
- **Create a new Xcode project** with a command-line interface.
- Name the project and save it to a local Git-enabled folder.

### Create a Simple Database
- Implement a basic array of dictionaries representing items with attributes like `name`, `category`, `price`, and `rating`.
- Example data structure:
  ```swift
  let items = [
      ["name": "Laptop", "category": "Electronics", "price": "1200", "rating": "4.5"],
      ["name": "Headphones", "category": "Electronics", "price": "100", "rating": "4.0"]
      // Add more items as needed
  ]

3. Implement Search Functionality
Write a function that allows users to search by criteria like name, category, price range, or rating.
Use a simple search algorithm to filter items based on criteria.
User Interaction
Set up basic user interaction to allow students to enter search criteria in the Xcode console.
Display the search results in a readable format in the console.
Collaborate on GitHub
Each team member should create their own branch on GitHub.
Push changes to GitHub and use pull requests to review and merge code collaboratively.
Steps to Complete the Lab

Step 1: Set Up the Xcode Project
Create the Project:
Open Xcode and select “Create a new Xcode project.”
Choose “Command Line Tool” under macOS and click “Next.”
Name your project (e.g., AISearchProject) and set Language to Swift.
Select a location to save the project and make sure “Create Git repository on my Mac” is checked.
Initialize GitHub Repository:
Open the terminal, navigate to the project folder, and link the project to a new GitHub repository with these commands:
git remote add origin https://github.com/yourusername/AISearchProject.git
git push -u origin main
Verify that your initial project files are on GitHub.
Step 2: Build the Database
As a team, decide on the structure and attributes of your database.
Implement a Swift array of dictionaries to store your items in main.swift.
Example:
let items = [
    ["name": "Laptop", "category": "Electronics", "price": "1200", "rating": "4.5"],
    ["name": "Headphones", "category": "Electronics", "price": "100", "rating": "4.0"]
]
Step 3: Implement Search Functionality
One member can create a Swift function that accepts search parameters and returns matching items.
Example function:
func searchItems(byName name: String, in items: [[String: String]]) -> [[String: String]] {
    return items.filter { $0["name"]?.contains(name) == true }
}
Step 4: User Interaction and Display
Another member should work on handling user input and displaying results. Prompt users to enter search terms and show results in the Xcode console.
Step 5: GitHub Collaboration
Create Branches:
Each team member should create their branch in the terminal or GitHub Desktop:
git checkout -b branch-name
Make Changes and Push:
Commit changes with meaningful messages:
git add .
git commit -m "Added search functionality"
git push origin branch-name
Pull Requests and Merging:
Each member should create a pull request on GitHub to merge their branch into the main branch.
Review code as a team, test each other’s changes, and resolve any conflicts before merging.
Step 6: Finalize and Submit
Ensure the program runs correctly in Xcode.
Push the final version of the project to GitHub.
Submit the GitHub repository link.
Sample Code Snippets

Database Array Example:
let items = [
    ["name": "Laptop", "category": "Electronics", "price": "1200", "rating": "4.5"],
    ["name": "Headphones", "category": "Electronics", "price": "100", "rating": "4.0"],
    ["name": "Coffee Maker", "category": "Kitchen", "price": "30", "rating": "4.2"]
]
Search Function Example:
func searchItems(byCategory category: String, in items: [[String: String]]) -> [[String: String]] {
    return items.filter { $0["category"] == category }
}
User Interaction Example:
print("Enter a category to search for:")
if let input = readLine() {
    let results = searchItems(byCategory: input, in: items)
    print("Results:", results)
}

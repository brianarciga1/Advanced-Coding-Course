Here’s the revised lab manual for performing Git operations using the MacBook terminal instead of Xcode:

---

## **Lab Manual: GitHub Integration and Git Basics on MacBook Terminal**

### **Objective:**
Learn how to use the MacBook terminal to integrate GitHub with your local projects, make commits and pushes, create and manage branches, and handle authentication using a Personal Access Token (PAT).

### **Requirements:**
- GitHub account
- Git installed on your Mac

---

### **1. **Setting Up GitHub Integration with the Terminal**

#### **Step 1: Generate a Personal Access Token (PAT)**

1. **Log in to GitHub:**
   Go to [GitHub](https://github.com/) and log in to your account.

2. **Generate a PAT:**
   - Navigate to [GitHub Settings](https://github.com/settings/tokens).
   - Click on **"Generate new token."**
   - Give your token a descriptive name, select the scopes or permissions you need (e.g., `repo` for full control of private repositories), and generate the token.
   - **Copy the PAT** as you will need it later for authentication.

#### **Step 2: Configure Git to Use the PAT**

1. **Open Terminal:**
   Launch the Terminal app on your Mac.

2. **Set Up Credential Helper:**
   Configure Git to use macOS’s Keychain Access to store your credentials:
   ```bash
   git config --global credential.helper osxkeychain
   ```

3. **Test GitHub Connection:**
   - Run the following command to check your GitHub connection:
     ```bash
     git config --global user.name "Your GitHub Username"
     git config --global user.email "your_email@example.com"
     ```

---

### **2. **Creating a New Repository and Linking It with GitHub**

#### **Step 1: Initialize a Git Repository**

1. **Navigate to Your Project Directory:**
   - Use the `cd` command to move into your project directory:
     ```bash
     cd /path/to/your/project
     ```

2. **Initialize the Repository:**
   - Initialize the project directory as a Git repository:
     ```bash
     git init
     ```

#### **Step 2: Add a Remote Repository**

1. **Link Your Local Repository to GitHub:**
   - Add the remote repository URL (replace `<remote-repository-URL>` with your GitHub repository URL):
     ```bash
     git remote add origin <remote-repository-URL>
     ```

---

### **3. **Making Commits and Pushes**

#### **Step 1: Stage Changes**

1. **Check the Status of Your Repository:**
   - View the status of your working directory:
     ```bash
     git status
     ```

2. **Add Files to the Staging Area:**
   - Stage all changes for commit:
     ```bash
     git add .
     ```
   - Alternatively, specify individual files to add.

#### **Step 2: Commit Changes**

1. **Commit the Staged Changes:**
   - Commit your changes with a descriptive message:
     ```bash
     git commit -m "Your commit message"
     ```

#### **Step 3: Push Changes to GitHub**

1. **Push to the Remote Repository:**
   - Push your committed changes to the GitHub repository:
     ```bash
     git push origin main
     ```
   - Replace `main` with the branch name if different.

---

### **4. **Creating and Managing Branches**

#### **Step 1: Create a New Branch**

1. **Create and Switch to a New Branch:**
   - Create a new branch and switch to it:
     ```bash
     git checkout -b new-branch-name
     ```

#### **Step 2: Switch Between Branches**

1. **List All Branches:**
   - View all existing branches in the repository:
     ```bash
     git branch
     ```

2. **Switch to a Different Branch:**
   - Change to another branch:
     ```bash
     git checkout branch-name
     ```

#### **Step 3: Merge Branches**

1. **Merge Changes from Another Branch:**
   - Switch to the branch you want to merge changes into:
     ```bash
     git checkout main
     ```
   - Merge the other branch into it:
     ```bash
     git merge branch-name
     ```

---

### **5. **Handling Authentication Issues**

#### **If You Encounter Authentication Errors:**

1. **Clear Cached Credentials from Keychain:**
   - Open **Keychain Access** (found in Applications > Utilities).
   - Search for and delete any items related to Git or GitHub.

2. **Re-authenticate with Your PAT:**
   - When pushing or pulling, enter your GitHub username and use the PAT as your password when prompted.

3. **Switch to SSH (Optional):**
   - If you prefer using SSH over HTTPS, generate an SSH key, add it to your GitHub account, and update your remote URL to use SSH.

---

### **Conclusion**

By following this lab manual, you should now be able to integrate GitHub with your local projects using the MacBook terminal, manage commits and pushes, create and manage branches, and handle authentication using a PAT.

If you encounter any issues or have questions, please ask for further assistance.

--- 

This guide should cover everything your students need to work with GitHub from the terminal on their MacBooks! Let me know if you need any further adjustments.

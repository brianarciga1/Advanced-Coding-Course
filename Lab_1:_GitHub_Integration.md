### **Lab Manual: GitHub Integration and Git Basics on MacBook Terminal**

### **Objective:**
By the end of this lab, you will:

Clone a GitHub repository to your terminal.
Create a simple "Hello World" program in Swift.
Push the program back to the GitHub repository.

### **Requirements:**
- GitHub account
- Xcode installed on your Mac

---

### **1. Setting Up GitHub Integration with the Terminal**

#### **Step 1: Generate a Personal Access Token (PAT)**

1. **Log in to GitHub:**
   Go to [GitHub](https://github.com/) and log in to your account.

2. **Generate a Personal access token (PAT):**
   - Navigate to [GitHub Settings](https://github.com/settings/tokens).
   - Click on **"Generate new token."**
   - Select the scopes or permissions you need (e.g., `repo` for full control of private repositories), and generate the token.
   - **Copy the PAT** as you will need it later for authentication so make sure to **SAVE IT**

#### **Step 2: Configure Git to Use the PAT**

1. **Open Terminal:**
   Launch the Terminal app on your Mac

2. **Enter Previously Created Class folder:**
   Open up your previously created AdvancedCoding directory.
   ```bash
   cd AdvancedCoding
   ```

   If you have not already created one, create one then change into it.
   ```bash
   mkdir AdvancedCoding
   cd AdvancedCoding
   ```
3. **Test GitHub Connection:**
   Now since we have Xcode on these laptops they should already have the git packages we need to run our git commands. To check your git version run the following command:
   ```bash
   git --version
   ```
   You should see something like this:
   ```bash
   git version 2.39.3 (Apple Git-146)
   ```
   If not, make sure you have Xcode downloaded. If you still don't see it please let me know!
   
---

### **2. Cloning Your Repository**

#### **CLONE your Advanced Coding Repository from GitHub**

1. **Navigate to your Class Repository:**
   - Go to github and open up your Advanced Coding Repository (The one you created for the class)
   - Click the green <>Code button
   - Copy your HTTPS URL

2. **Navigate back to your Terminal:**
   - Enter the following code using your https url:
     ```bash
     git clone https://github.com/your-username/you-repository.git
     ```
   - Since this is your first time logging in via the terminal, you will be prompted to authenticate:
Username for 'https://github.com': Enter your GitHub username or email.
Password for 'https://github.com': Instead of your GitHub password, you must enter a Personal Access Token (PAT) from earlier

   - You should see output similar to this:
     ```bash
     Cloning into 'Your-Repository'...
     remote: Enumerating objects: 3, done.
     remote: Counting objects: 100% (3/3), done.
     remote: Compressing objects: 100% (2/2), done.
     remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
     Receiving objects: 100% (3/3), done.
     ```
   - Type in the command
     ```bash
        ls
     ```
     and you should see the name of your newly created repository directory
   - Change into your newly created directory
     ```bash
        cd Your-Repository
     ```
---

### **3: Creating and Pushing a "Hello World" Program**

#### Step 1: Create a "Hello World" Program
1. Yes, I know, not another hello world. In the terminal, create and open a new Swift file called `hello_world.swift`:

   ```bash
   vim hello_world.swift
   ```

2. Inside **vim**, press `i` to enter insert mode:

3. Hello world is too easy so lets spice it up a bit, create a loop that prints "hello world" 10 times!

4. Once you've finished typing, press `Esc` to exit insert mode.

5. To save and quit **vim**, type `:wq` and press **Enter**.

#### Step 2: Add and Commit Your Changes
1. Add the new Swift file to the staging area:

   ```bash
   git add hello_world.swift
   ```

2. Commit the changes with a message:

   ```bash
   git commit -m "Added hello_world.swift program"
   ```

3. The terminal should show:

   ```bash
   [main 1a2b3c4] Added hello_world.swift program
    1 file changed, 1 insertion(+)
    create mode 100644 hello_world.swift
   ```

#### Step 3: Push Your Code to GitHub
1. Push the changes to your GitHub repository:

   ```bash
   git push origin main
   ```

2. You might be prompted for your GitHub username and **Personal Access Token** again if it's your first time pushing:

   ```bash
   Username for 'https://github.com': <enter your username>
   Password for 'https://github.com': <enter your PAT>
   ```

3. After successfully pushing, the terminal will output something like:

   ```bash
   Enumerating objects: 5, done.
   Counting objects: 100% (5/5), done.
   Delta compression using up to 8 threads
   Compressing objects: 100% (3/3), done.
   Writing objects: 100% (3/3), 380 bytes | 380.00 KiB/s, done.
   Total 3 (delta 1), reused 0 (delta 0)
   To https://github.com/your-username/hello-world-swift.git
      1a2b3c4..5d6e7f8  main -> main
   ```
---

### **4: Verifying Your Changes on GitHub**

1. Go to your repository on GitHub.
2. You should see your `hello_world.swift` file in the repository, with your commit message.
3. Click on the file to verify that it contains the "Hello, World!" code.
4. At this point call me over to confirm that you pushed your code.
---

### Lab Completion

Congrats!! You have successfully cloned a GitHub repository, created a "Hello World" program in Swift using **vim**, and pushed it back to GitHub. 🎉

---

# Web Development Lab Manual

## Introduction
This lab will guide you through creating a simple HTML and CSS website. You have the freedom to design it however you like, but the structure follows a common layout.

## Understanding the HTML File
- `<head>`: Contains metadata, links to stylesheets, and the title of the webpage.
- `<li>`: Defines a list item within an unordered list (`<ul>`) or ordered list (`<ol>`).
- `<href>`: Attribute in an `<a>` tag that specifies the hyperlink reference.
- `<div>`: A container used to group elements and apply styles.
- `<script>`: Used to include JavaScript files.

## Understanding the CSS File
- `.main`: The main container for the webpage, including the background and overall layout.
- `.navbar`: Defines the navigation bar, containing menu items and the website logo.
- `.menu ul li`: Styles the menu items inside the navigation bar.
- `.content`: Defines the main content area, including headings, paragraphs, and buttons.
- `.form`: Styles the login form with input fields and buttons.

## Steps to Preview HTML/CSS Files Using Xcode

### Create an Xcode Project or Workspace:
1. Open Xcode and create a new project:
   - Go to **File > New > Project**.
   - Choose **Other > Empty**.
   - Click **Next**, name your project, and select a location to save it.
   - Once the project opens, you'll have an empty workspace.

### Add Your HTML and CSS Files:
1. Drag and drop your `index.html` and `style.css` files into the Xcode Project Navigator (on the left side).
2. When prompted, select **Copy items if needed** and click **Finish**.

### Edit Files in Xcode:
- You can now edit your HTML and CSS files directly in Xcode, just like you would in any text editor.

### Locate Your Files for Preview:
1. Right-click the `index.html` file in the Project Navigator and select **Show in Finder**.
2. This will reveal the actual file location on your disk.

### Open Your HTML File in a Browser:
1. In Finder, double-click the `index.html` file to open it in your default browser.
2. Alternatively, right-click it, choose **Open With**, and select your browser of choice (e.g., Chrome, Safari).

### Preview Changes:
- Save your changes in Xcode, and refresh the browser to see the updates.

### Optional: Add a Script to Launch the Browser from Xcode
You can configure Xcode to open the HTML file in a browser with a shortcut:

#### Create a Build Script:
1. Go to **File > New > File**, then select **Shell Script** from the templates.
2. Add the following script to open your `index.html` file in your browser:
   ```bash
   #!/bin/bash
   open path/to/index.html
   ```
3. Save it in your project folder.

#### Run the Script:
- You can run this script from Xcode’s terminal or during a build step.

## Publishing Your Website Using GitHub Pages
1. **Push Your Files to GitHub**
   - Make sure your `index.html` and `style.css` files are in a GitHub repository.
   - Use Git commands in the terminal or GitHub Desktop to push your files.

2. **Enable GitHub Pages**
   - Go to your repository on GitHub.
   - Click on **Settings**.
   - Scroll down to the **Pages** section.
   - Under **Source**, select `main` (or your default branch).
   - Click **Save**.

3. **Access Your Website**
   - After a few minutes, your website will be live at `https://yourusername.github.io/repository-name/`.
   - Share the link with others to view your project online.

# Submission
- Upload your project to a GitHub repository.
- Submit the repository link for evaluation.

Happy Coding!


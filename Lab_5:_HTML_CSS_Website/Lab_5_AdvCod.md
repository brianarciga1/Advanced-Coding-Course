# Web Development Lab Manual

## Overview
In this lab, students will create a personal website using HTML and CSS. They have the freedom to design their website about any topic of their choice.

## Provided Files
- `index.html`: The main HTML file containing the structure of the webpage.
- `style.css`: The CSS file responsible for styling the webpage.

## Understanding the HTML File
The `index.html` file consists of essential elements such as:
- `<!DOCTYPE html>`: Declares the document type as HTML5.
- `<html lang="en">`: Defines the language of the document.
- `<title>`: Sets the title of the webpage.
- `<link rel="stylesheet" href="style.css">`: Links the CSS file for styling.
- `<body>`: Contains all the visible content of the webpage.
- `<div>`: Defines sections of the page.
- `<nav>`: Represents the navigation bar.
- `<ul>` and `<li>`: Used to create navigation menu lists.
- `<a href="#">`: Defines hyperlinks.
- `<h1>`, `<p>`: Headers and paragraphs for text content.
- `<input>`: Used for user input fields in forms.
- `<button>`: Clickable buttons.
- `<head>`: Contains metadata, links to stylesheets, and the title of the webpage.
- `<li>`: Defines a list item within an unordered list (`<ul>`) or ordered list (`<ol>`).
- `<href>`: Attribute in an `<a>` tag that specifies the hyperlink reference.
- `<div>`: A container used to group elements and apply styles.
- `<script>`: Used to include JavaScript files.

## Understanding the CSS File
The `style.css` file is used to style the webpage. Key elements include:
- `* { margin: 0; padding: 0; }`: Resets default margins and padding.
- `.main`: Styles the main container.
- `.navbar`: Styles the navigation bar.
- `.logo`: Defines the appearance of the website logo.
- `.menu ul li a`: Styles the menu links.
- `.content`: Styles the main text content.
- `.form`: Styles the login form section.
- `.btn`: Styles buttons.

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
   - Open the link to view your project online.

## Task
1. Modify `index.html` to personalize the content (customize it however you want!).
2. Customize `style.css` to change colors, fonts, and layout.
3. Add additional elements like images, new sections, or animations.
4. Include atleast ONE animation (youtube and google are good resources)
5. Test your website in a browser.
6. Commit and push your changes to GitHub.
7. Publish your site with GitHub Pages.

# Submission
- Submit your website link in the comments
- Submit a screenshot of your home page
  
Happy Coding!


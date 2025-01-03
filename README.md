# UOR Foundation Official Homepage Repository

**Call to all Old Skool webpage developers!!!**

**In need of plain HTML code!!!**

Welcome to the UOR Foundation Homepage [**Repository**](https://github.com/UOR-Foundation/uor-homepage), the central hub for the development and maintenance of the "OFFICIAL" UOR Foundation [**Homepage**](https://uor-foundation.github.io/uor-homepage/) and [your own UOR website](https://github.com/UOR-Foundation/uor-homepage/tree/homepage/uor-webpages)! 

- The [index.html](./index.html) file **IS** the OFFICIAL Hompage of the UOR Foundation. Located in the same folder as this README.md file.

- The [**Official UOR Foundation Homepage**](https://uor-foundation.github.io/uor-homepage/) serves as the authoritative entry point for everything related to the UOR Foundation, providing you access to all people, projects, content, and source code in the UOR Community.

- The [**Official UOR Foundation Homepage**](https://uor-foundation.github.io/uor-homepage/) is your portal to the webpages in support of the UOR Foundation's mission that you design in accordance with the three (3) policies in this repo.

This repository embraces the philosophy of simplicity, using **pure HTML** to create *form* combined with the power of **GitHub Actions** to create *function*al, elegant, and efficient web pages without relying on JavaScript, CSS, or other additional languages.

## Purpose
This repository is dedicated to:
- The overall development of new devops workflows in support of the UOR Machine.
- Providing a central **entry point** for all UOR Foundation resources while adhering to the principle of simplicity and the [**3-click rule**](https://en.wikipedia.org/wiki/Three-click_rule).
- Leveraging **GitHub Actions** for backend automation, content updates, and dynamic functionality without introducing additional complexity.
- Demonstrating the power of **pure HTML** as a foundational tool for creating accessible and elegant websites.

## Philosophy
The UOR Foundation Homepage embodies a minimalist design philosophy that aligns with early web principles:
1. **Simplicity:** Pure HTML ensures that the website is lightweight, easy to maintain, and <u>universally</u> accessible.
2. **Functionality through Automation:** GitHub Actions handle dynamic tasks like generating content, indexing files, or deploying updates, removing the need for JavaScript or server-side processing.
3. **Focus on Content:** By avoiding unnecessary embellishments, the emphasis remains on delivering clear, relevant, and accessible information.

# Co-create a Safe, Friendly, & Creative Community
The UOR Foundation casts a wide net to attract developers from all over. Respect & kindness are values we practice, hold and react to positively. Other acts demostrated by members that do not fall under kindness & respect will be ignored or properly handled for removal to ensure a friendly, safe & creative environment. 

We will always maintain the desire to co-create a friendly and open community. We believe a foundation grounded in **respect & kindness** is the key to a friendly and open community.

We also believe in forgiveness...creating new and exciting software will inevitably create disagreements. Disagreements lead to frustrations. Frustrations lead to loud words. And loud wor...well you get the idea. We make mistakes. Just stick to respect & kindness and have fun!

 Now back to business*!

## Three Policies for Developers:

### 1. **Pure HTML for All Content**
- Use **HTML only** for creating pages.
- Avoid relying on JavaScript or CSS for interactivity or styling.
- Keep the design clean and functional, reminiscent of early web aesthetics.

### 2. **Leveraging GitHub Actions**
GitHub Actions enable functionality traditionally handled by scripts or server-side processes:
- **Dynamic Content Updates:** Automatically generate or update pages based on repository changes.
- **File Indexing:** Scan and list files (e.g., PDFs, blog posts) dynamically.
- **Deployment:** Ensure all changes to the `main` branch are deployed seamlessly to GitHub Pages.
- **You:** How will you leverage GitHub Actions?

Example workflow for generating an index of PDFs:
```yaml
name: Generate PDF Index

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Generate index.html
      run: |
        echo '<!DOCTYPE html><html><body><h1>PDF Index</h1><ul>' > index.html
        find . -name "*.pdf" | sed 's|^./||' | while read -r file; do
          echo "<li><a href='$file'>$file</a></li>" >> index.html
        done
        echo '</ul></body></html>' >> index.html

    - name: Commit and Push Changes
      run: |
        git config user.name "GitHub Actions"
        git config user.email "actions@github.com"
        git add index.html
        git commit -m "Update PDF index"
        git push
```

### 3. **Maintaining Simplicity**
- The [**3-click rule**](https://en.wikipedia.org/wiki/Three-click_rule).
- Focus on plain content delivery.
- Disregard dependencies or external libraries.
- Use simple inline styles sparingly to enhance readability where necessary.

## Contributing
- Contributions must adhere to the repository’s simplicity-first approach (Policy #3).
- Use **pull requests** for any changes, ensuring they align with the purpose of the repository.
- Avoid introducing JavaScript, CSS frameworks, or other languages unless absolutely, and we mean ABSOLUTELY, necessary.

## Deployment
This repository is automatically deployed to GitHub Pages. Changes pushed to the `homepage` branch are reflected at:
```
https://uor-foundation.github.io/uor-homepage/
```

## UOR Webpage Static File Structure
Under construction...

uor-homepage/webpages
root/                   # Main directory
├── index.html          # Homepage
├── assets/             # Static assets
│   ├── images/         # Folder for images
│   │   ├── logo.png    # Logo file
│   │   └── banner.jpg  # Banner image
│   └── styles.css      # CSS file for styling
├── docs/               # Documentation folder
│   └── manual.pdf      # User manual
├── pages/              # Additional HTML pages
│   ├── about.html      # About page
│   └── contact.html    # Contact page
└── blog/               # Blog directory
    ├── 2025-01-01.html # Example blog post
    └── 2025-01-02.html # Another blog post


## UOR Webpage Dynamic File Workflow
Under construction...

Describe dynamic workflow: 

Github actions triggered &rarr; read input files (any data accessed) &rarr;  execute desired workflow on data (compute data) &rarr; write outputs (.html objects) in static structure?? &rarr;  display of new .html file generated in browser
 
## Vision
The UOR Foundation's Homepage demonstrates how combining the elegance of pure HTML with the automation capabilities of GitHub Actions can create powerful, maintainable, and user-focused websites. It challenges the modern tendency toward over-engineering, proving that simplicity can coexist with robust & rich functionality. And it is the front door into the world of UOR!

---

Thank you for supporting this vision of simplicity and innovation!

## Contact
For questions or feedback, please reach out via the [Contact page](https://<org-name>.github.io/uor-pages/contact.html) on the homepage.

---

<small>* The business of the foundation is building capability. And business is good!</small>

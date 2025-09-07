## Part 1: Version Control Understanding (~500 Words) 

How version control helps track changes in software:

Version control systems “give software engineering teams complete visibility to the code history and a single source of documentation for all files, folders, and messages” (Github,2025). Git is an example of a version control tool which provides the history of changes that occur over time to files and folders, helping software developers manage and track their work more effectively. Developers can add, commit and push their files with clear commit types and messages to a centralized repository used for collaborative projects, helping them to keep a complete code history by tracking changes. It also provides the ability to roll back to a previous commit when running into a bug/problem. 

Three specific collaboration benefits with examples:
1.	Ability to work together at the same time
   
Multiple developers can work on the project simultaneously without overwriting each other’s work. With a centralized remote repository, each developer can work on the same branch or different branch and merge them safely when needed. If both developers are working on the same file and branch but in different sections of it, Git has the ability to merge the changes to a singular file because the changes don’t overlap (in different parts of the file).

2.	Branching for feature Isolation / Trying new things

Developers can create separate branches for testing new features, experiments, or bug fixes without affecting the main project. For example, a developer creates a new feature and implements it within a secondary branch which contains the same files as the main branch, reducing the potential risk of breaking existing functionality. 

3.	Conflict resolution

Git has the ability to highlight conflicts that are caused from two developers editing the same file and same lines/part of the file. For example, if two developers edit the same file and lines, Git shows the conflicting lines which can then have to be resolved before merging.

Git’s Backup and Recovery Mechanisms: 

Git is a distributed version control system meaning each developer has a copy of the repository on their local machine. If the remote repository is inaccessible, the local repository can be used to restore the remote repository. One can roll back to earlier commits using commands such as git reset and git checkout. 

Difference between Git and GitHub:

Git is a version control system that resides and runs locally on a device, it is responsible for managing changes, tracking history, creating and initializing branches, and also allowing merging. Whereas GitHub is a cloud-based platform for hosting Git repositories, it enables collaboration by providing a centralized repository. It also offers features such as pull requests and merging. 

## Part 2: Git Repository Setup 
The steps listed below should help one create a local repository and push it's contents to a remote repository via Git.

1. Create a local directory and initalize it as a local repository with the branch name "main"
 ```bash
   mkdir csp451-checkpoint1
   cd csp451-checkpoint1
   git init -b main 
 ```
2. Create the required files via touch

List of intial required files; README.md .gitignore index.html style.css script.js 

 ```bash
   touch README.md .gitignore index.html style.css script.js
 ```

3. Add each required file to the local repository and commit (minimum 5 total commits)
```bash
   git add README.md
   git commit -m "docs: adding assignmnet brief reference"
   git add .gitignore
   git commit -m "chore: file specifiying what files or directories git should ignore in the repository"
   git add index.html
   git commit -m "style: basic html page"
   git add style.css
   git commit -m "refactor: code changes that does not fix a bug or add a new feature"
   git add script.js
   git commit -m "feat: a new feature that is to be added"
```
    
## Part 3: GitHub Repository (Remote Repository)
1. Creating a remote repository via GUI
   - Left click the "Create New" icon on the GitHub dashboard and select "New repository"
   - Enter the repository name "CSP451-CheckPoint1-YourName", for example CSP451-CheckPoint1-SunnyBasion
   - Ensure the visibility configuration is set  to "public" and keep the other configuration settings set to default
   - Click create repository at the bottom

2. Connecting to the remote repository and pushing the changes
   - One must associate their SSH public key  with their Github account in order to connect to the remote repository from the local machine.
   - To associate a SSH public key navigate to settings -> SSH and GPG Keys -> SSH Keys --> and select New SSH Key
   - The command below was used with my specific GitHub username and repository to connect to the remote repository and push changes from the local repository. 
   ```bash
   git remote add origin git@github.com:SunnyBasion/CSP451-Checkpoint1-SunnyBasion.git
   git push -u origin main
   ```
   
## Part 4: Branching Exercise 
1. Start on your main branch
   ```bash
   git checkout main
   git pull origin main   # make sure your main is up to date
   ```
2. Create and switch to the feature branch
   ```bash
   git checkout -b feature/add-about-page #option -b creates a new branch and switches to it 
   ```
3. Add about.html file and commit changes (minimum 3 total commits) 
   - Create the file via touch
   ```bash
   touch about.html
   ```
   - Add the about.html file to the local repository
   ```bash
   git add about.html
   ```
   - Add the following content (personal info), **refer to captured outputs heading below**
   - Listed below are the commit changes made:
   ```bash 
   git commit -m "feat: add about.html with personal information"
   git commit -m "feat: removing the interests line of code"
   git commit -m "feat: re-adding updated interests"
   ```
4. Push the feature branch to remote repository
   ```bash 
   git push -u origin feature/add-about-page
   ```
5. Creating a pull request (PR)
   - Go to your repository on GitHub
   - Select your feature/add-about-page branch from the branch drop down menu
   - Click create pull request
   - Fill in the following information:
      - Title: feature/add-about-page
      - Description: brief explanation of newly created branch
      - Assigning an instructor as a reviewer
   - It should redirect one to the newly created pull request webpage with the option to **merge the pull request**
   - After the merge has been successfully completed, switch over to the main branch and delete the feature branch locally and remotely
   ```bash 
   git checkout main
   git pull origin main
   git branch -d feature/add-about-page      # delete local branch
   git push origin --delete feature/add-about-page  # delete remote branch
   ```

## Appendix: Full Code Listing 

README.md 

CSP451 Checkpoint 1

Project Overview

This repository contains the files for CSP451 Checkpoint 1. It demonstrates basic Git workflow, including version control, branching, and collaboration practices. The project includes a simple HTML website with personal information and styling. 
Files
- `.gitignore` – Specifies files/folders Git should ignore  
- `index.html` – Main HTML page  
- `style.css` – CSS for styling  
- `script.js` – JavaScript functionality  
- `about.html` – About page with personal information  
- `README.md` – Project overview and setup instructions
Setup Instructions
1. Clone the repository:  
   ```bash
   git clone git@github.com:SunnyBasion/CSP451-Checkpoint1-SunnyBasion.git
   cd CSP451-Checkpoint1-SunnyBasion
****
Usage 
   - One can use the index.html for their apache/httpd webserver 
   - Open about.html to view the about page with personal information
     
Contributing 
   - Use feature branches and pull requests
     
License
   - This project is for educational purposes.

.gitignore
```
#OS files
.DS_Store
Thumbs.db

#Editor/IDE files

.vscode/
.idea/

#Backup files
*~
*.bak
```

index.html 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSPS41 CheckPoint 1</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Welcome to CSPS41 CheckPoint 1 – now with About!</h1>
    
    <script src="script.js"></script>
</body>
</html>
```
style.css
```
/* style.css */

/* Basic page styling */
body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
    margin: 0;
    padding: 20px;
    text-align: center;
}

/* Heading styling */
h1 {
    color: #333;
    margin-bottom: 20px;
}

/* Paragraph styling */
p {
    color: #555;
    font-size: 16px;
}

/* Optional: style links if you add any */
a {
    color: #007bff;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
}
```



     
## Reference:
1. GitHub. “What Is Version Control?” GitHub, 29 July 2024, github.com/resources/articles/software-development/what-is-version-control.






















































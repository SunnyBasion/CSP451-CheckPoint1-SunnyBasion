## Part 1: Version Control Understanding (~500 Words) 

## Part 2: Git Repository Setup 
The steps listed below should help one create a local repository and push it's contents to a remote repository via Git.

### Commands Executed
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
   - Ensure the visisbility configuration is set  to "public" and leep the other configuration settings set to default
   - Click create repository at the bottom

2. Connecting to the remote repository and pushing the changes
   - One must associate their SSH public key  with their Github account in order to connect to the remote repository from the local machine.
   - To associate a SSH public key navigate to settings -> SSH and GPG Keys -> SSH Keys --> and select New SSH Key
   - The command listed below with my specific GitHub username repository will allow one to connect to the remote repository and push changes from the local repository. 
   ```bash
   git remote add origin git@github.com:SunnyBasion/CSP451-Checkpoint1-SunnyBasion.git
   git push -u origin main
   ```






















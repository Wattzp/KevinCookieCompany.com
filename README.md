# GIT AND GITHUB

### WHAT IS GIT?

Git is a **distributed version control system** designed to help developers track changes in their code, collaborate with others, and maintain a history of their projects. Here’s a clear breakdown:

### 🔑 Key Features of Git

- **Version Tracking:** Records snapshots of your project over time, so you can revisit or roll back to earlier versions.

- **Branching & Merging:** Lets you create separate branches to experiment or develop features independently, then merge them back into the main project.

- **Collaboration:** Multiple developers can work on the same project without overwriting each other’s work.

- **Distributed System:** Every developer has a full copy of the repository, including its history, on their local machine.

- **Speed & Efficiency:** Git is optimized for performance, making operations like commits, diffs, and merges very fast.

### HOW TO INSTALL GIT

To install Git, download the installer for your operating system (Windows, macOS, or Linux), run it, and then verify the installation by typing git --version in your terminal or command prompt. On macOS and most Linux distributions, Git may already be preinstalled.

🖥️ Step-by-Step Installation Guide

1. Check if Git is Already Installed
- Open Terminal (macOS/Linux) or Command Prompt/Git Bash (Windows).

- Run:
```bash
`git --version`
```
- If Git is installed, you’ll see the version number. If not, proceed with installation.

2. Windows Installation
Download: Go to the official Git website and download the latest Windows installer.

Run Installer: Double-click the .exe file and follow the setup wizard.

Recommended: Accept default options unless you have specific needs.
Verify: Open Command Prompt or PowerShell and run:

git --version

Official Git web site: [GIT](https://www.git-scm.com/)

Official GitHub.com web site: [GITHUB](https://github.com/)

### 🛠️ HOW GIT IS USED
- **Local Development:** Developers commit changes to their local repository.

- **Remote Collaboration:** Teams often use platforms like GitHub, GitLab, or Bitbucket to share repositories online.

- **Project Management:** Git helps organize workflows, track bugs, and manage releases.

#### Example Workflow
- **Clone** a repository (download a copy).

- **Create** a branch for a new feature.

- **Commit** changes as you work.

- **Merge** your branch back into the main project.

- **Push** updates to a remote repository so others can access them.

**NOTE** When you install GIT, it comes with a terminal called GIT BASH. To launch it, simply click on your start menu and then type in git bash and then you can launch it. But you can also use any other terminal that you have on your computer. You can also use PowerShell, Command prompt. If you are on Mac, you could use the terminal that comes with your machine.

First configure your name and your email. This is important so that anytime we commit something or write something to the history book, we need to know who is doing it.
We specify the name using: 

`git config --global user.name "your name"` then press `Enter`.

We specify the email using:

`git config --global user.email "your email"` then press `Enter`.

We might also want to specify the default branch name, this might not make not make much sense now, but there are other branches that we would put in place later. 

`git config --global init.default branch main` then press `Enter`. # init.default == initialize.default.
    To change your default branch in Git from master to main using Git Bash, you’ll need to update both your local repository and the remote repository (e.g., GitHub).
    
**Local Repository Steps**
1. Rename the branch locally:
    `git branch -m master main`. This renames your current branch from `master` to `main`.
2. Update the upstream tracking branch:
    `git fetch origin`
    `git branch -u origin/main main`. This ensures your local `main` branch tracks the remote `main`.
3. Set HEAD to point to main:
    `git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main`.

**Remote Repository (GitHub/GitLab)**
1. Push the renamed branch:
    `git push -u origin main`
2. On GitHub (or your remote host), go to Repository Settings → Branches and set main as the default branch.
3. Optionally, delete the old `master` branch from the remote:
    `git push origin --delete master`

### SOME COMMAND PROMPT IN GIT CONFIG
To access other commands in git use:

`git config -h` then press `Enter`. This shows the **help information** for the `git config` command. This includes:

- __Options and flags__:

- `--global` → Apply settings for your user account across all repositories.

- `--system` → Apply settings system-wide.

- `--local` → Apply settings only to the current repository.

- `--list` → Show all current configuration settings.

- `--get <name>` → Retrieve the value of a specific configuration variable.

- `--unset <name>` → Remove a configuration variable.

- `--edit` → Open the configuration file in your default editor.

We can also see other detailed information on `git config` by running:

`git help config` then press `Enter`. This open up a manual that is hosted on your computer so even if you don't have internet access you can still be able to access this file.

To clear your termial and start afresh, simply type **`Clear`** and press `Enter`

#### CHANGE THE DIRECTORY 
1. If you want to commit in a different folder/repository

- Navigate to that folder in the Git Bash:

cd path/to/your/repo
Example:
cd C:/Users/Vincent/Downloads

Then to turn this to a Git repisitory you use:
`git init` 
then press `Enter`
This initializes our repository in our directory.
Check your file directory, you'll see a new `.git` folder. Once you click on `.git` you'll see all your necessary repository files. 

2. Still in your `GIT BASH` Terminal:
   type in `git status` this will tell you the status of your repository i.e it shows:
   - the branch of your repository(main/master)
   - the number of commit made
   - the untracked files; files in your file explorer (currently all files will be untracked meaning that if I make any changes to this files `Git` won't recognized it because they're untracked. But if I track a file `Git` would know what changes I made to the file.
  
To track a file I simply type in `git add` and then I could specify the file name. For example:
`git add the name of the file` then click `enter`
To cofirm the file is now been tracked, type in `git status`
To untrack a file back simple use: `git rm-- cached <file>`.

  To ignore or hide a file from git to see it from your file explorer, you go to your files in your file explorer and then add a new text document called `.gitignore`. This allows us to ignore certain files,folders, or even entire extension. Rename your text document `.gitignore`, a pop-up will appear idicating "It might become unstable if you also change the file extension. `.txt`, click on yes. A new file `.gitignore` is then created. 
Open it and it opens as a notepad. Here you can tell git what files to ignore. 
Example you can commit using "# ignore all .txt files, underneath it you can type in an asterisk, *, so basically any filename.txt, will be ignored, then go to file and save. 
  To see a comprehensive list of all the different files,folders, or even just an entire extensions, you can go to https://github.com/github/gitignore. This are important to log files, auto generated files or any files that you don't want to include as part of your project.
Back in git bash, type in `git status` and you'll no longer see those files you ignore.

Remember we tracked only one file before, "index.htm", but then we also untracked it so its back to our stagged files to be committed.

To track all files at once,
type:  `git add --all` alternatively `git add --A` or simply `git add .` then once again press `enter`. 
then once again type your `git status`, here you see all the files are currently been tracked tracked except for the file that I  ignored, and currently all these files are in an environment called **Staging** 

#### HOW TO COMMIT ON GIT
Now that I've added all these different file I want to commit them.
what does it means to commit?
In Git, a commit is essentially a snapshot of your project at a specific point in time. Think of it like saving your work in a video game—you capture the current state so you can revisit it later if needed.

- Command examples:

  - `git commit -m "Add login feature"` → saves staged changes with a message.

  - `git commit -a -m "Update all tracked files"` → stages and commits all tracked changes at once.

🧩 Why it matters
- Commits are the foundation of version control. They let you experiment safely, collaborate with teammates, and maintain a clear record of how your project evolves.

- Good commit messages are crucial—they help you (and others) understand why a change was made, not just what changed.

Now, let's say we want to make some changes to those files in our file explorer. For example, we want to modify our index.htm, by dragging the file into a notepad, we can see the content of our file. 
Then we can make changes to the content, and then save.

Then, back in `GIT BASH` we can then type `git status`. Here we can see that git recognize that a file has been modified. 
    To see what is been modified we type; `git diff` which will simply show us what the differences are.

In Git, **staging** (also called the staging area or index) is the intermediate step between editing files in your working directory and committing them to the repository. Think of it as a "draft board" where you prepare and review changes before making them permanent in the project history.

How Staging Works
- **Working Directory**: Where you edit files (new, modified, or deleted).

- **Staging Area**: A holding space where you place selected changes using git add.

- **Repository**: The permanent history of commits after you run git commit.

**Why Staging is Useful**
- **Selective commits**: You can choose which changes to include, even if multiple files were modified.

- **Organized history**: Break large edits into smaller, logical commits.

- **Review step**: Double-check what will be committed before finalizing.

**Key Commands**
```bash
- `git add <file>` → Stage a specific file.

- `git add .` or `git add -A` → Stage all changes in the directory.

- `git status` → See which files are staged vs. unstaged.

- `git restore --staged <file>` → Unstage a file if you change your mind.

- `git rm "<file>"` → To delete a file.

- `git mv "<old file>" "<new file>"` → To rename a file.

- `git commit -m " updated commit message"` → To add changes to the history book i.e directory.

- `git log`  → To review all commit that has bee made so far.

- `git log --oneline` → To see the abbreviated version of all the commit history.

- `git commit -m "updated commit message" --ammend` → To amend the commit message in the directory.

- `git log -p` → To see a specific commit made.

- `git help log` → To see the manual for git log.
```
In Git, **rebasing** is a way to integrate changes from one branch into another by **replaying commits** rather than merging them. It essentially moves or "re-bases" your branch’s commits on top of another branch, creating a cleaner, linear history.  

### How Rebasing Works
- Suppose you’re working on a feature branch while the `main` branch gets new updates.
- With `git merge`, you’d combine histories, producing a merge commit.
- With `git rebase`, Git takes your feature branch commits and re-applies them on top of the latest `main` branch commits, as if you had started your work from the newest version of `main`.  [Git](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)  [FreeCodecamp](https://www.freecodecamp.org/news/how-to-use-git-rebase/)  [GeeksForGeeks](https://www.geeksforgeeks.org/git/rebasing-of-branches-in-git/)  

To rebase, type: `git rebase -i --root`. These shows us all the commits made and how we can either `merge` or `squash` or even `reword` our commits. To exit this view we type colon, `:` and then x and hit enter. This successfully rebase and update your commits.

### Key Benefits
- **Linear history**: No extra merge commits, making `git log` easier to read.
- **Cleaner collaboration**: History looks like you developed your feature after the latest changes in `main`.
- **Easier debugging**: A straight timeline avoids complex branching structures.

### Basic Syntax
```bash
git checkout feature-branch
git rebase main
```
This moves the commits from `feature-branch` on top of `main`.

### When to Use
- **Before merging a feature branch**: To ensure it’s up to date with `main`.
- **For tidier history**: When you want commits to appear sequentially without merges.
- **In solo work**: Rebasing is safest when you’re the only one working on a branch, since it rewrites history.

### Caution ⚠️
- Rebasing **rewrites commit history**. If you’ve already pushed commits to a shared repository, rebasing can cause confusion for collaborators.
- Best practice: **Don’t rebase public/shared branches**. Use it mainly for local cleanup before pushing.

To create a new branch, type: `git branch "name of new branch"`. To check how many branch, type: `git branch`. To switch to another branch, type: `git switch <new branch>`. Now all the file reflects to the new branch. 
    peraventure we want to change the a file again to reflect in our new branch. we go to the file for example the "secret recipe.htm", we want to change the heat temp from 500 degree to 375 degree, we open the file in our file explorer using note pad then edit it and save. back in `GIT BASH` type `git status` there you'll see that the file was modified. Then if I want to commit this changes to the new branch, type: `git commit -a -m "updated commit message"`

Then to merge both branches together, we use: `git merge -m "merge new branch to old branch" new branch`
Since we have no need for the new branch we can delete it. To delete a branch we type in: `git branch -d branch you want to delete and enter `

#### CONFLICTS IN MERGING
If you have a conflict on which branch you made your commits, but what if you create a branch and you tried to merge it back in, but the main branch has changed since you created your branch. In this case you will have a merge conflict. To work through this, first you use a command that doesn't only switches you to a new branch but also create a new branch. Here we type in: `git switch -c new branch` the "c" will create a new branch. We can type in `git branch` to confirm. After this, go to your file explorer and you can make any changes you want to make in your files content by dragging i to a notepad and then make your changes and save, then close, example, like your `index.htm` file, then next, back in your `GIT BASH`  you commit on the new branch using: `git commit -a -m "commit message" the enter`. Then switch your branch back to `main`. Next, back on your file explorer, make a confilcting text on the same file i.e `index.htm`, then save and close. Back on your `GIT BASH` commit similar message and then merge both branches by using `git merge new branch` and click `enter`. A prompt will appear saying:

`Auto-merging index.htm
CONFLICT (content): merge conflict in index.htm
Automatic merge failed: fix conflict and then commit the result.`
To fixx this, go back to your file explorer and the clear the first content as the `<<<<<HEAD and also the comment messege at the end as >>>>>Updatetext` then save and close. Back in `GIT BASH` type: `git commit -a -m "update text on index" and click `enter`. You can see now that you are in your main branch.

### GITHUB
GitHub is a **web-based platform built around Git**, the version control system. It provides tools for **collaboration, version control, and project management** in software development. Here’s a clear breakdown:

### 🔑 What GitHub Is
- **Code hosting platform**: Stores and manages code repositories online.
- **Version control**: Tracks changes in code, enabling developers to revert, merge, or branch projects.
- **Collaboration hub**: Allows multiple developers to work together on the same project seamlessly.
- **Community & sharing**: Millions of developers share open-source projects, libraries, and tools.

### ⚙️ Core Features
- **Repositories**: Containers for projects (code, documentation, data, images, etc.).
- **Branches**: Parallel versions of a project for experimentation or feature development.
- **Commits**: Snapshots of changes made to the code.
- **Pull Requests (PRs)**: Proposals to merge changes into the main project, often reviewed by peers.
- **Issues**: Used to track bugs, tasks, or feature requests.
- **Actions**: Automations for testing, deployment, and CI/CD pipelines.

### 📊 Context
- Founded in **2008**, headquartered in **San Francisco**, and acquired by **Microsoft in 2018**.
- As of 2025, GitHub has over **150 million users worldwide**.
- It powers both open-source and enterprise projects, from small scripts to massive frameworks.  [Wikipedia](https://en.wikipedia.org/wiki/GitHub)  [W3School](https://www.w3schools.com/whatis/whatis_github.asp)  [GeeksForGeeks](https://www.geeksforgeeks.org/git/introduction-to-github/)

## 🔧 Installing Git & GitHub

### 1. Install Git
- **Windows**:  
  - Download from [git-scm.com](https://git-scm.com/downloads/win).  
  - Run the installer and follow the setup wizard (default settings are fine).  
- **Mac**:  
  - Git is usually pre-installed. Check with `git --version` in Terminal.  
  - If not installed, use Homebrew: `brew install git`.  
- **Linux**:  
  - Git often comes pre-installed. If not, use your package manager:  
    - Ubuntu/Debian: `sudo apt-get install git`  
    - Fedora: `sudo dnf install git`  

### 2. Install GitHub Desktop (Optional)
- GitHub Desktop is a GUI tool that simplifies Git usage.  
- Download from [desktop.github.com](https://desktop.github.com).  
- Installing it also installs Git automatically.  [Github](https://github.com/git-guides/install-git)

---

## ⚙️ How Git & GitHub Work

| Tool | Purpose | Example Use |
|------|----------|-------------|
| **Git** | Local version control system. Tracks changes in files, lets you revert, branch, and merge. | `git add`, `git commit`, `git push` |
| **GitHub** | Cloud platform for hosting Git repositories. Enables collaboration, issue tracking, and pull requests. | Share code, collaborate with teammates, open-source projects |

### Workflow
1. **Initialize a repo**: `git init` (creates a local repository).  
2. **Track changes**: `git add file.txt` → `git commit -m "message"`.  
3. **Connect to GitHub**: `git remote add origin <repo-url>`.  
4. **Push changes**: `git push origin main`.  
5. **Collaborate**: Others can clone your repo, make changes, and submit pull requests.  [GeeksForGeeks](https://www.geeksforgeeks.org/git/how-to-install-git-and-setup-github/)  [FreeCodecamp](https://www.freecodecamp.org/news/learn-how-to-use-git-and-github-a-beginner-friendly-handbook)

---

## 🚀 Quick Analogy
- **Git** = Your personal notebook where you track every change.  
- **GitHub** = The online library where you publish your notebook so others can read, contribute, and improve it.



























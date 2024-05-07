Key concepts:

- Repository - Where your project files and commit history are stored
- Commit - A snapshot of changes, like a version checkpoint 
- Branch - A timeline of commits that lets you work on parallel versions
- Merge - To combine changes from separate branches
- Pull request - Propose & review changes before merging branches

Key commands:

- git init - Initialize a new repo
- git status - View changed files not staged for commit
- git add - Stage files for commit
- git commit - Commit staged snapshot 
- git branch - List, create, or delete branches
- git checkout - Switch between branches
- git merge - Join two development histories (branches)
- git push/pull - Send/receive commits to remote repo

With these basic concepts and commands, you can leverage GIT to track changes, work in branches, and collaborate with others. 

![img](https://github.com/SouravGanesh/Data-Digest/blob/672dd0231f7adcfa2c641d50a84f961b5b08a4a9/images/git1.gif)

Here's a cheatsheet to master Git.


✨𝗚𝗲𝘁𝘁𝗶𝗻𝗴 𝗦𝘁𝗮𝗿𝘁𝗲𝗱:
git init: Initializes a new Git repository.
git clone <repo_url>: Clones an existing repository to your local machine.

📄𝗧𝗿𝗮𝗰𝗸𝗶𝗻𝗴 𝗖𝗵𝗮𝗻𝗴𝗲𝘀:
git status: Checks the status of files in your working directory.
git add <file> or git add .: Stages files for commit.

✅𝗖𝗼𝗺𝗺𝗶𝘁𝘁𝗶𝗻𝗴 𝗪𝗼𝗿𝗸:
git commit -m "message": Commits staged changes with a descriptive message.

🔀𝗕𝗿𝗮𝗻𝗰𝗵𝗶𝗻𝗴 𝗮𝗻𝗱 𝗠𝗲𝗿𝗴𝗶𝗻𝗴:
git branch: Lists existing branches.
git branch <new_branch>: Creates a new branch.
git checkout <branch>: Switches to a different branch.
git merge <branch>: Merges changes from one branch into another.
git checkout -b <new_branch>: Creates and switches to a new branch.

👨‍💻𝗥𝗲𝗺𝗼𝘁𝗲 𝗖𝗼𝗹𝗹𝗮𝗯𝗼𝗿𝗮𝘁𝗶𝗼𝗻:
git remote -v: Lists remote repositories.
git fetch origin <branch>: Fetches changes from a remote branch.
git merge origin/<branch>: Merges fetched changes into the current branch.
git push origin <branch>: Pushes local changes to a remote branch.

🔎𝗧𝗿𝗮𝗰𝗸𝗶𝗻𝗴 𝗛𝗶𝘀𝘁𝗼𝗿𝘆:
git log: Shows a list of commits.
git log --oneline: Displays a condensed commit history.

⏪𝗨𝗻𝗱𝗼𝗶𝗻𝗴 𝗠𝗶𝘀𝘁𝗮𝗸𝗲𝘀:
git revert <commit>: Reverses a specific commit.
git reset --hard HEAD: Resets the working directory to the last commit (use with caution!).

𝗧𝗮𝗴𝗴𝗶𝗻𝗴 𝗠𝗶𝗹𝗲𝘀𝘁𝗼𝗻𝗲𝘀:
git tag: Lists existing tags.
git tag -a v1.0 -m "tag": Creates a new tag for a specific commit.

⚙𝗖𝗼𝗻𝗳𝗶𝗴𝘂𝗿𝗮𝘁𝗶𝗼𝗻:
git config --global user. name "name": Sets your global Git username.
git config --global user. email "email": Sets your global Git email.

![img](https://github.com/SouravGanesh/Data-Digest/blob/9dac2971247ccd3bf90be9e69184d4f87770538a/images/git2.png)

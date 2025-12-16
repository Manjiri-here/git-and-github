# git-and-github

cd my_profile/
git status
git add .
git status
git commit -m "new changes to docker file"
git push

But there was a conflict during push command as below-

ubuntu@ip-172-31-27-157:~/my_profile$ git push
Username for 'https://github.com': Manjiri-here
Password for 'https://Manjiri-here@github.com':
To https://github.com/Manjiri-here/Docker-demo
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/Manjiri-here/Docker-demo'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. If you want to integrate the remote changes,
hint: use 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Hence to rebase we executed below commands-

git config pull.rebase false

Done, now we can push:

git status
git add .
git push
git pull origin main --no-rebase
git push origin main


----

Diference between git push and git pull request:

| Action           | What it is    | Where it happens | Purpose                                    |
| ---------------- | ------------- | ---------------- | ------------------------------------------ |
| **git push**     | Git command   | Terminal         | Upload commits to a remote branch          |
| **Pull Request** | GitHub action | GitHub UI        | Ask someone to review + merge your changes |

git add .
git commit -m "change"
git push origin feature-branch    # step 1: send your branch
# go to GitHub → create PR        # step 2: ask to merge your branch

Git push: Upload my local commits to a remote branch.
Pull request: I want someone to pull my changes into another branch (usually main). Please review and merge.


---
# Git push and pull request

Push (git push):
This is when you send your changes from your local computer (or your branch) directly to the remote repository (like GitHub).
It's like uploading your work straight away.
You need permission to do this on the target branch (e.g., you can usually push to your own branches, but not always directly to the main branch in team projects).
Pull Request (PR):
This is not a Git command — it's a feature on GitHub/GitLab/etc.
After you push your changes to a separate branch (or your fork), you create a Pull Request to ask the team/maintainer: "Hey, please review my changes and merge (pull) them into the main branch."
It's a request for review and merge, often with discussions, code reviews, and approvals before anything gets added to the main code.

Key Difference

Push = Directly upload/send your code (immediate, no review required if you have permission).
Pull Request = Politely ask someone else to review and add (pull) your code into the main branch (safe for teams, prevents bad code from going in directly).

Simple Analogy: Contributing to a Shared Cookbook
Imagine a team writing a big shared cookbook (the main repository/branch is the official book).

Push: You have direct access to the book. You write a new recipe on your computer, then push it straight into the official book. Done — no one checks it first. (Risky if you're new or might make mistakes!)
Pull Request: You don't have direct access (or the team rules say no direct changes). You write your new recipe, make a copy of the book (fork) or a separate section (branch), add it there, and push to your copy/section. Then you say: "Hey team, I added a chocolate cake recipe — please check it and pull it into the official book if it's good!"
The team reviews, suggests changes ("Add more sugar!"), and only if approved do they add it.

This way, the official cookbook stays high-quality, and everyone collaborates safely.
Many people get confused because both involve "pushing" first (you usually push your branch before opening a PR), but the PR is the extra step for safe merging.

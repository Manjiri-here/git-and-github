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



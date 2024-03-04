# github-intro

- practice command line git commands like
    - `git status`
    - `git add`
    - `git commit -m "message"`
    - `git push`
    - `git pull`
    - `git log`
    - `git checkout`
    - `git branch`
    - `git merge`
    - `git diff`


We will be running through this repo using first the desktop app GitHub desktop and then using the command line. 

These steps will primarily happen on the GitHub app or the website
0. Break into groups of 2-3
1. Fork this repo (and name the forked repo `github-intro-YOURNAME`)
2. Clone your forked repo onto your local computer
3. Open the repo folder in VSCode or your preferred text editor
4. Add a file to study spaces recommending a good place to do computer work near Harvard
5. Commit your changes
6. Push your changes to your forked repo
7. Open a pull request to merge your changes into the original repo and assign your partner to review your changes (???)
8. Review your partner's pull request and merge it into the original repo
9. Pull the changes from the original repo into your local repo
10. DELETE your repo (optional !!!) We'll be using the original repo for the next steps

Now we will be working on the command line.
1. Clone the original repo onto your local computer
    `git clone https://github.com/harvardinformatics/github-intro.git`
2. Start a new branch called `haiku-NAME` and write 1-2 lines of a haiku.
    `git checkout -b haiku-NAME`
3. Commit your changes & push to your branch
    `git add haikus/haiku_test.md`
    `git commit -m "Add haiku line"`
    3.1 If you try to push your branch, you will get an error. You need to set the upstream branch on your first push
    `git push` <- this will give you an error "The current branch haiku-NAME has no upstream branch"
    `git push --set-upstream origin haiku-NAME` <- this creates the branch on your remote to push to
5. Make a PR to the main branch repo and assign your partner to review
    `gh pr create --head haiku-lei --assignee "@YOURPARTNER"`
6. Review your partner's PR and add the next lines
    `gh pr checkout PRNUMBER`
7. Decide you don't like that line and want to change it back
    `git log` <- find the commit hash of the commit you want to revert to
    `git checkout COMMIT_HASH haikus/haiku_test.md`
8. Add the final lines to the haiku
9. Commit your changes and push upstream
    `git add haikus/haiku_test.md`
    `git commit -m "Add final lines to haiku"`
    `git push --set-upstream origin haiku-NAME`
12. Merge the PR and say something nice about the haiku!
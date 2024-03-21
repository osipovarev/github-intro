# github-intro

We will be running through this repo using first the command line and then GitHub Desktop or VSCode git integration.

These steps will primarily happen on the command line. Make sure you have the GitHub CLI installed and authenticated if you want to use the command line to do the pull request. Otherwise, you can use the GitHub website.

0. Break into pairs
1. Fork this repo (and name the forked repo `github-intro-YOURNAME`)
2. Clone your forked repo onto your local computer
    * `git clone https://github.com/YOURUSERNAME/github-intro.git`
3. Open the repo folder in VSCode or your preferred text editor
4. Add a file to study spaces recommending a good place to do computer work near Harvard
5. Commit your changes
    * `git add FILENAME`
    * `git commit -m "Add study spaces file"`
6. Push your changes to your forked repo
    * `git push`
7. Open a pull request to merge your changes into the original repo (can also do this on the GitHub website)
    * `gh pr create --assignee "@YOURPARTNER"`
8. Review your partner's pull request and merge it into the original repo (can also do this on the GitHub website)
    * `gh pr checkout PRNUMBER`
    * `gh pr merge`
9. On your fork, sync your fork so your repo is updated (Do this on the github website)
10. Pull the changes from the your fork into your local repo
    * `git pull`

Now we will be working on GitHub Desktop, the GitHub website, or VSCode git integration. Use whichever GUI you prefer. The equivalent command line commands to GUI options are printed below each step. We will be creating a branch and then working on the same file on two different branches to create a merge conflict. Branches are great for experimenting on a feature or fixing a bug without affecting the main code, but they can cause merge conflicts if two branches change the same line of code.

Example of branching:
```mermaid
gitGraph
    commit
    branch bugFix
    commit
    commit
    commit
    checkout main
    merge bugFix id: "merge"
    commit
```

1. Open your forked repo in your preferred text editor
2. Create an empty file called `haiku_yourname.md` in the `haikus` folder and commit & push it
    * `git add haikus/haiku_yourname.md`
    * `git commit -m "Add empty haiku file"`
    * `git push`
3. Start a new branch called `haiku-test` (substituting your name for NAME)
    * `git checkout -b haiku-test`
4. Write 1-2 lines of the haiku and save it in the `haikus` folder
5. Commit your changes & push it
    * `git add haikus/haiku_yourname.md`
    * `git commit -m "Add haiku lines"`
    * `git push`
6. Switch back to branch `main` and observe that your haiku is still empty
    * `git checkout main`
    * `cat haikus/haiku_yourname.md`
7. Write a line in your empty haiku and commit & push it
    * `git add haikus/haiku_yourname.md`
    * `git commit -m "Add haiku line"`
    * `git push`
8. Open a pull request from `haiku-test` and try to merge it into `main`
    * `gh pr create`
    * `gh pr checkout PRNUMBER`
    * `gh pr merge`
9. Use the GitHub interface or VSCode to resolve the merge conflict
10. Delete the branch once you are done merging (using the GitHub web interfact, command line version printed for reference)
    * `git branch -d haiku-test`
11. (Optional) Submit a pull request to the original repo with your haiku so we can all see it!

For reference, this is the gitflow diagram for the above steps:

```mermaid
gitGraph
    commit id: "Add empty haiku file"
    branch haiku-test
    commit id: "Add haiku lines"
    checkout main
    commit id: "Add haiku line"
    merge haiku-test type: highlight tag: "merge conflict"
```
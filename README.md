# Great at Git

## Part 1

### 1.1

- Clone SEAL from [GitHub.com/Microsoft/SEAL](https://GitHub.com/Microsoft/SEAL)
- Look at commit history with `git log --pretty=oneline`
- Use `git show 191226f` to look at the commit 191226f. What was changed?
- Use `git log --reverse` to see what the first commits were to the SEAL repository

### 1.2
- Create an account at [GitHub.com](https://GitHub.com).
- Create a new repository called `testrepo`
- Clone it as explained on the GitHub website
- Add a single file, README.md, with text "# testrepo" in it
- Create a new commit and push as explained on the website
- Observe how `README.md` is rendered by GitHub

### 1.3
- Clone the same repository into a different directory, make a (non-conflicting) change, commit, and push
- Pull the changes to the first clone you created
- Make non-conflicting changes in both clones simultaneously, commit, and push one at a time to see how Git handles this
- Add a `.gitignore` that ignores all *.pdf files; test that this works by creating an empty file `document.pdf`. Commit and push the `.gitignore`.

## Part 2

### 2.1

- Create a new file `newfile.txt` and add it to the index with `git add newfile.txt`
- Move it back to the working tree with `git reset -- newfile.txt`
- Add it back to the index and create a commit
- Print the chain of commits with `git log --pretty=oneline`
- Create a new branch called `newbranch` from `master` with `git branch newbranch`
- Switch to the new branch with `git checkout newbranch`
- Create a file `feature.cpp` into the new branch and commit
- Push the new branch to GitHub and observe it in GitHub

### 2.2

- Switch back to `master` with `git checkout master`
- Look at `git log`: the new file is gone and `HEAD` is now pointing to master
- Branches are commits (tips of chains of commits); HEAD is your current view; typically HEAD points to a branch
- `HEAD` is a symbolic reference to a branch
- `git checkout` changes which commit/branch `HEAD` points to; this changes the working tree
- Try checking out an older commit: you'll get to "detached HEAD" state

### 2.3

- Roughly, `git reset` changes what commits branches point to; another use is to invert what `git add` does (`git reset -- <paths>`)
- `git reset --soft <commit>` changes the branch that `HEAD` points to given commit and leaves all changes to the index
- `git reset` (or `git reset --mixed`) additionally resets the index but not the working tree
- `git reset --hard` additionally resets the working tree so you will lose all contents of your working tree (WARNING!!! THIS IS HOW YOU ACTUALLY REVERT BACK)

### 2.4

- Make some conflicting commits
- Try to merge the commits and resolve the conflict
- Create a chain of commits in one branch and use `git cherry-pick` to replay one of them in another branch
- Create a chain of commits and replay them onto another branch with `git rebase`; look also into `git rebase --onto`

## Part 3

- Simulate GitHub by creating a new bare repository: `git init --bare testrepo.git`
- Clone the repository
- Look at `.git/config` and `.git/refs`
- Demonstrate examples of local branches, local tracking branches, remote tracking branches, and remote branches
- Push to a specific remote branch with `git push <remote> <refspec>`
- Set up custom tracking branches
- Read about pull requests on GitHub
- Study SEAL development workflow and set up environment to work across ADO and GitHub
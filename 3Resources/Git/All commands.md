- configuring git
    - setting user name and email        
        - use the git config
        - set the user using the following command
        ```bash
        git config --global user.name "name"
        git config --global user.email "email"
        ```
    - viewing the user name and email        
        - use the get flag along with the git config        
        ```bash
        git config --get user.name
        git config --get user.email
        ```
    - removing the user name and email        
        - use the unset flag with config        
        ```bash
        git config --unset user.name
        git config --unset user.email
        ```
    - setting default code editor        
        this is done by setting the values in the core part of the config        
        ```bash
        git config --global core.editor "code --wait"
        ```
        
    - editing the global values using the code editor
        
        ```bash
        git config --global -e
        ```
        
    - setting the global carriage return and line end values
        
        ```bash
        git --config core.autocrlf input //linux
        git --config core.autocrlf true //windows
        ```
        
- status and short status
    
    status gives the status of the staging area
    
    the short status gives the status of the staging area in a short and easy to understand format
    
    ```bash
    git status
    git status -s
    ```
    
- adding files to the staging area (git add)
    
    can be added with the git add command
    
    ```bash
    git add <filename1> //adds filename1 to the git
    git add <filename1> <filename2> //adds filename1 and filename2 to git
    git add *.txt //adds every .txt file to git
    git add . //adds all files recursively to git
    ```
    
- committing changes
    
    done with the git commit command
    
    ```bash
    git commit -m "message"
    ```
    
    - rules for committing
        - commit as often as you can
        - each commit should make sense and should be a meaningful commit
        - do not combine multiple changes into one commit unless they make sense together
        - the commit messages should be written in past tense
- skipping the staging area and committing directly
    
    done with the -a flag and the commit command
    
    ```bash
    git commit -am "message"
    ```
    
    where _a_ is used to skip the staging area and _m_ is used to type the commit message
    
- displaying all the files in the staging area
    
    ```bash
    git ls-files
    ```
    
- removing files from the staging area
    
    - method 1
        
        - if we remove the files from the local machine, then we need to also remove the file from the staging area too
        - to do this, just _git add_ the file
        
        ```bash
        rm file2
        git add file2
        ```
        
    - method 2
        
        since removing the file from both the directory and the staging area is a common thing, git provides us with a command to do the same
        
        ```bash
        git rm <filename>
        git rm *.txt
        ```
        
- renaming or moving files in the staging area
    
    - method 1
        
        to rename or to move files, we need to stage both the initial and the final file name in git
        
        so if we rename _filename1_ to _filename2_, we need to _git add_ both these files to track the changes
        
        ```bash
        mv filename1 filanema2
        git add filename1 filename2
        ```
        
    - method 2
        
        since this is a common operation, git provides us with a command
        
        ```bash
        git mv filename1 filename2
        ```
        
        the changes are applied for both the directory and the staging area
        
- ignoring files
    
    - can be done by creating a new file called as gitignore
    - this gitignore file contains the regex of the files that need to be ignored by git
    - this gitignore file needs to be staged and committed
    
    <aside> 💡 if we commit a file, and then ask git to ignore it, git will still track the changes for that file
    
    </aside>
    
- removing files from staging area
    
    done using the the —cached flag/option and the rm
    
    <aside> 💡 the older name for staging area was **index.** this is what is commonly found in the git documentation too
    
    </aside>
    
    ```bash
    git rm --cached filename
    git rm --cached -r filename
    ```
    
- comparing the changes made to the files
    
    done using the git diff command
    
    to get the difference between the staged files and the committed files, we run the _git diff_ command with the _—staged_ option
    
    to get the difference between the directory files and the staged files, we run the _git diff_ command without any options
    
    ```bash
    git diff
    git diff --staged
    ```
    
- changing the diff tool to a more cleaner diff view tool
    
    primarily use vscode for diff viewing as it is cross platform
    
    add the changes to the .gitconfig file
    
    ```bash
    [diff]
    	tool = vscode
    [difftool "vscode"]
    	cmd = "code --wait --diff $LOCAL $REMOTE"
    ```
    
- viewing changes in the diff tool than the terminal diff tool
    
    use the exact same syntax as the _diff_ command, but call it with the _difftool_ command
    
    ```bash
    git difftool
    git difftool --staged
    ```
    
- viewing all commits
    
    uses the log command to view all the commits that have been made
    
    ```bash
    git log
    ```
    
    - the commits are sorted from latest to earliest
        
    - each commit contains
        
        - 40 character unique identifier
        - author
        - date
    - the —oneline flag is a option to show the logs in only a single line of code
        
        ```bash
        git log --oneline
        ```
        
    - reverse command, shows from earliest to latest
        
- restoring files
    
    - can be done using the git restore command
        
    - lets say we delete a file and commit that change
        
    - in order to make restore the file, we can pull the file back from the initial commits
        
        ```bash
        git restore --source=HEAD~1 <filename>
        ```
        
- git branches
    
    - think of this as a different instance of the same project
    - once we create a new branch, we can then make new changes to it, without affecting the existing code in the master branch
    - later, we can merge the branch into master branch
    
    ```bash
    git branch <branchname>
    git checkout <branchname>
    ```
    
    this can be combined into a single command
    
    ```bash
    git checkout -b <branchname>
    ```
    
    this will create a new branch and checkout to that particular branch
    
- merging branches
    
    - once we finish work on a particular branch, we can then merge the branch into the master branch
    - we use the _merge_ command to merge
    
    ```bash
    git merge <branchname>
    ```
    
    make sure to switch to the branch that will accept the merge before performing the merge operation
    
- deleting branches
    
    ```bash
    git branch -d branchname
    ```
    
- merge conflicts
    
- branch is ahead/before of branch by commits
    
    - it means that the branch has commits that the parent branch does not have
    - to solve this, we either do a git pull and try to look into the issue, or we look to rebase the branches to solve the issue
    - also doing a merge will solve the issue
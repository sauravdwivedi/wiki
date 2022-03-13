# Tech wiki

## Mac

<details><summary>Terminal</summary>
<p>

###### Create zshrc

> touch ~/.zshrc

> open ~/.zshrc -a Xcode

> source ~/.zshrc

###### To customise terminal, add in zshrc

> export PS1='sd@tracklib $ '


</p>
</details>

<details><summary>Homebrew</summary>
<p>

###### Install homebrew from terminal

> ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

</p>
</details>

<details><summary>Python</summary>
<p>

###### Set python3 global, open zshrc

> open ~/.zshrc -a Xcode

and add

> alias pip=/opt/homebrew/bin/pip3

> alias python=/opt/homebrew/bin/python3

</p>
</details>

<details><summary>GitLab/GitHub CLI</summary>
<p>

- [ ] https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html

> brew install gh

> brew install git

###### Login (for github not gitlab)

> gh auth login

###### Create project

> cd <project_dir>

@ SSH

> git clone git@gitlab.tracklib.com:saurav/test.git

@ HTTPS

> git clone https://github.com/sauravdwivedi/test.git

> cd test

###### Initialise connection between project dir and git repository (redundant)

> git init

###### Add remote that tells Git where to push or pull from (redundant)

> git remote add origin git@github.com:sauravdwivedi/test.git

> git remote -v

###### Download the latest changes in the project from origin repo (<_remote> = origin)

> git pull <_remote> <name_of_branch>

> git pull

###### Create a branch

> git checkout -b <name_of_branch>

###### Switch to a branch

> git checkout <name_of_branch>

###### Work on project, make changes (e.g. load <project_dir> in PyCharm)

###### View differences

> git diff

###### View the files that have changes

> git status

###### Add local changes to staging

> git add <filename_OR_folder_name>

###### stage all files in the current directory and subdirectory

> git add .

###### Confirm that the files have been added to staging

> git status

###### Commit the staged files

> git commit -m "e.g. addded test.py in project"

###### Send changes to Git (<_remote> = origin)

> git push <_remote> <name_of_branch>

###### Merge a branch with default branch

> git checkout <default_branch>

> git merge <feature_branch>
  
###### Delete local repo after repo update
  
> cd ..

> sudo rm -r <repo_name>

</p>
</details>



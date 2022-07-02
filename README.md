# Tech wiki

## Mac

<details><summary>Terminal</summary>
<p>

#### Create zshrc

> touch ~/.zshrc

> open ~/.zshrc -a Xcode

> source ~/.zshrc

#### To customise terminal, add in zshrc

> export PS1='sd@tracklib $ '
  
> parse_git_branch() {
git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

> setopt PROMPT_SUBST
PROMPT='% sd@tracklib%{%F{green}%}$(parse_git_branch)%{%F{none}%} $ '


</p>
</details>

<details><summary>Homebrew</summary>
<p>

#### Install homebrew from terminal

> ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

#### Install tree

> brew install tree

</p>
</details>

<details><summary>Python</summary>
<p>

#### Set python3 global, open zshrc

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
  
#### Git GUI
  
> brew install git-gui
  
> gitk
  
> brew install git-cola
  
> git-cola

#### Login (for github not gitlab)

> gh auth login

#### Create project

> cd <project_dir>

##### @ SSH

> git clone git@gitlab.<company_name>.com:saurav/<repo_name>.git

##### @ HTTPS

> git clone https://github.com/sauravdwivedi/<repo_name>.git
  
##### @ CLI
  
> gh repo clone sauravdwivedi/<repo_name>
  
#### Go to repository directory

> cd <repo_name>

#### Initialise connection between project dir and git repository (redundant)

> git init

#### Add remote that tells Git where to push or pull from

> git remote add origin git@github.com:sauravdwivedi/test.git
  
#### Check origin

> git remote -v

#### Download the latest changes in the project from origin repo (<_remote> = origin)

> git pull <_remote> <name_of_branch> # here branch refers to origin branch, from where to pull!

> git pull

#### Create a branch

> git checkout -b <name_of_branch>

#### Switch to a branch

> git checkout <name_of_branch>
  
#### Check current branch
  
> git branch

#### Rename a branch
  
> git branch -m <old_branch_name> <new_branch_name>

#### Work on project, make changes (e.g. load <project_dir> in PyCharm)

#### If you want to UNDO all changes in project, use

> git restore .

#### View differences

> git diff

#### View the files that have changes

> git status

#### Add local changes to staging

> git add <filename_OR_folder_name>

#### Stage all files in the current directory and subdirectory

> git add .

#### Confirm that the files have been added to staging

> git status

#### Undo added files

> git reset <file_name>

#### Remove files

> git rm <file_name>

#### Commit the staged files

> git commit -m "Add via CLI"

#### Send changes to Git (<_remote> = origin)

> git push <_remote> <name_of_branch>

#### Merge a branch with default branch

> git checkout <default_branch>

> git merge <feature_branch>
  
#### Delete feature branch

> git branch -d <feature_branch>
  
#### Delete local repo after repo update
  
> cd ..

> sudo rm -r <repo_name>

</p>
</details>

<details><summary>Flask</summary>
<p>

- [ ] https://flask.palletsprojects.com/

- [ ] https://flask-restful.readthedocs.io/

- [ ] https://flask-restplus.readthedocs.io/

- [ ] https://flask-restx.readthedocs.io/

#### Create and activate virtual environment (e.g. FlaskEnv)

> python -m venv <env_name>

> source <env_name>/bin/activate

#### Install Flask

> pip install Flask

> pip install flask-restful

> pip install flask-restplus

> pip install flask-restx

</p>
</details>

<details><summary>Django</summary>
<p>
  
- [ ] https://docs.djangoproject.com/
  
- [ ] https://www.django-rest-framework.org/

- [ ] https://edu.anarcho-copy.org/Programming%20Languages/Python/Python%20CheatSheet/beginners_python_cheat_sheet_pcc_django.pdf

- [ ] https://youtu.be/rHux0gMZ3Eg

- [ ] https://youtu.be/c708Nf0cHrs

#### Architecture

- [ ] In django, Model is models.py, Controller is views.py and View is called Templates in analogy to MVC architecture.

#### Create and activate virtual environment (e.g. DjangoEnv)

> python -m venv <env_name>

> source <env_name>/bin/activate

#### Create project

> django-admin startproject <project_name> .

#### Create database

> python manage.py migrate

#### View project

> python manage.py runserver <port>

> http://127.0.0.1:8000/admin/

#### Create new app

> python manage.py startapp <app_name>

#### Update app

> cd <app_name>

> open -a Xcode models.py

#### Add app to project

> cd ..

> cd <project_name>

> open -a Xcode settings.py

> add '<app_name>'

#### Migrate updates to database

> cd ..

> python manage.py makemigrations <app_name>

> python manage.py migrate

#### Create a superuser

> python manage.py createsuperuser

#### Register a model with the admin site

> cd <app_name>

> open -a Xcode admin.py

> add 'from .models import <model_name>' and 'admin.site.register(<model_name>)'

</p>
</details>

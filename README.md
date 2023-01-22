# Tech wiki

<details><summary>Terminal</summary>
<p>

### Create z-shell profile

```bash
$ touch ~/.zshrc
$ open ~/.zshrc -a Xcode
$ source ~/.zshrc
```

### To customise terminal, add in zshrc

```
export PS1='sd@tracklib $ '  

parse_git_branch() {
git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

setopt PROMPT_SUBST
PROMPT='% sd@tracklib%{%F{green}%}$(parse_git_branch)%{%F{none}%} $ '
```


</p>
</details>


<details><summary>Homebrew</summary>
<p>

### Install homebrew from terminal

```bash 
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Install tree

```bash 
$ brew install tree
```

</p>
</details>


<details><summary>GitLab/GitHub CLI</summary>
<p>

- [ ] https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html

```bash 
$ brew install gh
$ brew install git
```
  
### Login (for github not gitlab)

```bash 
$ gh auth login
```
  
### Create project

```bash 
$ cd <project_dir>
```
  
#### @ SSH

```bash 
$ git clone git@gitlab.<company_name>.com:saurav/<repo_name>.git
```

#### @ HTTPS
  
```bash 
$ git clone https://github.com/sauravdwivedi/<repo_name>.git
```
    
#### @ CLI

```bash   
$ gh repo clone sauravdwivedi/<repo_name>
```
    
### Go to repository directory
  
```bash 
$ cd <repo_name>
```
  
### Initialise connection between project dir and git repository (redundant)

```bash 
$ git init
```
  
### Add remote that tells Git where to push or pull from

```bash 
$ git remote add origin git@github.com:sauravdwivedi/test.git
```
    
### Check origin

```bash 
$ git remote -v
```
  
### Download the latest changes in the project from origin repo (<_remote> = origin)

```bash 
$ git pull <_remote> <name_of_branch> # here branch refers to origin branch, from where to pull!
$ git pull
```
  
### Create a branch

```bash 
$ git checkout -b <name_of_branch>
```
  
### Switch to a branch

```bash 
$ git checkout <name_of_branch>
```
  
### Check current branch

```bash   
$ git branch
```
  
### Rename a branch

```bash   
$ git branch -m <old_branch_name> <new_branch_name>
```
  
### Work on project, make changes (e.g. load <project_dir> in PyCharm)

### If you want to UNDO all changes in project, use

```bash 
$ git restore .
```
  
### View differences

```bash 
$ git diff
```
  
### View the files that have changes

```bash 
$ git status
```
  
### Add local changes to staging

```bash 
$ git add <filename_OR_folder_name>
```
  
### Stage all files in the current directory and subdirectory

```bash 
$ git add .
```
  
### Confirm that the files have been added to staging

```bash 
$ git status
```
  
### Undo added files

```bash 
$ git reset <file_name>
```
  
### Remove files

```bash 
$ git rm <file_name>
```
  
### Commit the staged files

```bash 
$ git commit -m "Modify feat: Endpoint etc"
```
  
### Send changes to Git (<_remote> = origin)

```bash 
$ git push <_remote> <name_of_branch>
```
  
### Merge a branch with default branch

```bash 
$ git checkout <default_branch>
$ git merge <feature_branch>
```

### Delete feature branch

```bash 
$ git branch -d <feature_branch>
```
  
### Delete local repo after repo update

```bash   
$ cd ..
$ sudo rm -r <repo_name>
```

</p>
</details>

<details><summary>Git Desktop</summary>
<p>

### Install Github Desktop
  
```bash
$ brew install --cask github
```

### Squashing commits
  
- [ ] https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/managing-commits/squashing-commits

### Other Git GUI

```bash   
$ brew install git-gui 
$ gitk
$ brew install git-cola  
$ git-cola
```

</p>
</details>


<details><summary>Flask</summary>
<p>

- [ ] https://flask.palletsprojects.com/

- [ ] https://flask-restful.readthedocs.io/

- [ ] https://flask-restplus.readthedocs.io/

- [ ] https://flask-restx.readthedocs.io/

- [ ] https://flask-smorest.readthedocs.io/

- [ ] https://flask-migrate.readthedocs.io/

### Create and activate virtual environment (e.g. FlaskEnv)
  
```bash
$ python3 -m venv <env_name>
$ source <env_name>/bin/activate
```

### Install Flask
  
```bash
$ pip3 install Flask
$ pip3 install flask-restful
$ pip3 install flask-restplus
$ pip3 install flask-restx
```

### Migrate updates (new models) to database

```
$ export FLASK_APP=app.py
$ flask db init
$ flask db migrate -m "Initial migration."
$ flask db upgrade
```

</p>
</details>


<details><summary>Django</summary>
<p>
  
- [ ] https://docs.djangoproject.com/
  
- [ ] https://www.django-rest-framework.org/

- [ ] https://edu.anarcho-copy.org/Programming%20Languages/Python/Python%20CheatSheet/beginners_python_cheat_sheet_pcc_django.pdf

- [ ] https://youtu.be/rHux0gMZ3Eg

- [ ] https://youtu.be/c708Nf0cHrs

### Architecture

- [ ] In django, Model is models.py, Controller is views.py and View is called Templates in analogy to MVC architecture.

### Create and activate virtual environment (e.g. DjangoEnv)
  
```bash
$ python3 -m venv <env_name>
$ source <env_name>/bin/activate
```
  
### Install django
  
```bash  
$ python3 -m pip install Django
$ pip3 install djangorestframework
```
  
### Create project
  
```bash
$ django-admin startproject <project_name> .
```
  
### Create database

```bash  
$ python3 manage.py migrate
```
  
### View project

```bash  
$ python3 manage.py runserver <port>
$ http://127.0.0.1:8000/admin/
```

### Create new app

```bash  
$ python3 manage.py startapp <app_name>
```

### Update app

```bash  
$ cd <app_name>
$ open -a Xcode models.py
```
  
### Add app to project

```bash  
$ cd ..
$ cd <project_name>
$ open -a Xcode settings.py
$ add '<app_name>'
```

### Migrate updates to database

```
$ cd ..
$ python3 manage.py makemigrations <app_name>
$ python3 manage.py migrate
```

### Create a superuser

```bash  
$ python3 manage.py createsuperuser
```

### Register a model with the admin site

```bash
$ cd <app_name>
$ open -a Xcode admin.py
$ add 'from .models import <model_name>' and 'admin.site.register(<model_name>)'
```

</p>
</details>

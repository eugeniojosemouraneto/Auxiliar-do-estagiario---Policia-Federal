# Starting a Project

## 1. Create a virtual environment
```sh
python -m venv venv
```
This command creates an isolated virtual environment for your project, ensuring dependencies do not interfere with system-wide Python installations.

## 2. Activate the virtual environment
```sh
. venv/bin/activate
```
This activates the virtual environment, allowing installed packages to be used within the project scope.

## 3. Install Django
```sh
pip install django
```
This installs Django in the virtual environment. If needed, update pip before installing Django:
```sh
python -m pip install --upgrade pip
```
This ensures you have the latest version of pip.

---

# Starting Django

## 1. Create the base Django configuration
```sh
django-admin startproject project_name .
```
This initializes a new Django project with default configurations in the current directory.

## 2. Modify settings
Edit `settings.py` to adjust configurations.

## 3. Configure template directory
Modify the `TEMPLATES` setting in `settings.py` to specify a directory for base templates:
```python
'DIRS': [
    BASE_DIR / 'base_templates'
],
```
This allows Django to find your custom templates.

## 4. Set language and timezone
Modify `settings.py` to reflect Brazil's language and timezone:
```python
LANGUAGE_CODE = 'pt-br'
TIME_ZONE = 'America/Sao_Paulo'
```
This ensures the project uses the correct locale settings.

## 5. Configure static files
Add the following variables to `settings.py` to handle static files:
```python
STATICFILES_DIRS = (
    BASE_DIR / 'base_statics',
)
STATIC_ROOT = BASE_DIR / 'static'  # collectstatic
```
This defines directories for static files and where they will be collected when using `collectstatic`.

---

# Starting an App

## Create a new Django app
```sh
python manage.py startapp app_name
```
This generates the necessary structure and files for a Django application.

---

# Other Django Commands

## Activate the virtual environment
```sh
. venv/bin/activate
```
This enables the virtual environment before running any Django commands.

## Run the development server
```sh
python manage.py runserver
```
This starts Django's built-in development server for testing your application.

## Create migrations
```sh
python manage.py makemigrations
```
This creates migration files based on model changes.

## Apply migrations
```sh
python manage.py migrate
```
This applies migration files to the database.

## Create a superuser
```sh
python manage.py createsuperuser
```
This prompts for credentials to create an admin user.

## Collect static files
```sh
python manage.py collectstatic
```
This gathers all static files into the directory specified in `STATIC_ROOT`.

---

# Git Commands

## Initialize a Git repository
```sh
git init
```
This creates a new Git repository in the current directory.

## Add all files to staging
```sh
git add .
```
This stages all new and modified files for the next commit.

## Commit changes
```sh
git commit -m "Initial commit"
```
This saves the staged changes with a commit message.

## Add a remote repository
```sh
git remote add origin <repository_url>
```
This links the local repository to a remote Git repository.

## Push changes to a remote repository
```sh
git push -u origin main
```
This uploads the committed changes to the `main` branch on the remote repository.

## Pull latest changes from the remote repository
```sh
git pull origin main
```
This fetches and merges the latest changes from the remote repository.

## Check repository status
```sh
git status
```
This displays the current state of the working directory and staging area.

## Create and switch to a new branch
```sh
git checkout -b new_branch
```
This creates and moves to a new branch.

## Merge a branch into main
```sh
git checkout main
git merge new_branch
```
This merges `new_branch` into the `main` branch.

## Remove a file from version control
```sh
git rm --cached file_name
```
This removes a file from Git tracking while keeping it in the local directory.

## Undo the last commit
```sh
git reset --soft HEAD~1
```
This reverts the last commit but keeps the changes staged.

---

This guide covers essential Django setup and Git commands to help manage your project efficiently.

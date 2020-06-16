<img src="https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png" style="margin: 0;">

Welcome Thomas,

This is the Code Institute student template for Gitpod. We have preinstalled all of the tools you need to get started. You can safely delete this README.md file, or change it for your own project.

## Gitpod Reminders

To run a frontend (HTML, CSS, Javascript only) application in Gitpod, in the terminal, type:

`python3 -m http.server`

A blue button should appear to click: *Make Public*,

Another blue button should appear to click: *Open Browser*.

To run a backend Python file, type `python3 app.py`, if your Python file is named `app.py` of course.

A blue button should appear to click: *Make Public*,

Another blue button should appear to click: *Open Browser*.

In Gitpod you have superuser security privileges by default. Therefore you do not need to use the `sudo` (superuser do) command in the bash terminal in any of the backend lessons.

## Updates Since The Instructional Video

We continually tweak and adjust this template to help give you the best experience. Here are the updates since the original video was made:

**April 16 2020:** The template now automatically installs MySQL instead of relying on the Gitpod MySQL image. The message about a Python linter not being installed has been dealt with, and the set-up files are now hidden in the Gitpod file explorer.

**April 13 2020:** Added the _Prettier_ code beautifier extension instead of the code formatter built-in to Gitpod.

**February 2020:** The initialisation files now _do not_ auto-delete. They will remain in your project. You can safely ignore them. They just make sure that your workspace is configured correctly each time you open it. It will also prevent the Gitpod configuration popup from appearing.

**December 2019:** Added Eventyret's Bootstrap 4 extension. Type `!bscdn` in a HTML file to add the Bootstrap boilerplate. Check out the <a href="https://github.com/Eventyret/vscode-bcdn" target="_blank">README.md file at the official repo</a> for more options.

--------

Happy coding!

## Deployment

## Intial project setup

pip3 install django

django-admin startproject boutique .

touch .gitignore - to create gitignore file

python3 manage.py runserver - to run project

python3 manage.py migrate - manage migrations

python3 manage.py createsuperuser - create superuser to log into admin

Enter username, email address & password for admin superuser account.


## Allauth setup

pip3 install django-allauth

Go to: https://django-allauth.readthedocs.io/en/latest/installation.html

Confirm that 'django.template.context_processors.request' has been added to the list of 'context_processors' in settings.py

Add the following code beneath 'TEMPLATES' in settings.py:

AUTHENTICATION_BACKENDS = [
    # Needed to login by username in Django admin, regardless of `allauth`
    'django.contrib.auth.backends.ModelBackend',

    # `allauth` specific authentication methods, such as login by e-mail
    'allauth.account.auth_backends.AuthenticationBackend',
]

Add the following to 'INSTALLED APPS':

'django.contrib.sites',
'allauth',
'allauth.account',
'allauth.socialaccount'

Beneath 'AUTHENTICATION_BACKENDS' add the following code:

'SITE_ID = 1'

## Update urls.py file as follows:

Gives us all the urls needed for logins, logouts, password resets etc.

add 'include' to 'from django.urls import path, include' in urls.py file

add 'path('accounts', include('allauth.urls')),' to urlpatterns:

urlpatterns = [
    path('admin/', admin.site.ur
    ls),
    path('accounts/', include('allauth.urls')),
]


Run python3 manage.py migrations to update databases with new apps
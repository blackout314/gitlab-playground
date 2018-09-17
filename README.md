# Tech Lunch | Session 1 | GitLab CI

## Prerequisites

- Git: https://git-scm.com/
- Docker + docker-compose: https://www.docker.com/get-started

## Step-by-step guide

### Start services

Add the following entry to your */etc/hosts* file:

    127.0.0.1       gitlab.session1.techlunch.com

Clone this repository and start the services with docker-compose:

    git clone https://github.com/fagia/tech-lunch-session-1-gitlab-ci.git session-1-gitlab-ci
    cd session-1-gitlab-ci
    docker-compose up -d

You can inspect the GitLab startup logs with:

    docker-compose logs -f gitlab

### Reset GitLab root password

After starting the services, visit the GitLab web GUI here: http://gitlab.session1.techlunch.com:9980/. Since this is the first startup, it might take a while before the GitLab Docker container starts to respond to queries.

Enter and confirm the new password for the newly create user *root*. Click 'Change your password' button.

Now you can log in to the GitLab web GUI with default user 'root' and the password you have just entered.

### Change GitLab's default user username

After you logged in to the GitLab web GUI, click on the top right of your icon profile, and click the 'Settings' icon to setup your profile.

Go to the 'Account' tab and change the default root username with your own username, then click the 'Update username' button.

Now you can log in to the GitLab web GUI with the username you have just entered and the password you have entered before.

### Create a GitLab group

After you logged in to the GitLab web GUI, click on the "Create a group" link. Enter 'tech-lunch' as group path and click 'Create group' button.

### Create a GitLab project

After having create the 'tech-lunch' group, click on the "New project" button. Enter 'hello-world' as project name and click 'Create project' button.

The first time you try to create the project you might see the following error message: '*TODO*', this is due to *TODO*, just click again the 'Create project' button and the new project creation should work fine this time.

## Clean-up

### Stop services

    docker-compose down

### Permanently delete persistent data

    cd .. && rm -Rf session-1-gitlab-ci
#Development Environment
This project serves as the base development environment for the team.

## Setup
- Install Docker.  The method of installation will depend on your environment
consult [https://docs.docker.com/engine/installation/](Docker Installation Guide)
for further details.
- Copy env.sample over to .env and change any values to match your environment.
- Install projects in the projects directory.
- Configure needed nginx vhost files in the docker/sites-enabled directory.
*Note that the path to the projects must be /var/www/html/projects.
- Use the command line utility to bring the environment up.

## Command Line Utility
The env bash file serves as an interface between the docker commands
and your environment.  You may still bind and run all commands manually
using the docker cli tools if you wish.  To list all available commands
and their usage run ./env help.

>Basic Usage:
>- ./dev up-build will build/rebuild the project freshly.  
Use this command when edits have been made to conf files.
>- ./dev down will shut down all containers for the project.
>- ./dev up will bring the project up but will not rebuild any
configuration settings in the environment.  Use this when you
simply want to bring up all projects without environment configuration
changes.

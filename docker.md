# FUN with Docker

We extensively use Docker at FUN. Mostly for developement, but also in production. In this document, you will find a few guidelines on how we write, run and manage our containers.

## System setup \(GNU/Linux only\)

it is commonly assumed that Docker containers **should not** run commands with a privileged account as the `root` user. So it's a good practice to create and declare a `USER` in your `Dockerfile`. When a docker volume is mounted from the host to a container, you may then encounter permission issues with the container's user trying to create new files on the host volume \(_e.g._ when installing dependencies with _npm_\), and this is a good thing! But it is a bit annoying as it may break your development workflow.

A workaround to solve this issue is to: i. create a new group on your system for the user of your container \(mapping container user primary group's `gid`\), ii. create a new user attached to this group on your system \(mapping container user's `uid`\), iii. add your account to this group, and allow this group to write in your project's tree.

An example for CircleCi containers follows:

```bash
# Create a new circleci group
$ sudo groupadd --gid 3434 circleci

# Create the circleci users with uid 3434 (same as in the container)
# and attach him to the circleci group
$ sudo useradd --uid 3434 --gid circleci --shell /usr/sbin/nologin --no-create-home circleci

# Attach your account the docker-users group
$ sudo usermod -aG circleci $USER

# Give the circleci group write permission on our project directory
$ cd /home/me/workdir
$ (sudo) chown $USER:circleci project
$ chmod 775 project
```

Note that depending on your application and what your docker user has to achieve, you may want to make the last two commands \(`chown` & `chmod`\) recursive \(`-R`\).


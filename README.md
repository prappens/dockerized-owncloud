# dockerized-owncloud

Adopted Owncloud Docker setup from the official [Owncloud documentation](https://doc.owncloud.com/server/admin_manual/installation/docker/), and the
corresponding official [Owncloud docs repository](https://github.com/owncloud/docs).

# Why?

Just for fun I wanted to install OwnCloud on an old machine with Docker. I stumbled accross the previously mentioned Docker setup from Owncloud.
I tried it, and disliked some of the implementations within the docker-compose. Therefoer I created this simple adoption.

# What?

I noticed that the official Owncloud docker-compose.yml does not use the official MariaDB and Redis Docker images. In addition to that I noticed
that both images do not use a pinned Docker tag and the created containers are not named. I tackled all those issues and further improved the 
`.env` file which sets the corresponding credentials.

The negative side effect of naming the containers is the fact that only one Owncloud instance can run on a host, since otherwise the names will
be in conflict. From my perspective this is a reasonable tradeoff to have some static names, which enables easier Docker CLI usage.

# How?

The setup and features are basically the same as stated [here](https://doc.owncloud.com/server/admin_manual/installation/docker/), but within this repository
a template file is checked in:

0. Clone repository, or download files.
1. Rename `.env.template` to `.env` and adopt the parameters as you wish.
2. Do a `docker-compose up` in repository directory.
3. Visit your Owncloud instance under your specified Domain.

Try it at your own risk, no warranties!


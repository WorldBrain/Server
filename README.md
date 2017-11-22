# WorldBrain Analytics Server

## Instructions

1. [install Docker CE](https://www.docker.com/community-edition#/download)
2. [install Docker Compose](https://docs.docker.com/compose/install/)
3. make a new `.env` file for `docker-compose` to use __(copy `.env.example` and change as needed)__
4. run `docker-compose up -d analytics` to start up the docker containers in the background
5. visit `localhost:ANALYTICS_HTTP_PORT` in your browser __(where `ANALYTICS_HTTP_PORT` is whatever port number defined in `.env`)__
6. complete Piwik installation wizard

During the Piwik installation wizard, the connection to the DB will need to be set up. When asked, simply set the database server to `db`, `root` for username, and use the root DB password as you specified in `.env`. Db name can be anything.

The DB instance runs on a separate container which is made available to the Piwik container at the hostname `db` (via `docker-compose` conf).

When asked about which site to track, set it  to `worldbrain.io`. This doesn't matter so much as we will set things up more specifically from the extension-side, but still required in the wizard.

The user details asked for in the wizard will be used for logging into the Piwik server dashboard.

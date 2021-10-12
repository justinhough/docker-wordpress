# Docker Wordpress with code-server

Docker Wordpress is a starter project to get started quickly with a fresh install of Wordpress, MySQL and WP CLI. It can be forked and customized for personal builds or for client sites.

## Initial Setup

Ensure that you have Homebrew and Homebrew Cask installed before proceeding.
```sh
# Install Homebrew
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Install Homebrew Cask, VirtualBox, Docker, and WP CLI

```sh
brew install caskroom/cask/brew-cask
brew cask install virtualbox
brew install docker docker-machine
brew install wp-cli
```

## Start Wordpress

1. Duplicate `.sample-env` to `.env` and update for your application
2. Start Wordpress, MySQL and code-server with `docker-compose up -d`. (To stop the container use `docker-compose stop`.)
3. Open a browser `http://localhost:<port_selected>` and finish setting up Wordpress.

**Note:** MySQL databases and schema for Wordpress will be automagically synced into the folder `db/mysql`


### Accessing WP through WP CLI

You can run WP CLI commands through the Docker container using Docker Compose and prefixing all commands with this: `docker-compose run --rm wpcli`. Using `wpcli` at the end is merely the name of the Docker image that is installed in `docker-compose.yml`. You can change this to be anything to make it easier to remember.

**Note:** Full list of commands is listed on the [WP CLI Commands](https://wp-cli.org/commands/) page.

#### Example Commands

- `docker-compose run --service-ports --rm wpcli`
- `docker-compose run --service-ports --rm wpcli post list1`

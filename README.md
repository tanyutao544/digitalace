# DigitaLAce

[![Build Status](https://travis-ci.com/CrownKira/digitalace.svg?branch=main)](https://travis-ci.com/CrownKira/digitalace)
![GitHub](https://img.shields.io/github/license/CrownKira/digitalace)

## Getting Started

### Installation

1. Install a stable version of NodeJS. The active LTS or current version should work fine.
2. Install Docker.

- macOS and Windows users can install [Docker Desktop](https://www.docker.com/products/docker-desktop) which contains both Docker and Docker-Compose tools.
- Linux users need to follow the instructions on [Get Docker CE for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/) and then [Install Docker Compose](https://docs.docker.com/compose/install/) separately.
- You are good to go when you can successfully run:
  `docker-compose --version`

3. Install ModHeader.

- To test our API, we use [Google Chrome](https://www.google.com/chrome/) with the [ModHeader extension](https://chrome.google.com/webstore/detail/modheader/idgpnmonknjnojddfkpgkljpfnnfcklj?hl=en).

4. Run `git clone <url> --recursive` to clone the repository and navigate to it using `cd` in your command line or shell tool.
5. Run `yarn --cwd digitalace-frontend/ install` to install all dependencies for frontend.
6. Run `mkdir pgdata` to create a directory that is used to persist data generated by and used by `db` container.
7. Run `docker compose up --build` to create and run all containers.

- To run a specific service, please refer to [this section](#useful-commands).
- It might take a while for all the servers to be ready when you are running it for the first time. (so please be patient ^.^)

9. Point your browser to http://localhost:3000 to access the frontend.
10. Point your browser to http://localhost:5000 to access the backend.

## Development

### Docker Services

1. `api` running backend server
2. `db` running postgresql server
3. `client` running frontend server

### Useful Commands

- `docker exec -it <container> sh`: to access a running container (Note: this container must be running before you can do this)
- `docker compose run <service> sh -c "<command>"`: to run a one-time command against a service
- `docker compose run --service-ports <service>`: to run a specific service

### Contribution Guidelines

#### As a Collaborator

##### To make a pull request

- `git clone <url> --recursive`
- cd to the project directory
- `git checkout <branch>`
- (make changes)
- `git add .`
- `git commit -m 'commit message'`
- `git push origin <branch>`
- compare and pull request

##### To contribute to a pull request branch

- `git fetch origin pull/<id>/head:<branch>`
- `git checkout <branch>`
- (make changes)
- `git add .`
- `git commit -m 'commit message'`
- `git push origin <branch>`
- compare and pull request

##### To sync your forked repo

(`cd` to the root and `git checkout main`)

- `git remote add upstream <url>`
- `git remote -v` to check that this repo has been added as upstream
- `git reset --hard` to reset all local changes to the latest local commit
- `git fetch upstream`
- `git merge upstream/main`
- `git push origin main`

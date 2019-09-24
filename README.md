# About this Repo

**This image is based node docker official node image :**

- Docker image : [node](https://hub.docker.com/_/node/)
- Github repository : [nodejs/docker-node](https://github.com/nodejs/docker-node)

**Additions :**

- Gulp local and global package

## Supported tags and respective `Dockerfile` links

- `alpine`, `latest` [(alpine/Dockerfile)](https://github.com/slebote/gulp/blob/master/alpine/Dockerfile)

## Docker compose example

Assuming `./theme-folder` contains `gulpfile.js` and `package.json` with gulp node dependencies (ex: gulp-sass)

```
version: "3"
services:
  # Service Node / Gulp
  gulp:
    image: slebote/gulp
    user: node
    working_dir: /home/node/app
    environment:
      - NODE_ENV=dev
    volumes:
      - ./theme-folder:/home/node/app
    command:
      - /bin/sh
      - -c
      - |
          npm install
          gulp
```
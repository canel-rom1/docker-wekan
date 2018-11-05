# 2018-11-05 MOVED

Newest docker-compose.yml has moved to https://github.com/wekan/wekan file docker-compose.yml

# Docker: Wekan <=> MongoDB

* [Wekan kanban board, made with Meteor.js framework, running on
  Node.js](https://wekan.io) -- [GitHub](https://github.com/wekan/wekan)
* [MongoDB NoSQL database](https://www.mongodb.com)

## Screenshot

![Screenshot of Wekan][screenshot]

## Install

1) Install docker-compose.

2) Clone this repo.

```bash
git clone https://github.com/wekan/wekan-mongodb.git
cd wekan-mongodb
```

3a) Detached mode:

```bash
docker-compose up -d
```

3b) Running attached to console, so Ctrl-c stops it:

```bash
docker-compose up
```

4) Wekan is at http://localhost (port 80)

5) MongoDB is at 127.0.0.1:27017

6) Wekan and databases bind to address 0.0.0.0 so could be also available to other
   computers in network. I have not tested this.

7) [Restore your MongoDB data](https://github.com/wekan/wekan/wiki/Export-Docker-Mongo-Data).

## Backup before upgrading

[Backup all data from MongoDB](https://github.com/wekan/wekan/wiki/Export-Docker-Mongo-Data)

## Upgrading Wekan

1) In wekan-mongodb directory, stop Wekan:

```bash
docker-compose stop
```

2) Check what is CONTAINER ID of wekanteam/wekan:latest container. Then remove container.

```bash
docker ps
docker rm CONTAINER-ID-HERE
```

3) Check Docker images, what is IMAGE ID of quay.io/wekan/wekan, and remove quay.io/wekan/wekan image:

```bash
docker images
docker rmi IMAGE-ID-HERE
```

4) If you have made backups of MongoDB container to outside of Docker, and want to upgrade MongoDB, you could also delete MongoDB container and image.

5) Start Wekan again in background:

```bash
docker-compose up -d
```

6) You can also check container logs:

```bash
docker ps
docker logs CONTAINER-ID-OF-Wekan-or-MongoDB-HERE
```

7) Restore MongoDB data if needed.

## Feedback

[Create GitHub issue](https://github.com/wekan/wekan/issues)

[screenshot]: https://wekan.github.io/screenshot.png


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

## Feedback

[Create GitHub issue](https://github.com/wekan/wekan/issues)

[screenshot]: http://i.imgur.com/OCtpqb6.png


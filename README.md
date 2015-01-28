docker-lamp
===========

This Docker image allows to quickly run a web application based on a full LAMP stack (Linux, Apache, MySQL, PHP).

![Build status](https://circleci.com/gh/fbenard/docker-lamp/tree/master.svg?style=shield&circle-token=1e6b07920fa6676dafe860d85dbd9674b02ff456)


## Install

You must have Docker installed on your machine prior to using this image.

To install the binary `docker-lamp`, run:

```
curl -sS https://raw.githubusercontent.com/fbenard/docker-lamp/master/install.sh | sudo bash
```


## Getting started

Run your web application inside the docker-lamp image:

```
cd myapp
docker-lamp
```

Once inside the container, start services:

```
start.sh
```

Edit your hosts so that app.local is forwarded to the IP address of the Docker container.

```
x.x.x.x    app.local
```

Then open you browser and visit:

http://app.local


# Bind services

By default all services are bound to the Docker container on default ports:

- Apache on port 80
- MySQL on port 3306
- Redis on port 6379

However if you need to either remove binding of a service or to map it to a different port, you can do so with the `-b` option. For instance,

- To bind only Apache on port 8080:

```
docker-lamp -b "apache:8080"
```

- To bind Apache and MySQL on default ports:

```
docker-lamp -b "apache|mysql"
```

- To bind Apache on default port and MySQL on port 3000:

```
docker-lamp -b "apache|mysql:3000"
```


## Services

**MySQL**

- Login: `root`
- Password: `root`

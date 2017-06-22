+++
date = "2017-06-22T00:13:18-05:00"
title = "Configure Colmena"
toc = true
weight = 5

+++


## Development servers

Colmena comes with a MongoDB and Mailhog development server that run inside Docker.

When MongoDB is not configured Colmena will use the in-memory database.
This means that all the data is gone each time the API server restarts, and in order to be useful you'd have to run Colmena with `initdb` mode on, which slows down API start significantly.

> It's recommended to run Colmena in development mode on MongoDB. 

```bash
npm run servers:start
```


## Create a local configuration file


The API of Colmena is configured by [node-config](https://github.com/lorenwest/node-config/) and the configuration files
are located in `apps/api/config`. 


To configure the API in local development create a copy of `default.yaml` to `local.yaml`:

```
cp apps/api/config/default.yaml apps/api/config/local.yaml
```


> The file local.yaml is ignored by Git so it won't be committed to your repository.


## Configure MongoDB and Mailhog


Update `apps/api/config/local.yaml` to define the development database- and mailserver.

```
mongodb:
  url: mongodb://localhost/ngatl

smtp:
  host: localhost
  port: 1025
```


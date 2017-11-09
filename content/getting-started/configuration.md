+++
date = "2017-06-22T00:13:18-05:00"
title = "Configuration"
toc = true
weight = 5

+++

## Create a local configuration file


The API of Colmena is configured by [node-config](https://github.com/lorenwest/node-config/) and the configuration files
are located in `config`. 


To configure the API in local development create a copy of `default.yaml` to `local.yaml`:

```
cp config/default.yaml config/local.yaml
```


> The file local.yaml is ignored by Git so it won't be committed to your repository.


## Development servers

Colmena comes with a MongoDB and Mailhog development server that run inside Docker. 

Start the servers by running:

```bash
npm run servers:start
```

Other commands to interact with the servers:

```bash
npm run servers:stop    # Stop the servers
npm run servers:logs    # Show and tail the output of the server logs
npm run servers:rm      # Removes the Docker instances of these servers
```

You can of course use your own servers if you can't or don't want to use these servers.

### MongoDB

#### **It's recommended to run Colmena in development mode on MongoDB.**
 
When MongoDB is not configured Colmena will use the in-memory database, this means that all the data is gone each time
the API server restarts. 

This means that in order to be useful you'd have to run Colmena with `initdb` mode on, which slows down API start significantly.

To configure MongoDB add the following lines to  `config/local.yaml` :

```yaml
mongodb:
  url: mongodb://localhost/colmena-dev
```

### Mailhog

Mailhog is an SMTP-server with a web interface that is useful for testing the email functionality of your API.

It's not required to configure Mailhog but it is recommended.

To configure Mailhog add the following lines to  `config/local.yaml` :

```
smtp:
  host: localhost
  port: 1025
```


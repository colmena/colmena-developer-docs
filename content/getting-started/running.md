+++
date = "2017-06-22T00:13:18-05:00"
title = "Running"
toc = true
weight = 5

+++
## Seed DB with sample data

When first starting Colmena it's useful to import the sample data.

In order to get some sample data in the database we run the `npm run initdb` command:

```
npm run initdb
```

> 💡 This assumes you are running Colmena connected to MongoDB. If you are using the in-memory database you need to run
the sample data on server start by setting `initdb` to `true` in `config.yaml`, or by setting the environment variable
`INITDB=true`.




## Start Colmena in Development mode

After installation and configuration you can start Colmena by running the following command from the project root: 

```
npm run dev
```

You should now see the Colmena API and Admin starting. 

The API will listen on [http://127.0.0.1:3000](http://127.0.0.1:3000) and the API explorer is found here [http://127.0.0.1:3000/explorer](http://127.0.0.1:3000/explorer)

When the admin is built it can be accessed on [http://127.0.0.1:9000](http://127.0.0.1:9000).



## Run the apps independently

Sometimes it can be useful to run the API and Admin in separate terminals. 

To start only the API move into the director and run `npm run dev`:

```bash
cd apps/api
npm run dev
```

To start only the Admin move into the director and run `npm run dev`:

```bash
cd apps/admin
npm run dev
```

## Make sure Colmena is working 

When there are no build errors in the log, and you see the message `Webpack: Compiled successfully.` you should be able to log in on [http://127.0.0.1:9000](http://127.0.0.1:9000). Because the server is running in development mode, the default credentials will be displayed. 

After logging in you should see the sample content like pages, files, etc that are all part of the defailt 'domain'.
 

## Help, I'm stuck!

If you are stuck please refer to the [support page](../../introduction/support/)
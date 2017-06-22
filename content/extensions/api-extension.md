+++
date = "2017-06-22T00:13:18-05:00"
title = "API Extension"
toc = true
weight = 1

+++

## Installing an API Extension

- Download and extract the [Colmena Starter](https://github.com/colmena/colmena-starter/archive/master.zip) 
into the `extensions` folder of your Colmena installation.

- Run `lerna ls` in the Colmena project root and verify that it lists the entry **@colmena/module-api-starter** 

- Open the file `apps/api/package.json` and add this line to the `dependencies` array:


```json
"@colmena/module-api-starter": "0.0.0",
```

- Run `lerna bootstrap` from the project root to link the new package to the API.

## Configure the LoopBack API

- Open the file `apps/api/config/default.yaml` and add this line to the `colmena.modules` object. This makes sure the API
loads the new module.

```yaml
colmena:
  modules:
    ...
    '@colmena/module-api-starter': true
    ...
```


- Start the API by running `npm run dev:api` from the project root. 

- If the module is installed successfully you should see this message:

```
[loopback-modules] Registering models from module: @colmena/module-api-starter
```

- Open the API Explorer [http://127.0.0.1:3000/explorer/](http://127.0.0.1:3000/explorer/) and verify the two new
API endpoints, `Starter` and `StarterItems`.


## Load the sample data

The starter kit comes with sample data. To load this data run:

```bash
npm run initdb
```

Please note that this will wipe any data from the development database!

## Generate the LoopBack SDK

Now that the endpoint is working we need to update the LoopBack SDK. This makes sure that the
[Admin Extension](./admin-extension) can easily consume the new endpoints.

In order to re-generate the LoopBack SDK run the following command from the project root:

```bash
npm run sdk
```

This will output a list of newly generated files. These files should be committed to the project as they describe the
structure of the API.

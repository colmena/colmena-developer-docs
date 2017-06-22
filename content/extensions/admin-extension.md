+++
date = "2017-06-22T00:13:18-05:00"
title = "Admin Extension"
toc = true
weight = 2

+++

## Installing an Admin Extension

- Make sure to finish the previous chapter about installing an [API Extension](./api-extension)

- Run `lerna ls` in the Colmena project root and verify that it lists the entry **@colmena/module-admin-starter** 

- Open the file `apps/admin/package.json` and add this line to the `dependencies` array:


```json
"@colmena/module-admin-starter": "0.0.0",
```

- Run `lerna bootstrap` from the project root to link the new package to the API.


## Configure the LoopBack Application


- Open the file `apps/admin/src/app/extensions.module.ts` 


- Add the import statement to the top of this file

```typescript
import { StarterConfigModule } from '@colmena/module-admin-starter'
```

- Add the `StarterConfigModule` to the *imports* array:

```typescript
@NgModule({
  imports: [
    ExtensionsRoutingModule,

    StarterConfigModule
  ],
})
export class ExtensionsModule {}
```

- Open the file `apps/admin/src/app/extensions-routing.module.ts` 

- Add the module to the *routes* array:

```typescript
const routes: Routes = [
  { path: '', loadChildren: '@colmena/module-admin-starter#StarterModule' },
]
```


- Start the Admin by running `npm run dev:admin` from the project root. 

- Make sure the API is also running

- Navigate to [http://127.0.0.1:9000](http://127.0.0.1:9000), log in and verify 
that there is a new entry in the sidebar called *Starter*.

## Done!

By downloading and extracting one file, changing 5 project files and running some commands you've enabled a custom
playground for API and Admin development.

You can now go ahead and customize the both modules. Both the API and the Admin should pick up any changes.

You might have to restart the stack once in a while if it gets stuck with errors (`ctrl-c` -> `npm run dev`).

This mostly happens when renaming or moving files around in the project.

#### Don't hesitate to [join our slack channel](http://colmena-slack.now.sh/) and ask for help there. 


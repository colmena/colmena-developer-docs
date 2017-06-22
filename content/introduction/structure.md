+++
date = "2017-06-22T01:09:18-05:00"
title = "Structure"
toc = true
weight = 2

+++

## Mono Repo

The project is a mono-repo managed by [lerna](https://lernajs.io). This means that the complete project and all it's 
related sub-projects live in 1 Git repository. There are several benefits to doing this, especially when using lerna.

Lerna manages the packages in the repository and makes them available to each other. This means you can use software
from your local repository like any other Node package you'd download from NPM.

Additionally Lerna can take care of the publishing, versioning and tagging of the packages.

## Directory Structure
It is structured like this:

-   `apps/`
    -   `admin` The **Admin interface** built with Angular.
    -   `api` The **REST API** built with LoopBack.
-   `extensions/` **Here is where YOUR magic happens.**
-   `modules/`
    -   `admin/*` Modules that **add routes** to the Admin interface.
    -   `api/*` Modules that **add endpoints** to the API.
-   `packages/`
    -   `*` Functionality used by the Admin, the API and their Modules.



> 💡 The difference between an *extension* and a *module* is that modules come with Colmena. 
So extensions are nothing more than custom or third-party modules.


## Credits

The structure of this project is inspired by this great example: [OasisDigital/scalable-enterprise-angular](https://github.com/OasisDigital/scalable-enterprise-angular).

+++
date = "2017-06-22T00:13:18-05:00"
title = "Requirements"
toc = true
weight = 1

+++

## Software installed on your system:

Colmena is written in JavaScript using [NodeJS](https://nodejs.org/) and [NPM](https://www.npmjs.com/).

The minimal versions required are Node v6.9.x or higher and NPM v3.x or higher.

Use the following commands to verify the versions installed:

```bash
node -v
npm -v
```

If you don't have NodeJS and NPM installed on your machine please [download](https://nodejs.org/en/download/) and install it.

## Globally installed Node packages:

Once you have NodeJS and NPM installed it's time to install a couple of *global dependencies*.

Colmena expects the following packages to be installed globally:

-   [Lerna](https://github.com/lerna/lerna)
  - Manage the project mono repo and package inter-dependencies.
-   [Angular CLI](https://github.com/angular/angular-cli)
  - Run, build and test Angular applications.

```bash
npm install -g lerna @angular/cli
```

Use the following commands to verify the packages are installed:

```bash
lerna -v
ng -v
```

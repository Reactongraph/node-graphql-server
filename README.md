# node-graphql-server

## Requirements

To run this project, you will only need Node.js, Postgres, Graphql installed on your environement.
You can use the appropriate Editorconfig plugin for your Editor (not mandatory).

### Node

[Node](http://nodejs.org/) is really easy to install & now include [NPM](https://npmjs.org/).
You should be able to run the following command after the installation procedure
below.

    $ node --version
    v10.14.2

    $ npm --version
    6.4.1

#### Node installation on OS X

You will need to use a Terminal. On OS X, you can find the default terminal in
`/Applications/Utilities/Terminal.app`.

Please install [Homebrew](http://brew.sh/) if it's not already done with the following command.

    $ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"

If everything when fine, you should run

    brew install node

#### Node installation on Linux

    sudo apt-get install python-software-properties
    sudo add-apt-repository ppa:chris-lea/node.js
    sudo apt-get update
    sudo apt-get install nodejs

#### Node installation on Windows

Just go on [official Node.js website](http://nodejs.org/) & grab the installer.
Also, be sure to have `git` available in your PATH, `npm` might need it.

---

#### Postgres installation on Linux

Just go on [official postgresql website](https://www.postgresql.org/) & grab the database.

---

## Install

    $ git clone https://github.com/Reactongraph/node-graphql-server.git
    $ cd node-graphql-server
    $ npm install

#### or

    $ yarn

### Configure app

Edit `config.json` inside config folder with the url where you have setup:

- Postgres username, password
- Postgres database name
- Project host

## Start & watch

### To run in development

    $ sudo yarn dev

#### or

    $ sudo npm dev

#### To run in production

    $ sudo yarn start

#### or

    $ sudo npm start

## Postgres Relations

#### Postgres Model Creation

    $ sequelize model:create --name Relation_Name --attributes attribute_name:attribute_type
    ex: sequelize model:create --name User --attributes username:string,password:string

#### Database migration

    $ sequelize db:migrate

## Update sources

Some packages usages might change so you should run `npm prune` & `npm install` often.
A common way to update is by doing

    $ git pull
    $ npm prune
    $ npm install

To run those 3 commands you can just do

    $ npm run pull

**Note:** Unix user can just link the `git-hooks/post-merge`:

## Enable git hooks (unix only :/)

    $ npm run create-hook-symlinks

### `post-merge` (≃ `npm install`)

This hook will `npm prune && npm install` each time you `git pull` something if the `package.json` has been modified.

### `pre-commit` (≃ `npm test`)

This hook will just ensure you will commit something not broken bye pruning npm packages not in the `package.json` & eventually reinstall missings/not correctly removed packages.
Then it will try a production build.

---

## Languages & tools

### HTML

- [Jade](http://jade-lang.com/) for some templating.

### JavaScript

- [ESLINT](https://eslint.org/) is used to prevent JavaScript and JSX error.
- [express](https://expressjs.com/) is a web framework for Node.js.
- [graphql](https://graphql.org/) is a query language to handle request.
- [sequelize](http://docs.sequelizejs.com/) a promise-based ORM for Node.js
- [React](http://facebook.github.io/react) is used for UI.

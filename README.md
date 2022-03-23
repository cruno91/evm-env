# Ethereum Virtual Machine (evm) Development Environment (env)

## About
A local Lando-based environment to build, test, and run EVM projects.

By using this starter development environment it is possible to avoid ever
installing common dependencies locally (like NodeJS), keeping host machines 
clean and storage space easy to manage.

## Prerequisites
- [Lando](https://lando.dev/download/) and [its dependencies](https://docs.lando.dev/getting-started/installation.html)

## Usage
- Run `lando start` to spin up the service containers
- Run `lando stop` to turn off the service containers

For more information on Lando see [their docs](https://docs.lando.dev/).

# Tooling
Some tooling is built in to avoid having to SSH into container services by piping
them the `lando` command from the host machine.
###node 
> Runs from the appserver service with `lando node`

###npm 
> Runs from the appserver service with `lando npm`

###npx 
> Runs from the appserver service with `lando npx`

###truffle 
> Runs from the appserver service with `lando truffle`

###ganache-cli 
> Runs from the appserver service with `lando ganache-cli`

###nx 
> Runs from the remix service with `lando nx

# Services

### appserver
Where most of your code will probably live.  It runs on NodeJS version 
16 and contains the tools for npm, truffle, and ganache-cli out of the box.

### remix
Where most of your development will probably occur.  It runs on NodeJS version
14, which is the requirements for 
[Remix IDE](https://github.com/ethereum/remix-project).  

It would probably be better to just run the Remix IDE Desktop client or 
something like WebStorm with its Solidity plugin, but it's included here 
nonetheless.

The Remix IDE takes a _while_ to build (at least on an M1 Macbook Air).

If you don't want the Remix IDE, just comment out the `remix` portion of
`.lando.yml`.
# Screeps Typescript Starter

The International's take on the screeper's [Screeps Typescript Starter](https://github.com/screepers/screeps-typescript-starter) is a starting point for a Screeps AI written in Typescript. It provides everything you need to start writing your AI whilst leaving `main.ts` as empty as possible.

Much of the code and readme components from the screeper's starter has been cloned for this repository. We've added additional tools like a performance server and unified credentials to make your development process easier.

## Requirements

You will need:

- [Node.JS](https://nodejs.org/en/download) (10.x || 12.x)
- A Package Manager ([Yarn](https://yarnpkg.com/en/docs/getting-started) or [npm](https://docs.npmjs.com/getting-started/installing-node))
- Rollup CLI (Optional, install via `npm install -g rollup`)

Begin by cloning this repository. Then open the folder in your terminal and run your package manager to install the required packages and TypeScript declaration files:

```bash
# npm
npm install

# yarn
yarn
```

Fire up your preferred editor with typescript installed and you are good to begin development!

### Usage

Using [rollup](https://rollupjs.org/guide/en/) we will translate the code into a single js file, which will be used in environments set in `.screeps.yaml` file (see below if you don't have one yet). This compiles the code so it can be run by Screeps while we develop using folders and typescript.

First, rename `.screeps.yaml.example` to `.screeps.yaml` and fill in the required information for each environment you want to run the bot in. For the official server, replace the `token` with an [API token](https://docs.screeps.com/auth-tokens.html) for your account. On private servers, edit *(or copy and rename)* the `pserver` section with `host` set to your server domain or IP then complete `username` and `password` with your credentials on this server. For more information about this file, check the [screeps unified credentials file](https://github.com/screepers/screepers-standards/blob/master/SS3-Unified_Credentials_File.md) spec.

Running `rollup -c` will compile your code and do a "dry run", preparing the code for upload but not actually pushing it. Running `rollup -c --environment DEST:mmo` will compile your code, and then upload it to a screeps server using the `mmo` config from `.screeps.yaml`.

You can use `-cw` instead of `-c` to automatically re-run when your source code changes - for example, `rollup -cw --environment DEST:main` will automatically upload your code to the `mmo` configuration every time your code is changed.

Finally, there are also NPM scripts that serve as aliases for these commands in `package.json` for IDE integration. Running `npm run push-mmo` is equivalent to `rollup -c --environment DEST:mmo`, and `npm run watch-pserver` is equivalent to `rollup -cw --dest pserver`.

#### Important! To upload code to a private server, you must have [screepsmod-auth](https://github.com/ScreepsMods/screepsmod-auth) installed and configured!

## Typings

The type definitions for Screeps come from [typed-screeps](https://github.com/screepers/typed-screeps). If you find a problem or have a suggestion, please open an issue there.

## Documentation

We've also spent some time reworking the documentation from the ground-up, which is now generated through [Gitbooks](https://www.gitbook.com/). Includes all the essentials to get you up and running with Screeps AI development in TypeScript, as well as various other tips and tricks to further improve your development workflow.

Maintaining the docs will also become a more community-focused effort, which means you too, can take part in improving the docs for this starter kit.

To visit the docs, [click here](https://screepers.gitbook.io/screeps-typescript-starter/).

## Contributing

Issues, Pull Requests, and contribution to the docs are welcome and encouraged!

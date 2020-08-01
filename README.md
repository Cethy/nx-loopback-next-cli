# nx-loopback-next-cli (@loopback/cli fork)

[Nx](https://nx.dev/) friendly [@loopback/cli](https://github.com/strongloop/loopback-next/tree/master/packages/cli) (official CLI for LoopBack 4)

## Installation

Run the following command to install the CLI.

```sh
yarn add nx-loopback-next-cli
```

## Basic Use

Run `nx-lb4 --commands` or `nx-lb4 -l` to list all available commands:

See [CLI reference](https://loopback.io/doc/en/lb4/Command-line-interface.html)
for a detailed documentation.

## Usage w/ loopback 4

1. Generate a loopback app w/ [nx-loopback-next](https://www.npmjs.com/package/nx-loopback-next) ;
2. Update your `workspace.json` file :

```json
{
  "projects": {
    "{{YOUR_PROJECT}}": {
      // ...
      "architect": {
        // ...
        "model": {
          "builder": "@nrwl/workspace:run-commands",
          "options": {
            "command": "nx-lb4 model --appDir={{YOUR_PROJECT}}"
          }
        }
      }
    }
  }
}
```

3. Use the new command :

```sh
nx model gateway
```

## Changes from official repo

- `artifact-generator` gets a new option `appDir` (default: `process.cwd()`) ;
- Every generators making use of `utils.sourceRootDir` are updated to prepend `appDir` ;

### "Fixed" commands

- [x] model
- [x] interceptor
- [x] observer
- [ ] openapi
- [x] relation
- [x] repository
- [ ] rest-crud
- [x] service

## License

MIT

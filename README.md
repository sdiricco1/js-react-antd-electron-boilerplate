# Boilerplate for react, ant design and electron using javascript

## Installation

You may need `yarn`, another package manager as `npm`. If you have already installed `npm` type:
```bash
npm i yarn -g 
```
Then, install node_modules:
```bash
yarn install
```

## Usage

To start electron app launch:
```bash
yarn electron:serve
```
To build app for current operating:
```bash
yarn electron:build
```

## Debug main process

If you want to debug the main process throw electron, using vs code, you can add to your launch.json following configuration:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Main Process",
      "type": "node",
      "request": "launch",
      "cwd": "${workspaceFolder}",
      "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron.cmd"
      },
      "args" : ["."],
      "outputCapture": "std"
    }
  ]
}
```

Now you have to start only the renderer process throw:

```bash
yarn start
```

Then you can click `Run & Debug` in VS code to start the debugger.
Note that the debug can run only the main Process not the renderer process.
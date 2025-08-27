# Contributing to the JupyterHub extension for Cursor

---

| `main` branch |
| ------------- |

## | ![Main Build](https://github.com/zeckem19/cursor-jupyter-hub/actions/workflows/build-test.yml/badge.svg?branch=main)

## Contributing a pull request

### Prerequisites

1. [Node.js](https://nodejs.org/) v20.18.2
2. [npm](https://www.npmjs.com/) 10.8.2
3. [Python](https://www.python.org/) 3.8 or later
4. Windows, macOS, or Linux
5. Cursor IDE (or VS Code) for development
6. The following extensions:
    - [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
    - [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
    - [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
    - [Python Extension Code](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
    - Jupyter Extension (`ms-toolsai.jupyter`)
    - [TypeScript + Webpack Problem Matchers](https://marketplace.visualstudio.com/items?itemName=amodio.tsl-problem-matcher)

### Setup

```shell
git clone https://github.com/zeckem19/cursor-jupyter-hub
cd cursor-jupyter-hub
npm install
```

### Incremental Builds

* Run `npm run esbuild-node-watch` for desktop version of extension
* Run `npm run esbuild-web-watch` for desktop version of extension
* Run `npm run test-compile-watch` for compilation of tests for the desktop as well as some scripts required for Web Tests
* Run `npm run test-compile-wepack-watch` for compilation of tests for the web

### Errors and Warnings

TypeScript errors and warnings will be displayed in the `Problems` window of your editor.
Best to use the command `npm run test-compile-watch` to get `Problems` showing up in the `Problems` window.

### Run dev build and validate your changes

To test changes locally, use `npm run esbuild-node-watch` and `npm run esbuild-web-watch`, then launch an Extension Development Host from your editor.

### Running Desktop Tests

* Setup and start Jupyter Hub locally
    * Update the `./build/jupyterhub_config.py` to replace `runner` with the username of the current computer
    * Launch JupyterHub via the CLI `python -m jupyterhub --config <fully qualified path to Jupyter Hub repo>/build/jupyterhub_config.py`
    * Verify Jupyter Hub is running and listening at `http://localhost:8000`
* Run the script `npm run esbuild-node-watch`
* Run the script `npm run test-compile-watch`
* From within your editor run the launch option `Tests`


### Running Web Tests

* Setup and start Jupyter Hub locally
    * Update the `./build/jupyterhub_config.py` to replace `runner` with the username of the current computer
    * Launch JupyterHub via the CLI `python -m jupyterhub --config <fully qualified path to Jupyter Hub repo>/build/jupyterhub_config.py`
    * Verify Jupyter Hub is running and listening at `http://localhost:8000`
* Run the script `npm run esbuild-web-watch`
* Run the script `npm run test-compile-watch`
* Run the script `npm run test-compile-webpack-watch`
* From the terminal run the command `npm run test:web`

### Standard Debugging

Clone the repo into any directory, open that directory in Cursor/VS Code, and use the `Build and launch` launch option.

### Coding Standards

We follow common TypeScript/ESLint/Prettier conventions for this repository.

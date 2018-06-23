# Fragment.Network Dapp Agreements

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)

# Install
This project requires nodejs environment with installed yarn.
```
yarn # install all dependencies
```

# Use
```
yarn build # builds whole project

# development
yarn test # run tests on smart contract (build all first)
yarn watch # watch for changes in files and rebuilds project everytime
yarn guiServer # serves testing gui at localhost:8080
```

When running `guiServer` you should be able to access demos at http://localhost:8080/src/gui/
e.g. [taskRequesterDemo](http://localhost:8080/src/gui/taskRequesterDemo.html).

## Testing
For tests to work you need to run [Ganache](https://github.com/trufflesuite/ganache) and provide
Ethereum RPC at http://127.0.0.1:7545 (Ganache's default). Ganache is not included in this package
due to unstability of Ganache's NPM package(installing the newest AppImage is prefered).

# Troubleshooting

## Development
Dependencies in alpha/beta versions might be unstable. When encountering any strange error after dependency update
try to set fixed version of *Web3js* and/or *Ganache* to older ones.
https://github.com/ethereum/web3.js/issues/966

### Ganache
Unstable results for tests using ganache have been observed. It seems like there is some transaction concurency problem.
Also when using ganache-core Promise.catch() are not called when transaction fails. When using Ganache AppImage
everything works fine.

### Dependency Bugs
There is problem with `ts-node` package v 6.x.x and had to be downgraded to 5.0.1. Issue can be tracked at https://github.com/TypeStrong/ts-node/issues/573.

# Suply Chain

## Getting started

### [Download starter code](https://github.com/udacity/nd1309-Project-6b-Example-Template)

### Install Truffle
```
sudo npm install -g truffle
truffle version
```

### Prevents `Error: error:0308010C:digital envelope routines::unsupported`
```
export NODE_OPTIONS=--openssl-legacy-provider
```

### Generate `truffle-config.js`
```
truffle init
```

### Fix outdated code
1. Find and replace `pragma solidity...` by `pragma solidity ^0.8.15;`
2. Add `// SPDX-License-Identifier: UNLICENSED` before `pragma solidity...`
3. Add `memory` between the `string` and the parameter name in `function` declarations and `returns`

### Compile
```
truffle develop
compile
```
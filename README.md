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

### Try to compile
```
truffle develop
compile
```

### Fix obsolete code
1. Find and replace `pragma solidity...` by `pragma solidity ^0.8.15;`
2. Add `// SPDX-License-Identifier: UNLICENSED` before `pragma solidity...`
3. Replace `string` by `string memory` in `function` declarations and `returns`
4. Remove `public` and `internal` from `constructor`
5. `transfer()` and `selfdestruct()` are not available for `address`, but for `address payable` only
6. if necessary, use `payable()` to convert an `address` to `address payable` 
7. comment unused variables
8. convert a few functions from `view` to `pure`


### Compile
```
truffle compile
```



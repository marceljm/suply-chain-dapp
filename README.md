# Architect a Blockchain Supply Chain Solution

## Write Up

### UML

> Project write-up include the following UML diagrams: Activity, Sequence, State and Classes (Data Model)

![Activity diagram](https://github.com/marceljm/supply-chain-dapp/blob/main/uml/activity.png)

---

![Sequence diagram](https://github.com/marceljm/supply-chain-dapp/blob/main/uml/sequence.png)

---

![State diagram](https://github.com/marceljm/supply-chain-dapp/blob/main/uml/state.png)

---

![Class diagram](https://github.com/marceljm/supply-chain-dapp/blob/main/uml/class.png)

### Libraries

> If libraries are used, the project write-up discusses why these libraries were adopted.

No libraries used.

### IPFS

> If IPFS is used, the project write-up discusses how IPFS is used in this project.

IPFS not used.

### General

> A general write up exists to items like steps and contracts address. 

<-------------- TODO ----------------

## Write smart contracts with functions

### SupplyChain.sol contains required tracking functions.

> Smart contract implements functions to track. For example: Product ID, Product UPC,Origination Information, Farm, Misc organization info, Longitude & Latitude of geo coordinates and Product notes.

`fetchItem...` functions implemented in `SupplyChain.sol`.

### Ownable.sol contains required functions that establish owner and the transfer of ownership.

> Ownable.sol has required functions that establish owner and the transfer of ownership.

:white_check_mark:

### ConsumerRole.sol contains required functions that manage the consumer role.

> ConsumerRole.sol has required functions that manage the consumer role.

:white_check_mark:

### RetailerRole.sol contains required functions that manage the consumer role.

> RetailerRole.sol has required functions that manage the consumer role.

:white_check_mark:

### DistributorRole.sol contains required functions that manage the consumer role.

> DistributorRole.sol has required functions that manage the consumer role.

:white_check_mark:

### Additional roles implemented are integrated correctly. 

> Student has implemented additional roles correctly. 

:white_check_mark:

## Test smart contract code coverage

### Test smart contract tests all required functions.

> Project contains tests for the boiler plate functions and all tests are approved without error.

Tests implemented in `TestSupplychain.js`.

## Deploy smart contract on a public test network (Rinkeby)

### Deploy smart contract on a public test network.

> Smart contract is deployed on on the Ethereum RINKEBY test network.

<-------------- TODO ----------------

### Project submission includes transaction ID and contract address

> Project submission includes a document (.md, .txt) that includes Transaction ID and Contract address. Hint: You can view Transaction ID and Contract ID from a blockchain explorer (e.g. Etherscan). Example Contract ID: https://rinkeby.etherscan.io/address/0xfb0720c0715e68f80c0c0437c9c491abfed9e7ab#code

<-------------- TODO ----------------

## Modify client code to interact with a smart contract

### Client code interacts with smart contract.

> Front-end is configured to: Submit a product for shipment (farmer to the distributor, distributor to retailer, etc); Receive product from shipment; Validate the authenticity of the product.

<-------------- TODO ----------------

## Roadmap

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
9. replace `toWei` by `utils.toWei` and convert the values using `String()`
10. and more...

### Write the missing code

### Compile
```
truffle compile
```

### Test
```
truffle test
```

### Migrate
```
./ganache-2.5.4-linux-x86_64.AppImage
truffle migrate
```


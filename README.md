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

- web3.js: collection of libraries that allow you to interact with a local or remote ethereum node using HTTP, IPC or WebSocket.
- truffle: a world-class development environment, testing framework and asset pipeline for blockchains using the Ethereum Virtual Machine (EVM), aiming to make life as a developer easier.

### IPFS

> If IPFS is used, the project write-up discusses how IPFS is used in this project.

IPFS not used.

### General

> A general write up exists to items like steps and contracts address. 

Contract addresses:
- FarmerRole: 0xCe39011C2A0261A85768D8Dd1aC6A0d40cb69b0f
- DistributorRole: 0x26E2Cc4BdB3798956Baa6CBCdc55617A707D78e3
- RetailerRole: 0x6087469d80921E74f285120C349195EF2726e203
- ConsumerRole: 0x4b400f80F29ccb841857C8Fd366dBFb63229A0fB
- SupplyChain: 0x9735cee8A54Cee13DbEd7F77F64B43A4032e2A6D

All the steps are listed on the `Roadmap` section below.

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

```
migrate --reset --network rinkeby
```

### Project submission includes transaction ID and contract address

> Project submission includes a document (.md, .txt) that includes Transaction ID and Contract address. Hint: You can view Transaction ID and Contract ID from a blockchain explorer (e.g. Etherscan). Example Contract ID: https://rinkeby.etherscan.io/address/0xfb0720c0715e68f80c0c0437c9c491abfed9e7ab#code

- Transaction ID: 0xb254e409c6ca057df1febe3402b44535092594949662c8cd15fb44604c0b7af4
- Contract Address: 0x9735cee8A54Cee13DbEd7F77F64B43A4032e2A6D
- [Etherscan](https://rinkeby.etherscan.io/address/0x9735cee8A54Cee13DbEd7F77F64B43A4032e2A6D)

## Modify client code to interact with a smart contract

### Client code interacts with smart contract.

> Front-end is configured to: Submit a product for shipment (farmer to the distributor, distributor to retailer, etc); Receive product from shipment; Validate the authenticity of the product.

:white_check_mark:s

## Roadmap

### [Download starter code](https://github.com/udacity/nd1309-Project-6b-Example-Template)

### Install Truffle
```
sudo npm install -g truffle
npm install --save  @truffle/hdwallet-provider
npm install web3 --save
npm install @truffle/contract --save
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
:white_check_mark:s

### Compile
```
truffle develop
compile
```

### Test
```
test
```

### Migrate
Local:
```
migrate --reset
```

Rinkeby:
```
migrate --reset --network rinkeby
```

### Additional steps for Rinkeby

- Create [faucets](https://rinkebyfaucet.com/) for all the accounts
- Add your Infura key to `truffle-config.js`
```
const infuraKey = "<INFURA KEY>";
```

### Run
```
npm run dev
```

0. Open http://localhost:3000/
1. Set `Current Owner ID` with the first account provided by Truffle (private network) or your Metamask account (Rinkeby)
2. Set `Farmer ID`, `Distributor ID`, `Retailer ID` and `Consumer ID` with different accounts
3. Set the other values (optional)
4. Connected to the owner account, click on `Add Roles`
5. Connected to the farmer account, click on `Harvest`, `Process`, `Pack` and `ForSale`
6. Connected to the distributor account, click on `Buy` and `Ship`
7. Connected to the retailer account, click on `Receive`
8. Connected to the consumer account, click on `Purchase`
9. Click on `Fetch Data 1` and `Fetch Data 2` to load the `Item Information`
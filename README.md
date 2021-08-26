# ND1309 C2 Ethereum Smart Contracts, Tokens and Dapps - Project Starter 
**PROJECT: Decentralized Star Notary Service Project** - 
Transaction Hash
0xd6ccd453f682f56ac0da40e6b959ee420026d68f6ccb69e7c736baa643eee538


### Dependencies
**This project works with**
1. **Install all required packages**
Truffle v5.1.6 (core: 5.1.6)
Solidity v0.5.12 (solc-js)
Node v8.10.0
Web3.js v1.2.1 
npm 5.6.0


2. **Metamask: 5.3.1** - If you need to update Metamask just delete your Metamask extension and install it again.


3. **Ganache** 
Intall from here (https://www.trufflesuite.com/ganache) - Make sure that your Ganache and Truffle configuration file have the same port.


4. **Other mandatory packages**:
```bash
cd app
# install packages
npm install --save  openzeppelin-solidity@2.3
npm install --save  truffle-hdwallet-provider@1.0.17
npm install webpack-dev-server -g
npm install web3
```


## Run the application
1. Start Truffle by running


### For starting the development console
truffle develop
### truffle console

### For compiling the contract, inside the development console, run:
compile

### For migrating the contract to the locally running Ethereum network, inside the development console
migrate --reset

### For migrating the contract to rinkeby network
migrate --reset --network rinkeby

### For running unit tests the contract, inside the development console, run:
test
```

2. Frontend - Once you are ready to start your frontend, run the following from the app folder:

cd app
npm run dev

## Troubleshoot
#### Error 1 
```
'webpack-dev-server' is not recognized as an internal or external command
```
**Solution:**
- Delete the node_modules folder, the one within the /app folder
- Execute `npm install` command from the /app folder

After a long install, everything will work just fine!


#### Error 2
```
ParserError: Source file requires different compiler version. 
Error: Truffle is currently using solc 0.5.16, but one or more of your contracts specify "pragma solidity >=0.X.X <0.X.X".
```
**Solution:** In such a case, ensure the following in `truffle-config.js`:
```js
// Configure your compilers  
compilers: {    
  solc: {      
    version: "0.5.16", // <- Use this        
    // docker: true,
    // ...
```

#### Error 3
```
Metamak transfer error : 
```
**Solution:** In such a case:
```
 reset your account data in metamask
```

#### Error 4
```
test file error assert.equal error: 
```
**Solution:** In such a case:
```
 make sure your test file doenst have thie below line of code. it added automatiically and lead test file to give an error.

const { assert } = require("console");

 if you have it just remove it and run the test again
```

#### Error 5
```
after running npm run dev lot of log error will be keep showing in the terminal 
```
**Solution:** In such a case edit truffle-config.js:
```
instead of 
  provider: () => new HDWalletProvider(mnemonic, `https://rinkeby.infura.io/v3/${infuraKey}`),
Use
  provider: new HDWalletProvider(mnemonic, `https://rinkeby.infura.io/v3/${infuraKey}`), 
```

# Let's put Taj Mahal on sale !! 
Yes i am not out of my mind and it is completely possible with the help of blockchain technology.Of course Blockchian will protect us from intervention of third parties ie government,bank and police.
What we will be building is a digital asset (ERC721 token) on blockchain with the help of solidity(by writing smart contracts).We will then use IPFS to deploy our Dapp.

## Setup Environment 
We need to get hold of truffle,get it via ```npm install -g truffle```.You need to have Node.js v6+ LTS and npm (comes with Node) and Git too.This tutorial is best suited for unix environment. 
We would also be needing ganache or testrpc for local deployment.

## Let's conspire to sell Taj Mahal
* Open Terminal 
* Make a suitable folder with ```mkdir tajmahal``` and navigate into folder ```cd tajmahal```
* Now initialize the project with ```truffle init``` .
  * You will notice ***contracts  migrations  test  truffle-config.js  truffle.js*** directories and files being added to folder.
  * __contracts/:__ Contains the Solidity source files for our smart contracts. There is an important contract in here called Migrations.sol.
  * __migrations/:__ Truffle uses a migration system to handle smart contract deployments. A migration is an additional special smart contract that keeps track of changes.
  * __test/:__ Contains both JavaScript and Solidity tests for our smart contracts
  * __truffle.js:__ Truffle configuration file
* In __truffle.js__ replace the stuff with following code. 
```javascript
// Allows us to use ES6 in our migrations and tests.
// require('babel-register')
// require('babel-polyfill')

module.exports = {
  networks: {
    development: {
        host: '127.0.0.1',
        port: 8545,
        network_id: '*', // Match any network id
    }
},
};
```
* Now add the following contracts in the **contracts** directory and then hit ```truffle compile```
  * I have created Tajmahal.sol (because written in soilidty) that contains buisness logic.According to this contract ONLY ONE Tajmahal can be created.It will be non fungible an unique as it implement erc721 standards.Since we do not want some overflow in our arithmetic operations we have used __safemath.sol__ library from openzepplin.__ownable.sol__ is again from openzepplin for restricting use of some contract functions to owners.
  * [Tajmahal.sol](https://github.com/phunsukwangdu/ERC721-fullstack-Dapp-Tutorial/blob/master/contracts/Tajmahal.sol)
  * [erc721.sol](https://github.com/phunsukwangdu/ERC721-fullstack-Dapp-Tutorial/blob/master/contracts/erc721.sol)
  * [ownable.sol](https://github.com/phunsukwangdu/ERC721-fullstack-Dapp-Tutorial/blob/master/contracts/ownable.sol)
  * [safemath.sol](https://github.com/phunsukwangdu/ERC721-fullstack-Dapp-Tutorial/blob/master/contracts/safemath.sol)



 

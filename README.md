# Hello World

This Solidity program is a "ERC20 TOKEN" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract of "Shadaptoken" is in file named "NakliToken.sol"


## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., NakliToken.sol). Copy and paste the following code into the file:

```javascript

// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.8.2 <0.9.0;

import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol";

contract Shadaptoken is ERC20 {
    address owner;
    constructor(string memory name, string memory symbol,uint supply) ERC20(name, symbol) {
         owner = msg.sender;
         _mint(msg.sender,supply);
    }

    function Minter(address toAddress, uint supply) public {
        require(msg.sender == owner,"Only Owner can min the tokesn");
        _mint(toAddress, supply);
    }

    function Burner(uint supply) public {
        if(balanceOf(msg.sender) < supply){
            revert("You Don't have enough Tokens");
        }

        _burn(msg.sender, supply);
    }



}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile NakliToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Shadaptoken" contract from the dropdown menu, and then click on the "Deploy" button the contract will be deployed only if you enter token name, token symbol and token supply at the time of deployment.

Once the contract is deployed, you can interact with it by passing the params transfer function, and also play with Minter and Burner also you'll be able to Mint tokens only from contract owner ID.

## Authors

Pulkit Dubey 

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

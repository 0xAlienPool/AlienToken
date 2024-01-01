# DEPLOY SMART CONTRACT ON REDBELLY NETWORK
# Redbelly Network Smart Contract Deployment Guide

## Add Redbelly Network to Metamask

1. Open Metamask and click on "Add Network."
2. Add a network manually with the following details:
   - **Network Name:** Devnet Redbelly
   - **RPC URL:** https://rbn-gcp-australia-southeast1-a-0-b-v2.devnet.redbelly.network:8545/
   - **ChainID:** 152
   - **Currency Symbol:** RBNT
   - **Block Explorer URL:** https://explorer.devnet.redbelly.network/
3. Claim RBNT faucet by joining their Discord and pasting your wallet in `#devnet-faucet`.

## Deploy Smart Contract Using Remix IDE

1. Open Remix IDE and create a new contract named `AlienToken.sol`.
2. Copy and paste the following Solidity code into `AlienToken.sol`:
   ```solidity
   pragma solidity 0.8.17;

   // SPDX-License-Identifier: MIT

   contract MarsToken { string public name = "AlienToken"; string public symbol = "ALIEN"; uint8 public decimals = 18; uint256 public totalSupply = 1000000000;

   mapping (address => uint256) public balances; address public owner;

   constructor() { owner = msg.sender; balances[owner] = totalSupply; }

   function transfer(address recipient, uint256 amount) public { require(balances[msg.sender] >= amount, "Insufficient balance."); balances[msg.sender] -= amount; balances[recipient] += amount; } }   }
   }
   ```
   
Compile AlienToken.sol in the Solidity Compiler.

## Deploy the Smart Contract

-- Go to "Deploy & Transactions" in Remix IDE.
-- Change the environment to "Injected Provider" and connect your Metamask to the Redbelly network.
-- Press "Deploy" and confirm the transaction in Metamask.
-- If prompted, click "Send Transaction" and confirm.
-- Verify Smart Contract Deployment
-- Copy the deployed smart contract address.

Check if the smart contract is visible on the Redbelly Explorer.

Congratulations!
You have successfully deployed a smart contract on the Redbelly network using Metamask and Remix IDE!



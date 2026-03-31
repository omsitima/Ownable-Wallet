# Ownable-Wallet
Ownable Wallet
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/access/Ownable.sol";

contract OwnerWallet is Ownable {
    receive() external payable {}

    function withdraw() public onlyOwner {
        payable(owner()).transfer(address(this).balance);
    }
}

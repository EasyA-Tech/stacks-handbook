# The Stacks handbook.

Welcome. This is EasyA's legendary handbook. If you want to learn Stacks like a legend, then you're in the right place.

# Purpose

This handbook serves as a guide to the Stacks ecosystem, geared towards those just joining for the first time. It isn't just a beginners' handbook; it's a legendary handbook. Even if you've already immersed yourself in the ecosystem, you'll find tons of helpful tidbits around here!

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Core Concepts](#core-concepts)
- [Development Tools](#development-tools)
- [Smart Contracts](#smart-contracts)
- [Stacks Blockchain](#stacks-blockchain)
- [Ecosystem Projects](#ecosystem-projects)
- [Resources](#resources)
- [Handy Code Snippets](#handy-code-snippets)
- [Contributing](#contributing)

## Introduction

What is Stacks:

- [Stacks Overview](https://www.stacks.co/learn/introduction) - Fundamentals of Stacks and its integration with Bitcoin.

## Getting Started

The no-fluff starter:

- [Official Stacks documentation](https://docs.stacks.co/) - Comprehensive guides and references for Stacks development.
- [Hiro documentation](https://docs.hiro.so/) - In-depth resources for building on Stacks with Hiro tools.
- [Stacks 101](https://stacks101.com) - Community-driven knowledge hub for Stacks learners.

## Core Concepts

Explanation of fundamental concepts in the Stacks ecosystem:

- [Clarity Language](https://clarity-lang.org/) - Learn about the smart contract language designed for Stacks.
- [Proof of Transfer (PoX) consensus mechanism](https://docs.stacks.co/stacks-101/proof-of-transfer) - Understand the unique consensus mechanism that connects Stacks to Bitcoin.

## Development Tools

Key tools and environments for Stacks:

- [Clarinet](https://github.com/hirosystems/clarinet) - CLI tool for developing and testing Clarity smart contracts.
- [Hiro Platform](https://platform.hiro.so/) - Browser-based IDE for streamlined Clarity development.
- [Stacks.js](https://github.com/hirosystems/stacks.js) - Powerful JavaScript libraries for interacting with the Stacks blockchain.

## Smart Contracts

How to write and deploy smart contracts on Stacks:

- [Example Contracts](https://github.com/hirosystems/clarity-examples) - Repository of Clarity smart contract examples for learning and reference.
- [Audited Example Smart Contracts](https://github.com/clarity-lang/book/tree/main/projects) - Curated collection of security-audited Clarity contracts.
- [NFT Tutorial](https://docs.hiro.so/tutorials/clarity-nft) - Hands-on guide to creating NFTs with Clarity.

## Stacks Blockchain

Going into the blockchain level:

- [Stacks API](https://www.hiro.so/stacks-api) - Comprehensive API for interacting with the Stacks blockchain and retrieving data.
- [Hiro Explorer](https://explorer.hiro.so/?chain=mainnet) - User-friendly interface for browsing Stacks blockchain data.
- [STX Scan](https://stxscan.co/) - Feature-rich explorer for Stacks transactions and blockchain information.

## Ecosystem Projects

Cool projects built on Stacks:

- [ALEX](https://alexgo.io) - Open-source DeFi protocol modeled on the world's financial markets.
- [Arkadiko](https://arkadiko.finance) - Open source protocol that mints a stablecoin, generating Bitcoin yield.
- [Bitflow](https://www.bitflow.finance) - The decentralized exchange for Bitcoiners.
- [Blocksurvey](https://blocksurvey.io) - AI-driven survey platform with focus on data ownership and privacy.
- [btc.us](https://btc.us) - An application for .btc names.
- [Console](https://www.console.xyz) - Decentralized community application.
- [Gamma](https://gamma.io) - Explore, collect, and sell NFTs secured by Bitcoin.
- [GoSats](https://gosats.io) - Bitcoin Cashback Rewards application that enables stacking fractional bitcoin every time you shop.
- [Hermetica](https://www.hermetica.fi) - A Bitcoin-backed, yield-bearing synthetic dollar protocol.
- [Light Finance](https://lightfinance.xyz) - The only stablecoin with native yield for Bitcoin.
- [MultiSafe](https://github.com/Trust-Machines/multisafe) - MultiSafe is a shared crypto vault for managing Stacks (STX) and Bitcoin (BTC).
- [Owl Link](https://owl.link) - An application to create linking page for BNS names.
- [Sigle](https://www.sigle.io) - De-centralised and open-source Web 3.0 writing platform.
- [Stacking DAO](https://stackingdao.com) - Liquid stacking on Stacks.
- [STX20](https://stx20.com) - The STX20 protocol introduces a novel approach to creating and sharing digital artifacts on the Stacks blockchain.
- [Velar](https://velar.co) - Velar is a multi-feature DeFi app with Bitcoin finality, built on Stacks.
- [Zest Protocol](https://app.zestprotocol.com) - Zest Protocol is a lending protocol, built for Bitcoin.

## Resources

Extra stuff:

- [Clarity Universe](https://clarity-lang.org/universe) - Immersive learning experience for mastering Clarity development.
- [Clarity of Mind Book](https://book.clarity-lang.org/) - Comprehensive guide to writing efficient and secure Clarity smart contracts.

## Handy Code Snippets

Some code snippets which you can copy/paste to kickstart your project:

### Clarity Smart Contract

```clarity
;; Define a simple counter contract

;; Define a data var to store the counter
(define-data-var counter uint u0)

;; Public function to get the current count
(define-read-only (get-count)
  (var-get counter))

;; Public function to increment the counter
(define-public (increment)
  (begin
    (var-set counter (+ (var-get counter) u1))
    (ok (var-get counter))))

;; Public function to decrement the counter
(define-public (decrement)
  (begin
    (if (> (var-get counter) u0)
      (var-set counter (- (var-get counter) u1))
      (var-set counter u0))
    (ok (var-get counter))))
```

### Interacting with Stacks using JavaScript

```javascript
import { StacksTestnet } from '@stacks/network';
import { callReadOnlyFunction, cvToValue, uintCV } from '@stacks/transactions';

// Set up the network (testnet in this example)
const network = new StacksTestnet();

// Define contract details
const contractAddress = 'ST2ZRX0K27GW0SP3GJCEMHD95TQGJMKB7G9Y0X1MH';
const contractName = 'counter';
const functionName = 'get-count';

// Call a read-only function
async function getCount() {
  const result = await callReadOnlyFunction({
    network,
    contractAddress,
    contractName,
    functionName,
    functionArgs: [],
    senderAddress: contractAddress,
  });
  
  console.log('Current count:', cvToValue(result));
}

getCount();
```

These examples showcase:
1. A simple Clarity smart contract for a counter.
2. JavaScript code to interact with a Stacks smart contract.

## Contributing

We welcome contributions to make this handbook even more legendary! Here's how you can contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/amazing-addition`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add some amazing feature'`)
5. Push to the branch (`git push origin feature/amazing-addition`)
6. Create a new Pull Request

Please ensure your contributions align with our code of conduct and contribution guidelines.

## Credit/Inspiration

This handbook was inspired by the famous awesome lists by sindresorhus. We need awesome lists for Web3 ecosystems, with more of a hacker's guide to how they work. This is the answer to that need.

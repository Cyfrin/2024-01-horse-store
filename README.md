<p align="center">
<img src="https://res.cloudinary.com/droqoz7lg/image/upload/q_90/dpr_2.0/c_fill,g_auto,h_320,w_320/f_auto/v1/company/wnjnaknf11h238xdycxd?_a=BATAUVAA0" width="400" alt="horse-store">
<br/>

*Much of the NFT code was inspired by [Huffmate](https://github.com/huff-language/huffmate/)*

# Contest Details

### Prize Pool

- High - 100xp
- Medium - 20xp
- Low - 2xp

- Starts: January 11, 2024 Noon UTC
- Ends: January 18, 2024 Noon UTC 

### Stats

- nSLOC: 
  - Solidity: 26
  - Huff: 434
- Complexity Score:
  - Solidity: 28
  - Huff: 🐴 

# Horse Store 

## About

*Neiiigghhhhhh*

We are the equestrian lovers, and we LOVE all things horses! So we've created an NFT to commemorate our love of horses.

But, here is the thing, horses are *fast* and don't burn *gas*, but burn *oats*. So we wanted to make sure our codebase was hyper optimized, and to do so, we've written our contracts in Huff, a horse-themed assembly-like language so our code can be hyper-optimized and FAST. 

🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎🐎

So, we wrote our codebase into 2 parts.

1. The Solidity Rendition
2. The Huff Rendition

**Every** function in the solidity rendition has been re-written in huff. We wrote it in solidity first to get a better understanding of what the codebase *should* do, and then optimized it in huff. We consider the solidity written code to be our *reference* code, and the huff code to be our *actual* code. 

## Seaport inspiration

This setup was inspired by the [Seaport](https://github.com/ProjectOpenSea/seaport) protocol, which did something similar with solidity reference contracts, and assembly actual contracts. 

## Functionality 

Our contracts are simple, they allow the following functionality:

1. `mintHorse`: Allow anyone to mint their own horse NFT.
2. `feedHorse`: Allow anyone to feed a horse NFT. This will add a `block.timestamp` to a mapping tracking when the horse was last fed. 
3. `isHappyHorse`: Allow anyone to see if a horse is happy. A horse is happy if and only if they have been fed within the past 24 hours.   

We consider the horse happiness the most important aspect of the codebase, and our invariants can be defined as follows:

1. 
```
If horse X has been fed within the past 24 hours, horse X must be happy.
```

2.   
```
Horses must be able to be fed at all times. 
```

## Hints

Even if you don't understand Huff... Maybe you can write some tests... 

## Audit Criteria 

For this codebase, we consider any of the following to be in-scope:
1. An issue with `HorseStore.sol`
2. An issue with `HorseStore.huff`
3. Any issue where `HorseStore.huff` functionality does not match `HorseStore.sol` functionality, not including gas costs, or specific storage slots. Sending any X calldata to either contract should result in them being in the same state. 

# Getting Started

## Requirements

-   [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)  
    -   You'll know you've done it right if you can run `git --version`
-   [Foundry / Foundryup](https://github.com/gakonst/foundry)
    -   This will install `forge`, `cast`, and `anvil`
    -   You can test you've installed them right by running `forge --version` and get an output like: `forge 0.2.0 (f016135 2022-07-04T00:15:02.930499Z)`
    -   To get the latest of each, just run `foundryup`
-   [Huff Compiler](https://docs.huff.sh/get-started/installing/)
    -   You'll know you've done it right if you can run `huffc --version` and get an output like: `huffc 0.2.0`


## Quickstart

1. Clone the repo & install dependencies

```
git clone https://github.com/Cyfrin/2024-01-horse-store
cd 2024-01-horse-store
make
```

2. Run tests

```
forge test
```

# Audit Scope Details

- Commit Hash: 
```
01bce4f0a2271c4105ee7c9121b27fe7973b0eaf
```
- In Scope:
(For this contest, just use the main branch)

```
#-- HorseStore.huff
#-- HorseStore.sol
#-- IHorseStore.sol
```

## Compatibilities

- Solc Version: `0.8.20`
- Chain(s) to deploy contract to: 
  - Arbitrum
  - Ethereum
- Tokens:
  - None

# Roles

None

# Known Issues

- We understand that the exact 24 hour time frame for a horse to be happy can be manipulated on some chains. Please ignore any discrepancies in timestamps up to 120 seconds. If you find a way for a horse to be labelled incorrectly outside of a 120 second grace window, it should be considered a valid finding. 
- We do not consider gas efficiency differences between the two valid findings. 
- The exact error names can be different between the huff and solidity versions

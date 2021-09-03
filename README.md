# About the Maki Protocol Repo
This repository is designed as a container for the contracts that play the most pivotal role in the farm and exchange components of the Maki Protocol, which is a Pancakeswap fork designed to operate on Fantom.
___
# Contracts for Audit
## Primary Exchange Contracts
    -   MakiswapFactory.sol
    -   MakiswapRouter.sol
    -   MakiswapPair.sol

## Primary Farm Contracts
    -   SoyBar.sol
    -   MakiToken.sol
    -   MasterChef.sol
    -   SousChef.sol
___
# Contracts Directory
-   Contains all the smart contracts relevant for direct inspection. This directory consists of two isolated sections -- exchange and farm. 
-   When possible, Open Zeppelin smart contracts are imported directly, however, some contracts required customization and those files are contains in this repository and stored public on NPM. 
-   In such instances, the Pancakeswap revision is forked and altered *strictly* where naming convention required, leaving the logic unscathed.

___
# (Auto)-Generate Flat Contracts
- We've enabled our Makiswap Protocol repository to automagically produce flats using the truffle-flattener.
- Use the `flatten` scripts to generate fresh, flattened contracts stored in the *flats* directory. 

```
yarn flatten:chefs 
```
___
## Main Directory Composition
___
-   [EXCHANGE](#exchange-and-farm) or [FARM](#exchange-and-farm)
    -   [Flats](#flats-and-libraries)
    -   [Interfaces](#interfaces-and-token)
    -   [Token](#interfaces-and-token)
    -   [Libraries](#flats-and-libraries)


[Notes on Libraries](#notes-on-libraries)

___
## Exchange and Farm
___
- This repository contains the smart contracts for the **exchange** and the **farm** component of MakiSwap. 
- These are included together to benefit the auditor tasked with reviewing each series of contracts.
___
## Interfaces and Token
___

- **Interfaces Directory**: includes the interfaces referenced in the main smart contracts for each respective sub-section.
- **Token Directory**: includes the smart contracts that are inherited by the MakiToken.sol, namely HRC20.sol and SafeHRC20.sol, which are designed to mirror the OZ smart contracts for the ERC equivalents.
___
## Flats and Libraries
___
- **Flats Directory**: contains the flattened versions of the smart contracts.
- **Libraries Directory**: contains the smart contracts that are referenced via an import, stored publicly in node package manager (npm).
- **More Details** 
    -   Please feel free to review each component in the context of their respective repositories as listed below,
        -   [maki-swap-lib](https://github.com/makiswap-protocol/maki-swap-lib)
        -   [maki-swap-core](https://github.com/makiswap-protocol/maki-swap-core)
        -   [maki-swap-periphery](https://github.com/makiswap-protocol/maki-swap-periphery)
        -   [maki-farm](https://github.com/makiswap-protocol/maki-farm)

### Notes on Libraries
- Conventionally, devs import Open Zeppelin smart contracts. However, given Fantom is the smart chain of choice, in instances where ERC20 / BEP20 is referenced a new variant of the contract in question is forked and becomes a unique contract in name only, not in logic.
- The schema of swap-lib, swap-core, and swap-periphery are modeled exactly like Pancakeswap, from which the repositories are forked and altered to meet the context of Fantom.

## Deployed Contracts (Testnet)
- [MakiswapFactory.sol](https://testnet.ftmscan.com/address/0x3297a02bcbd243fcce925bfe26345161453d1a52#code): 0x3297a02bcbd243fcce925bfe26345161453d1a52
    - `INIT_CODE_PAIR_HASH`: 0x4ab653b3b599042ff06f15448fa3cfea38d2b0931cdcbd174020e106ba1aea3f 
- [MakiswapRouter.sol](https://testnet.ftmscan.com/address/0x6fc9ae2657511d553827bb1920b1d492456ed5e7#code): 0x6fc9ae2657511d553827bb1920b1d492456ed5e7

- [MakiToken.sol](https://testnet.ftmscan.com/address/0xeeb45d492c7c87d739045fa76feebe1657a05dd5#code): 0xeeb45d492c7c87d739045fa76feebe1657a05dd5
- [SoyBar.sol](https://testnet.ftmscan.com/address/0x058b271c2909c2a690a543bef2bd165eb59e8efd#code): 0x058b271c2909c2a690a543bef2bd165eb59e8efd
- [MasterChef.sol](https://testnet.ftmscan.com/address/0x1becb580c988a71e9542982797cbdd8e81ae534b#code): 0x1becb580c988a71e9542982797cbdd8e81ae534b
- [SousChef.sol](https://testnet.ftmscan.com/address/0x79b5554dD97910E628ed12b9E62F6A0e42413D36#code): 0x79b5554dD97910E628ed12b9E62F6A0e42413D36


## Deployed Contracts (Mainnet)

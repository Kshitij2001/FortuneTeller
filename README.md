# FortuneTeller
This project involves two smart contracts, FortuneTeller.sol and FortuneSeeker.sol, that interact with each other on the Avalanche Fuji testnet (or any EVM network). FortuneTeller.sol uses Chainlink’s Verifiable Random Function (VRF) to generate a provably random number, which is then used to select a fortune from an array.
You will need to have the native token for the blockchain test network you use.  This project is configured to be deployed and run on the Avalanche Fuji testnet, but you can deploy the code on any EVM network that is [supported by Chainlink](https://docs.chain.link/chainlink-automation/supported-networks/)

You can have a time based (cron-like) automation schedule or you can have custom logic that tells the Chainlink Decentralized Network whether or not your contract needs to have its target function invoked.  We use the custom logic approach in this project.

As long as `FortuneTeller` is invoked to generate new random numbers, `FortuneSeeker` will receive a different (except by coincidence) Fortune from `FortuneTeller` - the frequency depends on the `interval` that you tell the Chainlink Automation Network you want your contract invoked, and will continue for so long as `FortuneSeeker` can pay `FortuneTeller` and for so long as your Chainlink Automation Upkeep registration has enough LINK balance.

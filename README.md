# Advanced Solidity

Our company has decided to crowdsale our PupperCoin token in order to help fund the network development. We have already worked with the legal team and obtained necessary documents for creating a crowdsale open to the public.

In the process, we are required to enable refunds if the crowdsale is successful and the goal is met. We are only allowed to raise a maximum of 300 Ether and the crowdsale will run for 24 weeks.

We would create an ERC20 token that would be minted through a `Crowdsale` contract using OpenZeppelin Solidity library. This crowdsale contract will manage the entire process, allowing users to send ETH and get back PUP (PupperCoin).

This contract will mint the tokens automatically and distribute them to buyers in one transaction.


### To create our project:

We use Remix to generate a file called `PupperCoin.sol` to create a standard `ERC20Mintable` token for a new contract named `PupperCoinCrowdsale.sol`


### Designing of the contracts

#### ERC20 PupperCoin

We use a standard `ERC20Mintable` and `ERC20Detailed` contract and use `18` as the `decimals`.


#### PupperCoinCrowdsale

We create another file in Remix as `Crowdsale.sol`. The parameters for the crowdsale are `name`, `symbol`, `wallet` and `goal`.

The `rate` is 1, to maintain parity with Ether units (1 TKN per Ether or 1 TKNbit per wei).

When passing the `open` and `close` times, we use `now` and `now + 24 weeks` to set the times for our `PupperCoinCrowdsaleDeployer` contract.


### Testing the Crowdsale

We tested the crowdsale by sending Ether to the crowdsale from a different account. We applied the process to MetaMask.


### Deploying the Crowdsale

We deployed the crowdsale to a testnet, noted the total gas cost to obtain information on what it would be in reality.
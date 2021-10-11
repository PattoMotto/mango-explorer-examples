# 🥭 Mango Explorer

## ⚠ Warning

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


## Introduction

These are some simple examples of how to use the [mango-explorer](https://github.com/blockworks-foundation/mango-explorer) library.

Each example aims to be as simple as possible for a given piece of functionality. The [mango-explorer](https://github.com/blockworks-foundation/mango-explorer) project itself has more realistic usage (for example, commands in the /bin directory), with parameters and error handling.

These examples are all in Jupyter Notebooks and can be [run in your browser (no installation necessary!) on Binder](https://mybinder.org/v2/gh/blockworks-foundation/mango-explorer-examples/HEAD).


## Devnet

All these examples run on Solana devnet, so no real tokens are used and no tokens have any value.

The private key for the account is shown below, and in many samples. It's hard-coded to simplify the examples as well as make it obvious how keys are used.

> Account: DeekipCw5jz7UgQbtUbHQckTYGKXWaPQV4xY93DaiM6h
> 
> Key: [67,218,68,118,140,171,228,222,8,29,48,61,255,114,49,226,239,89,151,110,29,136,149,118,97,189,163,8,23,88,246,35,187,241,107,226,47,155,40,162,3,222,98,203,176,230,34,49,45,8,253,77,136,241,34,4,80,227,234,174,103,11,124,146]

Please don't drain tokens from this account. Devnet tokens are already freely available and it just makes things more difficult for beginners.

If you find that the examples don't work because there's no SOL in the devnet account, you can 'airdrop' 1 SOL into it with the Solana CLI command:
```
solana airdrop 10 DeekipCw5jz7UgQbtUbHQckTYGKXWaPQV4xY93DaiM6h --url devnet
```

## Python3

All the code here and in [mango-explorer](https://github.com/blockworks-foundation/mango-explorer) assumes Python 3. Where you see commands running `python`, you may need to instead explicitly run `python3` (depending on your system).


## Contents

### Context

The `Context` is heavily used to provide access to Solana, Mango Groups and Accounts. [This example](ShowContext.ipynb) shows you how to create a `Context` object.


### Group

A Mango `Group` allows cross-margining of assets and holds details of spot and perp markets. [This example](ShowGroup.ipynb) shows you how to access a group and show its details.


### Wallet

A `Wallet` holds the keys to access specific Solana data. [This example](ShowWallet.ipynb) shows how to instantiate a wallet from existing data.


### Account

A Mango `Account` holds details of a user's balances and positions. [This example](ShowAccount.ipynb) shows you how to access an account and show its details.


### Balances

`Account`s have a lot of details. [This example](ShowBalances.ipynb) shows you how to access the net balances of all the tokens it contains.


### Specific Balance

`Account`s have a lot of details. [This example](ShowBalance.ipynb) shows you how to access the balance of one specific token.


### Oracle Price

Sometimes you just want to know the price of an asset. [This example](ShowPrice.ipynb) shows you how to fetch the current price from three different `Oracle`s.


### Streaming Prices

What if you want to watch the price update in real-time? [This example](ShowStreamingPrices.ipynb) shows you how to stream prices from an `Oracle`.


### Market

A `Market` is an abstract entity to gather together access to the 3 specific market types that [mango-explorer](https://github.com/blockworks-foundation/mango-explorer) supports: Serum, Spot and Perp. [This example](ShowMarkets.ipynb) shows you how to access different market types and show their details.


### Market Operations: Show All Orders

Once you have access to a `Market` you can show its `Order`s. [This example](ShowAllOrders.ipynb) shows you how.


### Market Operations: Place and Cancel Orders

If you have a `Market` and you have tokens, you can place and cancel `Order`s. [This example](PlaceAndCancelOrder.ipynb) shows you how.


### Market Operations: Show Own Orders

Often you just want to work with your own orders. [This example](ShowOwnOrders.ipynb) shows you how to retrieve only your own `Order`s from a `Market`.


### Serum OpenOrders

Tracking down details of token transfers across Serum accounts can be tricky. One place that's hard to check sometimes is the `OpenOrders` account. [This example](ShowSerumOpenOrders.ipynb) shows you how to fetch and print an account's Serum `OpenOrders`.


### Spot OpenOrders (Coming Soon...!)

Mango spot `OpenOrders` accounts are very similar to Serum `OpenOrders`, but are fetched slightly differently. This example shows you how to fetch and print an account's Spot `OpenOrders`.


### Perp OpenOrders (Coming Soon...!)

Perp `OpenOrders` are a little difference from Spot and Serum `OpenOrders`. This example shows you how to fetch and print an account's perp `OpenOrders`.


### Perp Event Queue

The `PerpEventQueue` holds `PerpFillEvent`s, `PerpOutEvent`a and `PerpLiquidateEvent`s, as they are processed. [This example](ShowPerpEventQueue.ipynb) shows you how to fetch and print all `PerpEventQueue` events.


### Streaming Perp Events

What if you want to watch the events appear in real-time? [This example](ShowStreamingPerpEvents.ipynb) shows you how to stream all perp events from a `PerpEventQueue`.


## Combinable Instructions: Place Order (Coming Soon...!)

`CombinableInstruction`s work at a lower level than `MarketOperations`, but they provide more flexibility because they can be gathered together into a single atomic transaction. This example shows you how to place an order, crank, and settle all in one go.


## Combinable Instructions: Deposit and Withdraw

Depositing and withdrawing are non-market operations, so don't fit into the `MarketOperations` paradign. They are still possible using `CombinableInstruction`s though! [This example](DepositAndWithdraw.ipynb) shows how to deposit and then withdraw Wrapped SOL to and from a Mango `Account`.


## Basic Marketmaker (Coming Soon...!)

Now that you can fetch prices and place and cancel orders, this example shows a basic marketmaker.


# Support

    🥭 Mango Markets: https://mango.markets
    📄 Documentation: https://docs.mango.markets/
    💬 Discord: https://discord.gg/67jySBhxrg
    🐦 Twitter: https://twitter.com/mangomarkets
    🚧 Github: https://github.com/blockworks-foundation
    📧 Email: mailto:hello@blockworks.foundation

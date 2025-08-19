# CLI Demo
## _Step-by-step CLI guide for Makerere_

[![BTC Hub Africa](https://btchubafrica.com/wp-content/uploads/2024/12/btc-hub-logo-3-1.png)](https://btchubafrica.com/)

This guide walks you through setting up and running Bitcoin Core in **regtest** mode for demo and learning purposes.

---

## First Step

Clone and build Bitcoin Core from the official repository.  
⚠️ Note: This process may take some time.

| OS | Build Guide |
|----|-------------|
| Mac | https://github.com/bitcoin/bitcoin/blob/master/doc/build-osx.md |
| Linux | https://github.com/bitcoin/bitcoin/blob/master/doc/build-unix.md |
| Windows | https://github.com/bitcoin/bitcoin/blob/master/doc/build-windows.md |

---

## Configuration Files

### `bitcoin.conf` (Regtest)
```conf
# Bitcoin Regtest Configuration File
[regtest]

# RPC port number
rpcport=18332

# RPC username and password
rpcusername=regtestuser
rpcpassword=regtestpass

# Wallet (disabled by default)
wallet=0

# Maximum connections
maxconnections=100

# Block size limit
txsize=5000000

# Block confirmation target
blockconfirmations=150

# Minimum transaction fee
minrelaytxfee=0.00005

# Max memory usage
maxmemory=200000000

# Log settings
logtimestamps=1

# Default fallback fee
fallbackfee=0.0001
```
### `bitcoin.conf` (signet)
```conf
# Set the best block hash here:
assumevalid=

# Run as a daemon mode without an interactive shell
daemon=1

# Set the data directory to the storage directory
datadir=/blockchain/.bitcoin/data

# Set the number of megabytes of RAM to use, set to like 50% of available memory
dbcache=3000

# Add visibility into mempool and RPC calls for potential LND debugging
debug=mempool
debug=rpc

# Don't bother listening for peers
listen=0

# Constrain the mempool to the number of megabytes needed:
maxmempool=100

# Limit uploading to peers
maxuploadtarget=1000

# Turn off serving SPV nodes
nopeerbloomfilters=1
peerbloomfilters=0

# Don't accept deprecated multi-sig style
permitbaremultisig=0

# Set the RPC auth to what was set above
rpcauth=

# Turn on the RPC server
server=1

# Reduce the log file size on restarts
shrinkdebuglog=1

# Set testnet if needed
signet=1

# Turn on transaction lookup index
txindex=1



#need a part , 19832

```
## Story Line

> lets create two wallets
> get some coins in one wallet 
> check balance
> send some cash from wallet to the 2nd one
> and end with transcation 
> extra commands if needed will be added for you to Test ~


## Commands
#### Starting Bitcoin Core
Run Core in regtest mode.
👉 Recommendation: start without -daemon (-d) so you can see logs in real time.
```sh
./bitcoind -regtest
```
#### Let test it : 

lets first create our two wallets using :
```sh
./bitcoin-cli -regtest createwallet "mywallet1"
./bitcoin-cli -regtest createwallet "mywallet2"
```
as we know we use addresses so lets generate address for both wallets using:
```sh
./bitcoin-cli -regtest -rpcwallet=mywallet1 getnewaddress
./bitcoin-cli -regtest -rpcwallet=mywallet2 getnewaddress
```
lets say that the two address are : (just an example , your will look different each time you reload your core)
1->bcrt1qqvz809fl94swsgcw2l03j8g08s7l56g54j7utz
2->bcrt1qm7llnurczxjwkjsd7u62hgwcch64x2u4l5d95c

🥉 Step 3: Generate Blocks to Get Coins (Mining)
```sh
./bitcoin-cli -regtest -rpcwallet=mywallet1 generatetoaddress 101 bcrt1qqvz809fl94swsgcw2l03j8g08s7l56g54j7utz
```
note:Generates 101 blocks to mature the coinbase rewards (first 100 are needed for maturity).
lets send 10 from the first wallet to the second one 
```sh
./bitcoin-cli -regtest -rpcwallet=mywallet1 sendtoaddress bcrt1qm7llnurczxjwkjsd7u62hgwcch64x2u4l5d95c 10
```
example : 
output -> transaction ID (txid)
6676a62c62ccee70618084be9f2d1cd38f64d9c3ddfadb5fe7631c3287e4fd58
here , lets check the state of our transcation so lets get info about it :
```sh
./bitcoin-cli -regtest getrawtransaction 6676a62c62ccee70618084be9f2d1cd38f64d9c3ddfadb5fe7631c3287e4fd58 true
```
lets check balance in both wallets:
```sh
./bitcoin-cli -regtest -rpcwallet=mywallet1 getbalance
./bitcoin-cli -regtest -rpcwallet=mywallet2 getbalance
./bitcoin-cli -regtest -rpcwallet=mywallet2 getunconfirmedbalance
```


💡 Assignment: Try to make the balances appear in both wallets. (Hint: repeat a familiar command.)

#### Extra Commands
Check wallet storage location:
```sh
./bitcoin-cli -regtest listwalletdir
```
List currently loaded wallets:
```sh
./bitcoin-cli -regtest listwallets
```
Load a wallet after restart:
```sh
./bitcoin-cli -regtest loadwallet "mywallet1"
```
Unload a wallet:
```sh
./bitcoin-cli -regtest unloadwallet "mywallet1"
```
Get wallet info:
```sh
./bitcoin-cli -regtest getwalletinfo -rpcwallet=mywallet1
```
List transactions:
```sh
./bitcoin-cli -regtest -rpcwallet=mywallet1 listtransactions
```
useful sites to check
https://developer.bitcoin.org/reference/rpc/
https://thunderbiscuit.github.io/Learning-Bitcoin-from-the-Command-Line/01_0_Introduction.html
https://lightningpolar.com/
## Whats Next
Want to contribute? Great!


# Geth-node

## About

### Getting started

`Create a new account`

```sh
geth account new
```

`Use snap sync node to start geth`

```sh
# I use snap syncnode because it is quicker that full syncnde
# to start the geth
geth --datadir geth-node --sepolia --syncmode snap
# It then awaits for other nodes to connect
# To interact - it uses RPC APIs (Remote Procedure Call)
```

`Start interaction through IPC(Inter-Process Communication)`

```sh
# start console and interact
geth attach geth-node/geth.ipc
# note that websockets are preferred when it comes to supertial web3 dapps notifications

# Get accounts that are connected
geth.accounts

# Check for ether balance of the account
web3.fromWei(eth.getBalance("<address>"), "ether")

# Perform various operation with console
geth help
```



-------------------------

@0xJonaseb11

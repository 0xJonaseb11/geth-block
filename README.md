### Author : @Jonas-sebera

## About
Create and interact with a Private Blockchain Using GETH [Go-ETHEREUM]

### QUICKSTART

To install `geth`,
```sh
sudo apt update
sudo apt install ethereum
```

To create a node account,
```sh
geth --datadir "./data" account new 
```

To establish a connection,
```sh
geth --datadir ./data init ../geth_block/geth_block.json
```

Let's now create and generate a boot key for connecting node1 to bootnode and node2 to bootnode and viseversa

Create and generate a boot key
```sh
bootnode -genkey boot.key
```

To start a new network connection,
```sh
bootnode -nodekey boot.key
```

### To fully start the connection;

Navigate to the bootNode directory
 ### ./GETH/bootNode$ 

```sh
bootnode -nodekey "./boot.key" -verbosity 7 -addr "127.0.0.1:30303"
```
Connect node1,

```sh

geth --networkid 14333 --datadir "./data" --bootnodes enode://903307600f04d59ff73ecc41016a2112aedebd4021799f764092872bd4aa75b55786bb14665f6171707ba5aa242afe7691b70303deea79ab46c0f63af6d59fed@127.0.0.1:0?discport=30301 --port 30300 --ipcdisable --syncmode full --rpc --allow-insecure-unlock --rpccorsdomain "*" --rpcport 8545 --unlock 0xa23b87d009c9023BeF10442568C3392CA3eeD89d --password password.txt --mine console

```

If `rpc` endpoint doesn't work, try using `http` as folows,

```sh
geth --networkid 14333 --datadir "./data" --bootnodes enode://903307600f04d59ff73ecc41016a2112aedebd4021799f764092872bd4aa75b55786bb14665f6171707ba5aa242afe7691b70303deea79ab46c0f63af6d59fed@127.0.0.1:0?discport=30301 --port 30303 --ipcdisable --syncmode full --http --allow-insecure-unlock --http.port 8545 --unlock 0xca9AdF6627A549c8D593439ab79E19f912E6dB11 --password password.txt --mine console

```

Connect node2,

```sh

geth --networkid 14333 --datadir "./data" --bootnodes enode://903307600f04d59ff73ecc41016a2112aedebd4021799f764092872bd4aa75b55786bb14665f6171707ba5aa242afe7691b70303deea79ab46c0f63af6d59fed@127.0.0.1:0?discport=30301 --port 30303 --ipcdisable --syncmode full --rpc --allow-insecure-unlock --rpccorsdomain "*" --rpcport 8545 --unlock 0xa23b87d009c9023BeF10442568C3392CA3eeD89d --password password.txt console

```

Want to only start a peer-2-peer network?
```sh
geth --networkid 14144 --datadir "./data" --bootnodes enode://903307600f04d59ff73ecc41016a2112aedebd4021799f764092872bd4aa75b55786bb14665f6171707ba5aa242afe7691b70303deea79ab46c0f63af6d59fed@127.0.0.1:0?discport=30301
```



If `rpc` endpoint doesn't work, try using `http` as follows,

```sh
geth --networkid 14333 --datadir "./data" --bootnodes enode://903307600f04d59ff73ecc41016a2112aedebd4021799f764092872bd4aa75b55786bb14665f6171707ba5aa242afe7691b70303deea79ab46c0f63af6d59fed@127.0.0.1:0?discport=30301 --port 30303 --ipcdisable --syncmode full --http --allow-insecure-unlock --http.port 8545 --unlock 0xca9AdF6627A549c8D593439ab79E19f912E6dB11 --password password.txt console

```

Start mining some ether, Use console 

Configuration;
```sh
geth --datadir "./data" --networkid 14144 --port 30303 --ipcdisable --syncmode full --mine console
```
Unlock Your account
```sh
personal.unlockAccount("0xa23b87d009c9023BeF10442568C3392CA3eeD89d", "MOOD9999", 0)
```

Start mining
In geth console,
```sh
miner.start()
```

Check mining status
```sh
eth.mining
```

If true, check mined blocks
```sh
eth.Number
```

After, when mining is done, stop mining
```sh
miner.stop()
```

<hr>

### @Jonas-sebera
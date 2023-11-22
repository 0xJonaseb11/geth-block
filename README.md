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

To start a network connection,
```sh
bootnode -nodekey boot.key
```

<hr>

### @Jonas-sebera
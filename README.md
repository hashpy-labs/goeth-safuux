## SafuuX - GoEth

Safuux Testnet implementation, from GoEthereum (GETH) / golang-ethereum

[![API Reference](
https://camo.githubusercontent.com/915b7be44ada53c290eb157634330494ebe3e30a/68747470733a2f2f676f646f632e6f72672f6769746875622e636f6d2f676f6c616e672f6764646f3f7374617475732e737667
)](https://pkg.go.dev/github.com/ethereum/go-ethereum?tab=doc)
[![Go Report Card](https://goreportcard.com/badge/github.com/ethereum/go-ethereum)](https://goreportcard.com/report/github.com/ethereum/go-ethereum)
[![Travis](https://travis-ci.com/ethereum/go-ethereum.svg?branch=master)](https://travis-ci.com/ethereum/go-ethereum)
[![Discord](https://img.shields.io/badge/discord-join%20chat-blue.svg)](https://discord.gg/nthXNEv)

Automated builds are available for stable releases and the unstable master branch. Binary
archives are published at https://geth.ethereum.org/downloads/.

## Building the source

For prerequisites and detailed build instructions please read the [Installation Instructions](https://geth.ethereum.org/docs/install-and-build/installing-geth).

Building `geth` requires both a Go (version 1.14 or later) and a C compiler. You can install
them using your favourite package manager. Once the dependencies are installed, run

```shell
make geth
```

or, to build the full suite of utilities:

```shell
make all
```
                                                                                                                                            |

## Running `geth`

Going through all the possible command line flags is out of scope here (please consult our
[CLI Wiki page](https://geth.ethereum.org/docs/interface/command-line-options)),
but we've enumerated a few common parameter combos to get you up to speed quickly
on how you can run your own `geth` instance.

### Hardware Requirements

Minimum:

* CPU with 2+ cores
* 4GB RAM
* 80GB free storage space to sync the Mainnet
* 8 MBit/sec download Internet service

Recommended:

* Fast CPU with 4+ cores
* 16GB+ RAM
* High Performance SSD with at least 80GB free space
* 25+ MBit/sec download Internet service

### Full node on the main Safuux network

By far the most common scenario is people wanting to simply interact with the Safuux
network: create accounts; transfer funds; deploy and interact with contracts. For this
particular use-case the user doesn't care about years-old historical data, so we can
sync quickly to the current state of the network. 


### Running a full node without being a validator


`./geth --datadir ./node init safuux_mainnet.json`

`./geth --networkid 14333 --datadir ./data/ --bootnodes enode://0bff00426a5155e4edd0ce94f2a94fb3cc94b59224651c4fa454db7a0bcbc2bec733fa45498c7cb46 131edae317aa6891c871f3f59b9647ff48cc6e17fff50e3@100.21.18.105:30303 --port 30303 --ipcdisable --syncmode full --http --allow-insecure-unlock --http.corsdomain "*" --http.port 8545 --http.addr "0.0.0.0" --unlock YOUR_ADDRESS_OF_GETH --password ./password.txt --http.api personal,admin,db,eth,net,web3,miner,shh,txpool,debug,clique`


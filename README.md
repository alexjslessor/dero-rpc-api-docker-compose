<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.3.1/styles/arta.min.css">

<!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.3.1/highlight.min.js"></script> -->

<!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.3.1/languages/python.min.js"></script> -->

<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.3.1/languages/bash.min.js"></script>


# Overview

This is a dockerized Dero wallet and daemon. This docker-compose configuration exposes the RPC api as specified in the .pdf document also contained in this repository.

The purpose of this project is to allow local developemnt of a Dero based blockchain application, making calls to the RPC API.


# Setup

To start both daemon and wallet run:

```bash
docker-compose up
```

note:

Dero daemon and wallet must be initialized externally before used in docker.


# CLI Commands



### Wallet CLI Commands

- `./dero-wallet-cli-linux-amd64 -h`

```bash
 Options:
  -h --help     Show this screen.
  --version     Show version.
  --wallet-file=<file>  Use this file to restore or create new wallet
  --password=<password>  Use this password to unlock the wallet
  --offline     Run the wallet in completely offline mode 
  --offline_datafile=<file>  Use the data in offline mode default ("getoutputs.bin") in current dir
  --prompt      Disable menu and display prompt
  --testnet  	Run in testnet mode.
  --debug       Debug mode enabled, print log messages
  --unlocked    Keep wallet unlocked for cli commands (Does not confirm password before commands)
  --generate-new-wallet Generate new wallet
  --restore-deterministic-wallet    Restore wallet from previously saved recovery seed
  --electrum-seed=<recovery-seed>   Seed to use while restoring wallet
  --socks-proxy=<socks_ip:port>  Use a proxy to connect to Daemon.
  --remote      use hard coded remote daemon https://rwallet.dero.live
  --daemon-address=<host:port>    Use daemon instance at <host>:<port> or https://domain
  --rpc-server      Run rpc server, so wallet is accessible using api
  --rpc-bind=<127.0.0.1:20209>  Wallet binds on this ip address and port
  --rpc-login=<username:password>  RPC server will grant access based on these credentials
```

### Daemon CLI Commands

- ```./derod-linux-amd64 -h```

```sh
derod 
DERO : A secure, private blockchain with smart-contracts

Usage:
  derod [--help] [--version] [--testnet] [--debug]  [--sync-node] [--boltdb | --badgerdb] [--disable-checkpoints] [--socks-proxy=<socks_ip:port>] [--data-dir=<directory>] [--p2p-bind=<0.0.0.0:18089>] [--add-exclusive-node=<ip:port>]... [--add-priority-node=<ip:port>]... 	[--min-peers=<11>] [--rpc-bind=<127.0.0.1:9999>] [--lowcpuram] [--mining-address=<wallet_address>] [--mining-threads=<cpu_num>] [--node-tag=<unique name>]
  derod -h | --help
  derod --version

Options:
  -h --help     Show this screen.
  --version     Show version.
  --testnet  	Run in testnet mode.
  --debug       Debug mode enabled, print log messages
  --boltdb      Use boltdb as backend  (default on 64 bit systems)
  --badgerdb    Use Badgerdb as backend (default on 32 bit systems)
  --disable-checkpoints  Disable checkpoints, work in truly async, slow mode 1 block at a time
  --socks-proxy=<socks_ip:port>  Use a proxy to connect to network.
  --data-dir=<directory>    Store blockchain data at this location
  --rpc-bind=<127.0.0.1:9999>    RPC listens on this ip:port
  --p2p-bind=<0.0.0.0:18089>    p2p server listens on this ip:port, specify port 0 to disable listening server
  --add-exclusive-node=<ip:port>	Connect to specific peer only 
  --add-priority-node=<ip:port>	Maintain persistant connection to specified peer
  --sync-node       Sync node automatically with the seeds nodes. This option is for rare use.
  --min-peers=<11>      Number of connections the daemon tries to maintain  
  --lowcpuram          Disables some RAM consuming sections (deactivates mining/ultra compact protocol etc).
  --mining-address=<wallet_address>         This address is rewarded when a block is mined sucessfully
  --mining-threads=<cpu_num>         Number of CPU threads for mining
  --node-tag=<unique name>	Unique name of node, visible to everyone
```

**Resources:**

https://docs.docker.com/compose/compose-file/compose-file-v3/

https://docs.docker.com/compose/networking/

https://www.penta-code.com/creating-a-lemp-stack-with-docker-compose/



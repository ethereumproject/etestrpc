# SputnikVM Developer Environment

[![Build Status](https://travis-ci.org/ethereumproject/sputnikvm-dev.svg?branch=master)](https://travis-ci.org/ethereumproject/sputnikvm-dev) [![Build status](https://ci.appveyor.com/api/projects/status/k4wytswph99qt9m9?svg=true)](https://ci.appveyor.com/project/splix/sputnikvm-dev)

Development environment based on SputnikVM and etcommon.

## Usage

You can either download `svmdev` from the release page, or build it by yourself by installing Rust, and run `cargo run`. We currently support Linux and MacOS, and Windows.

```
USAGE:
    svmdev [OPTIONS]

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

OPTIONS:
    -a, --accounts <ACCOUNTS>      Additional accounts to be generated, default to 9.
    -b, --balance <BALANCE>        Balance in Wei for the account to be generated, default is 0x10000000000000000000000000000.
    -l, --listen <LISTEN>          Listen address and port for the RPC, e.g. 127.0.0.1:8545.
    -k, --private <PRIVATE_KEY>    Private key for the account to be generated, if not provided, a random private key will be generated.
```

After started, `svmdev` will print out the address and private key with balance for testing. It will then generate new blocks every ten seconds, and include all pending transactions that yet to be confirmed. You can then use the RPC endpoints below to test your blockchain application.

# Using truffle
You can use [truffle](https://truffleframework.com/) to deploy and test your contracts:
First install truffle by `npm install -g truffle`.
Then make a new directory and then cd into it and run `truffle unbox ETCDEVTeam/emerald-starter-kit`.
Make sure `svmdev` is running. You can run `truffle deploy` to deploy and test your contracts.


## Supported RPC Endpoints

Below is a list of all the supported RPC endpoints by `sputnikvm-dev`.

* [web3_clientVersion](https://github.com/ethereum/wiki/wiki/JSON-RPC#web3_clientversion)
* [web3_sha3](https://github.com/ethereum/wiki/wiki/JSON-RPC#web3_sha3)
* [net_version](https://github.com/ethereum/wiki/wiki/JSON-RPC#net_version)
* [net_peerCount](https://github.com/ethereum/wiki/wiki/JSON-RPC#net_peercount)
* [net_listening](https://github.com/ethereum/wiki/wiki/JSON-RPC#net_listening)
* [eth_protocolVersion](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_protocolversion)
* [eth_syncing](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_syncing)
* [eth_coinbase](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_coinbase)
* [eth_mining](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_mining)
* [eth_hashrate](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_hashrate)
* [eth_gasPrice](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_gasprice)
* [eth_accounts](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_accounts)
* [eth_blockNumber](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_blocknumber)
* [eth_getBalance](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getbalance)
* [eth_getStorageAt](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getstorageat)
* [eth_getTransactionCount](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_gettransactioncount)
* [eth_getBlockTransactionCountByHash](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getblocktransactioncountbyhash)
* [eth_getBlockTransactionCountByNumber](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getblocktransactioncountbynumber)
* [eth_getUncleCountByBlockHash](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getunclecountbyblockhash)
* [eth_getUncleCountByBlockNumber](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getunclecountbyblocknumber)
* [eth_getCode](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getcode)
* [eth_sign](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_sign)
* [eth_sendTransaction](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_sendtransaction)
* [eth_sendRawTransaction](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_sendrawtransaction)
* [eth_call](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_call)
* [eth_estimateGas](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_estimategas)
* [eth_getBlockByHash](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getblockbyhash)
* [eth_getBlockByNumber](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getblockbynumber)
* [eth_getTransactionByHash](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_gettransactionbyhash)
* [eth_getTransactionByBlockHashAndIndex](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_gettransactionbyblockhashandindex)
* [eth_getTransactionByBlockNumberAndIndex](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_gettransactionbyblocknumberandindex)
* [eth_getTransactionReceipt](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_gettransactionreceipt)
* [eth_getUncleByBlockHashAndIndex](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getunclebyblockhashandindex)
* [eth_getUncleByBlockNumberAndIndex](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getunclebyblocknumberandindex)
* [eth_getCompilers](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getcompilers)
* [eth_newFilter](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_newfilter)
* [eth_newBlockFilter](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_newblockfilter)
* [eth_newPendingTransactionFilter](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_newpendingtransactionfilter)
* [eth_uninstallFilter](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_uninstallfilter)
* [eth_getFilterChanges](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getfilterchanges)
* [eth_getFilterLogs](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getfilterlogs)
* [eth_getLogs](https://github.com/ethereum/wiki/wiki/JSON-RPC#eth_getlogs)

## Supported Debug Endpoints

* debug_dumpBlock
* debug_getBlockRlp
* debug_traceBlock
* debug_traceBlockByNumber
* debug_traceBlockByHash
* debug_traceBlockFromFile
* debug_traceTransaction

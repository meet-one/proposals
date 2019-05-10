# Overview

The `removesaving` proposal remove 4% inflation to eosio.saving.

[Click me to see why reduce inflation from 5% to 1%.](https://medium.com/meet-one/meet-one-has-released-the-4-inflation-removal-eos-code-change-on-github-28e66f796e9b) 

This proposal makes three changes to the EOS system:

1. Change the system parameter continuous_rate to 0.00995

2. Change the 5% inflation rate to 1%

3. Stop the transfer of EOS tokens to eosio.saving account

## Important notes for top 21 BPs

The block.one will [add configurable inflation logic](https://github.com/EOSIO/eosio.contracts/issues/246) to system contract in the future.

### Review proposal

```
cleos multisig review eosiomeetone removesaving
```

### Proposal Status

```
cleos get table eosio.msig eosiomeetone approvals2
```

### Approve proposal

```
cleos multisig approve eosiomeetone removesaving '{"actor":"eosiomeetone","permission":"active"}' -p eosiomeetone
```

The `removesaving` proposal on Kylin Testnet.

https://kylin.eosx.io/tx/85848974110eb1fe370afda8b2a991e269649fd4d9f82505104a842888f2684d

## [Compare code changes](https://github.com/meet-one/eosio.contracts/compare/v1.6.0...meet-one:remove-inflation-to-wps?diff=unified)

# Build system contract

```shell
git clone https://github.com/meet-one/eosio.contracts.git

cd eosio.contracts/contracts/eosio.system

git checkout remove-inflation-to-wps

eosio-cpp -contract=eosio.system -abigen src/eosio.system.cpp -o eosio.system.wasm -I=/usr/local/include/ -I=./include -I=../eosio.token/include -I=./src

shasum -a 256 eosio.system.wasm

cleos set contract -s -j -d eosio ./ > upgrade_system_contract_official_trx.json
```


## Original system contract on EOS Mainnet: [eosio.contracts-1.6.0](https://github.com/EOSIO/eosio.contracts/tree/v1.6.0)

```
ubuntu 18.04
eosio.cdt 1.5.0
```

eosio.system.wasm hash: 009c1d1776e73e13c0dd15f78a0a3db77c471b8535362a3759e1b320709ec3e0

## New system contract: [remove-inflation-to-wps](https://github.com/meet-one/eosio.contracts/tree/remove-inflation-to-wps)

```
ubuntu 18.04
eosio.cdt 1.5.0
```

eosio.system.wasm hash: 43d7b343ae17b4ee3d67c165dd9d60337288e152d4e8ea4f59ddeba05535052d

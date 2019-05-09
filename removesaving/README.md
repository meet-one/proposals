# Overview

The `removesaving` proposal remove 4% inflation to eosio.saving.


# Build latest eosio


```shell
git clone https://github.com/meet-one/eosio.contracts.git

cd eosio.contracts/contracts/eosio.system/src

git checkout remove-inflation-to-wps

eosio-cpp -contract=eosio.system -abigen eosio.system.cpp -o eosio.system.wasm -I=/usr/local/include/ -I=../include -I=../../eosio.token/include -I=./

shasum -a 256 eosio.system.wasm
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

## [Comparing changes](https://github.com/meet-one/eosio.contracts/compare/v1.6.0...meet-one:remove-inflation-to-wps?diff=unified)
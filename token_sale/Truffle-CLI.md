# Steps

1. Init truffle project
- `truffle init`


2. Change config files 
- `truffle.js`
    ```js
    networks: {
        development: {
        host: "127.0.0.1",
        port: "7545",
        network_id: "*" // match any network id
        },
        rinkeby: {
        host: "localhost",
        port: 8545,
        network_id: 4,
        gas: 4700000
        }
    }
    ´´´

3. Add Contract's on Contract's folder
    ex: `DappToken.sol`

4. Add new Migration on Migrations folder
    with [migration number]_[name of new migration].js

5. Run truffle migrations 
    Run `truffle migrate --reset`

6. Enter in truffle console 
    Run `truffle console`

    ```js 
    truffle(development)> DappToken.deployed().then(function(i){ token=i;})
    undefined
  
    truffle(development)> token.totalSupply().then(function(s){ totalSupply = s; })
    undefined

    truffle(development)> totalSupply
    BigNumber { s: 1, e: 6, c: [ 1000000 ] }

    truffle(development)> totalSupply.toNumber()
    1000000
    ´´´
7. Create a tests for Solidity contract 
    Run truffle test



    ```js 
    ´´´

8. Deploy with Geth
     
    1. start geth node 
    ```console
        
        geth --rinkeby --rpc --rpcapi="personal, eth, network, web3, net" --ipcpath "~/Library/Ethereum/geth.ipc"
    ´´´

    2. attach to geth console
    ```console
        
        geth attach
    ´´´
  
    


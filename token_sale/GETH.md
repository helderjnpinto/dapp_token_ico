# Deploy with geth node 


- Setup a new account
geth --rinkeby account new
            add one password 
            get address of the new account

- Attach to the console        
get attach

- Get Status of blocks sync 
eth.syncing

- Get your Eth accounts
eth.accounts
eth.accounts[0]

eth.getBalance(eth.accounts[0])

- Unlock account for 12 min
personal.unlockAccount(eth.accounts[0], null, 1200)


- Geth location of accounts created 
~/Library/Ethereum/rinkebey/keystore

    > each .json file is one account, and it's possible to import with metamask



## Deploy with truffle
- create account 
- put some ethers 
- after unlock de account 

truffle migrate --reset --compile-all --network rinkeby

### get TokenSaleInstance from contract deployed

geth attach 

var admin = eth.accounts[0]
var tokensAvailable = 750000
//contract address 
var tokenSaleAddress = '0x5118415....'

#### get the tokenSaleInstance with web3 

var abi = [...]
var tokenAddress = '0x900000' 

var TokenContract = web3.eth.contract(abi)

var tokenInstance = TokenContract.at(tokenAddress)

// call functions on contract 
tokenInstance.name()

// transfer tokens from admin account 
tokenInstance.transfer(tokenSaleAddress, tokensAvailable, { from: admin })

// get balance

tokenInstance.balanceOf(admin)
tokenInstance.balanceOf(tokenSaleAddress)









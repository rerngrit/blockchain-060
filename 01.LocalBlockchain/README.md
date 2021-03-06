# Setting a private blockchain locally

1. **Execute StartGethMining script**
    * Launch PowerShell
    * Execute the following comand

            ./00.Setup/windows/StartGeth.ps1

# Manual Steps #
1. **[Download GoEthereum]**
    Download and extract the files. Add geth to your local path or use the installer.

2. **Initialize the genesis block**

            geth --datadir .\data init genesis.json

3. **Start GoEthereum with mining enabled**
    By default when geth launches with mining enabled it will attempt to consume all possible resources
    the command below will launch geth only running two threads which should leave CPU cycles to do other 
    activities. The network id is a random number that was selected to ensure this network is isolated.

            geth --datadir .\data --mine --minerthreads 2 --networkid 54321

# FAQ #
* What are the passwords on the files in they keystore folder?

    There is currently no password on any of the files in the key store folder.
* Is there a way to not run mining locally?
    
    Yes it is possible to not run mining locally. In order to do this a miner would need to be running on another computer.
    One of the easiest ways to accomplish this is to leverage Azure following the [Ethereum Arm Template](https://github.com/EthereumEx/ethereum-arm-templates/tree/master/ethereum-consortium)
* Where can I find more information about genesis.json?
    
    There is currently no great definitive guide to the genesis.json, but  this post on [Stack Exchange](http://ethereum.stackexchange.com/questions/2376/what-does-each-genesis-json-parameter-mean) does a good job of highlighting each of the values.
* What is the keystore folder?
    
    More information about managing accounts and the keystore folder may be found on the [Ethereum Wiki](https://github.com/ethereum/go-ethereum/wiki/Managing-your-accounts) 
* How can I create additional accounts?
    * Navigate to [My Ether Wallet](http://myetherwallet.com)
    * Type in a password that will be used to secure the file generated
    * Download the Keystore file. We'll use this later.
    * Copy the address ex. 0x0000000000000000000000000000000000000000

  


[Download GoEthereum]:https://geth.ethereum.org/downloads/
# Blockchain
![logo.jpg](Images/logo.jpg)

# Environment setup instructions and dependencies.

## **Go Ethereum**

Visit https://geth.ethereum.org/ install the Go Ethereum Tools to create our blockchain, from the genesis block to mining tokens and making transactions.

 Click on the **"Geth & Tools 1.9.7"** to download the applications bundle archive if you are running **OS X**.

Decompress the archive in the location of your preference in your hard drive.
## **MyCrypto**
Open your browser and navigate to the downloads page at https://download.mycrypto.com/.



NOW LETS BEGIN!

# Instructions

Open a new terminal window and nagivate to Directory where we installed Ethereum Tools and follow these commands:

* Run the `./puppeth command.`
* Type the network name "solo" and hit enter to move forward in the terminal

![tm7](images/tm7.png)

* Type `2` to pick the `Configure new genesis` option, then `1` to `Create new genesis from scratch`
* Type `1` to choose `Proof of Work` and continue.
![tm8](images/tm8.png)

* Copy and paste an address from your Ethereum wallet in MyCrypto, without the `0x` prefix.
 ![mc5](images/mc5.png)

* Hit enter again on the blank `0x` address to continue the prompt:

 * Enter `827` as the `Chain ID` number. 
 ![tm1](images/tm1.png)

* Create the first node's data directory using the geth command and a couple of command line flags by running the following line in your terminal window 

./geth account new --datadir node1

./geth account new --datadir node2

 ![tm5](images/tm5.png)

* Initialize the first node and the second node with the following commands

 >./geth init solo.json --datadir node1

 >./geth init solo.json --datadir node2

 ![tm6](images/tm6.png)

 

>### `node1` will be a full node that is also mining.

>### `node2` will be a full node that exposes an RPC port, allowing you to talk to it with MyCrypto.

* Launch the first node into mining mode with the following command:

 `./geth --datadir node1 --mine --minerthreads 1`
 
 >### The `--mine` flag tells the node to mine new blocks.

 >### The `--minerthreads` flag tells `geth` how many CPU threads, or "workers" to use during mining. 

* Scroll up in the terminal window where `node1` is running, and copy the entire `enode://` address (including the last `@address:port` segment) of the first node located in the `Started P2P Networking` line:
 ![tm10](images/tm10.png)

* Open another terminal window and navigate to the same directory as before.

* Launch the second node, enable RPC, change the sync port, and pass the `enode://` address of the first node in quotes by running the following command:

  ![tm11](images/tm11.png)


>### The `--rpc` flag enables us to talk to our second node, which will allow us to use MyCrypto 


>### The `--bootnodes` flag allows you to pass the network info needed to find other nodes in the blockchain. This will allow us to connect both of our nodes.
 ![tm9](images/tm9.png)


* Open up MyCrypto to get the private key of the ETH address you use to pre-fund your chain. Be sure the `Kovan` network is selected.

* Unlock your wallet using your mnemonic phrase and choose the address you want to inspect.
 ![mc6](images/mc6.png)


* Select the ETH address you use to pre-fund your chain, and in the "Select" dropdown list, choose `Wallet Info`.
 ![mc1](images/mc1.png)


* Click on the eye icon next to the `Private Key` field, and copy and paste the private key of the wallet. Keep this handy, as you will use it in a bit.
 ![mc4](images/mc4.png)


* Open up MyCrypto, then click `Change Network` at the bottom left:
 ![mc7](images/mc7.png)

* Click "Add Custom Node", then add the custom network information that you set in the genesis.

* Make sure that you scroll down to choose `Custom` in the "Network" column to reveal more options like `Chain ID`:

* The chain ID must match what you came up with earlier.

* The URL is pointing to the default RPC port on your local machine. Use `http://127.0.0.1:8545`.
 ![mc3](images/mc3.png)


* On the left pane menu, click on "View & Send".

* Next, click on the "Private Key" option to continue.

* A new window will pop-up, paste the private key of the pre-fund wallet and click on the "Unlock" button to continue.
 ![mc8](images/mc8.png)


Now we're going to send a transaction to ourselves to test it out. Follow the next steps.

* Copy the pre-fund address into the "To Address" field, then fill in an arbitrary amount of ETH:
 ![mc9](images/mc9.png)


* Confirm the transaction by clicking "Send Transaction", and the "Send" button in the pop-up window.
 ![mc10](images/mc10.png)


* Click the `Check TX Status` when the green message pops up, confirm the logout:
 ![mc11](images/mc11.png)

* You can click the `Check TX Status` button to update the status.
 ![mc12](images/mc12.png)
# Congratulations!!!

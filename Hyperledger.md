# Hyperledger

**Hyperledger Fabric**: an open source enterprise-grade permissioned distributed ledger technology (DLT) platform
  * a permissioned blockchain network that gets set by the organizations that intend to set up a consortium
  * **members**: the organizations that take part in building the Hyperledger Fabric network, Each member organization in the blockchain network network is responsible to set up their peers for participating in the network 
  * Peers in the member organization receives transaction invocation requests from the clients inside the organization. 
  * A **client** can be any specific application/portal serving specific organization/business activites. The client application uses Hyperledger Fabric SDK or REST web service to interact with the Hyperledger Fabric network. 
  * Chaincode (similar to Ethereum Smart Contract) installed in peers causes to initiate transaction invocation request
    
## Hyperledger Architecture 

### How does Hyperledger Fabric works?

![Hyperledger Fabric Work Flow](https://miro.medium.com/max/1229/1*KU3B3nvtI_8lsUmP6Dh_4Q.png)

All the peers maintin **their  one ledger per channel** that they are subscribed to. Unlike Ethereum in Hyperledger Fabric blockchain network peers have different roles. In Hyperledger Fabric, the secret channels, configured among the peers and transactions among the peers of that channel, are visible only to them.  

* Endorser peer
  * validates the transaction (i.e., Check certificate details and roles of the requester)
  * executes the Chaincode and simulates the outcome of the transaction
  
  After performing two tasks, the Endorser may approve or disapprove thr transaction. 
  Only Endorser node executes the Chaincode, so there is no necessity to install Chaincode in each and every
  node of the network. It increases the scalability of the network. 

* Anchor peer
  * Anchor peer or cluster of Ahcor peers is configured at the time of Channel configuration. Ahcnor peer receives updates and broadcsts the update to the other peers in the organization. Anchor peers are discoverable. So any peer makred as Anchor peer can be discovered by the Ordered peer or any other peer. 

* Orderer peer 
  * the central communication channel for the Hyperledger Fabric network
  * be responsible for consistent Ledger state across the network
  * creates the block and delivers that to all the peers
  * two options to implement Order peer
    * Solo: suitable for development, so it should not be used for the production-ready network (single point failure)
    * Kafka: production-ready Hyperledger Fabric network, messaging software that has high throughput fault tolerant feature 
    
* **Work flow**

1. A participant in the member Organization **invokes a transaction request through the client application**.
2. (Client) Client application **broadcasts the transaction invocation request to the Endorser peer**.
3. (Endorser) Endorser peer **checks the Certificate details and others to validate the transaction**. Then it **executes the Chaincode (ie. Smart Contract)** and returns the Endorsement **responses to the Client**. Endorser peer **sends transaction approval or rejection as part of the endorsement response**.
4. (Client) The client now **sends the approved transaction to the Orderer peer** for this to be properly ordered and be included in a block.
5. (Orderer) Orderer node **includes the transaction into a block** and **forwards the block to the Anchor nodes of different member Organizations** of the Hyperledger Fabric network.
6. (Anchor nodes) Anchor nodes then **broadcast the block to the other peers** inside their own organization. These individual peers then update their local ledger with the latest block. Thus all the network gets the ledger synced.


## Software Components
**DOcker images**: server software delivered through Docker images

**Command-Line-Interface(CLI) Tools**: tools used to control the Docker images though configuration files or APIcalls

**Hyperledger Fabric SDKs(NPM packages)**: control the Docker images in much the same way as the CLI tools do
two NPM packages: *fabric-client* and *fablic-client-ca*

**Chaincode Interface(NPM package)**: *fablic-shim*, provides a mechanism for developing smart controls, aka., 
chaincoid, in JavaScript 


* Hyperledger frameworks
  - Iroha
  - Sawtooth
  - Fabric: a modular blockchain framework which acts as a foundation for developing blockchain-based
  products, solutions, and applcations using plug-and-play components that are aitmed for use within the private 
  enterprises.
  - Indy
  - Burrow
  - Grid 
  
* Hyperledger Tools
  - Aries 
  - Cello
  - Composer
  - Caliper
  - Quilt
  - Transact
  - Uras


  
## Hyperledger Framework


## Tutorials
* [Hyberledger Fabric Official Tutorials](https://hyperledger-fabric.readthedocs.io/en/latest/tutorials.html)
  * [Key Concepts](https://hyperledger-fabric.readthedocs.io/en/latest/key_concepts.html)
  * [Building Your First Network(BYFN)](https://hyperledger-fabric.readthedocs.io/en/latest/build_network.html)
  * [Writing Your First Application](https://hyperledger-fabric.readthedocs.io/en/latest/write_first_app.html)
  * [Key_concepts(한글문서)](https://hihellloitland.tistory.com/45?category=7662210)
  
  


### References 
1. How does Hyperledger Fabric works?: (https://medium.com/coinmonks/how-does-hyperledger-fabric-works-cdb68e6066f5)


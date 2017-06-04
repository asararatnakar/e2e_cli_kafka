## Enabled Kafka configuration for e2e_cli sanity test

### Prerequisites and setup: 

* [Docker](https://www.docker.com/products/overview) - v1.12 or higher
* [Docker Compose](https://docs.docker.com/compose/overview/) - v1.8 or higher
* [Git client](https://git-scm.com/downloads) - needed for clone commands
* Generate Docker images (using "make docker" in fabric repo)

#### Genearte Artifacts
* Crypto material will be generated using the **cryptogen** tool (pre-built) from fabric and mounted to all peers, the orderering nodes. More details about using cryptogen tool [here](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html#using-the-cryptogen-tool).
* An Orderer genesis block (genesis.block) and channel configuration transaction (mychannel.tx also anchorpeer update transactions Org1MSPanchors.tx & Org2MSPanchors.tx) has been pre generated using the **configtxgen** tool and placed within the _channel-artifacts_ folder.
  More details about using configtxgen tool [here](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html#using-the-configtxgen-tool).

### Clone the repo and Launch the network
```
git clone https://github.com/asararatnakar/e2e_cli_kafka
cd e2e_cli_kafka
./network_setup.sh
```

Once you have completed the above setup, you will be provisioned a local network with following configuration:

* 3 Zookeepers
* 3 Kafka broker
* 3 Orderer services
* 2 Peer Orgs (each Org contains a leader/anchor peer and a non-leader peer)
* And a **CLI** Container to execute the end-to-end flow

Once after test completes you must see the following log

```

===================== All GOOD, End-2-End execution completed ===================== 


 _____   _   _   ____            _____   ____    _____ 
| ____| | \ | | |  _ \          | ____| |___ \  | ____|
|  _|   |  \| | | | | |  _____  |  _|     __) | |  _|
| |___  | |\  | | |_| | |_____| | |___   / __/  | |___ 
|_____| |_| \_| |____/          |_____| |_____| |_____|

```

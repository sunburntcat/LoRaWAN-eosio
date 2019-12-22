# LoRaWAN-eosio
A collection of libraries and protocols to send eosio transactions over a LoRaWAN network.

The incentive for this comes from the ability to improve the network health of TheThingsNetwork by reducing bandwidth of Class B LoRa device communication structure. Currently every Class B device receives its own specific periodic network updates from LoRa gateways, even though gateways have a very constrained duty cycle. There has been at least one study that has shown that this makes TheThingsNetwork much less scalable.

With an LoRa-eosio structure, we eliminate the need for an application key and rely on eosio ECC signatures as the network keys for data integrity and authentication. The network servers that would normally be part of LoRa would be part of an eosio blockchain, where data can be accessed by any connected node on the network. Furthermore, devices termed "Class B" under TheThingsNetwork would all be able to share the same network state information downlinked by LoRa gateways... as opposed to selfishly requesting its own network data at the expense of the gateway's duty cycle.

Duty cycle rules for node devices can be set via smart contract, whereby breaking the rules results in no acceptance of transactions or unpleasant behavior toward the device by block producers.

Components include:
- Protocol for emitting and receiving transaction data and signatures
- Protocol for setting system requirements for node devices either via CPU/NET/RAM or by tokenization
- Packet forwarder to tell LoRa gateways how to send data to servers running eosio nodes

# EY
My personal thoughts on the use case:-

This Use Case asssumes running three Quorum nodes for this bidding use case. As per my experience with such projects users bidding for the item would not be using dedicated quorum nodes to initiate bidding transations but rather their keys. 1-1 relationship between Quorum nodes and parties would not be scalable(assuming parties B and C are end bidder and not a mediater oranisation taking bids on end users behalf). 

In case parties are end users we can allot them unique assymetric encryption keys within a single/multiple node/s in party A's control by exposing APIs(hitting personal.createAccount(...)) to these end Users via a web/Mobile dashboard and they can use these keys to send bids using their UI client ( placeBid.sendTransaction(...) )

THE DIRECTORY STRUCTURE IS AS FOLLOWS :



1. there are 3 main binaries : constellation-node , geth, bootnode
2. the node encryption keys : node1.pub, node1.key, node2.pub , etc
3. the application directory : app
4. the configuration file for the constellation nodes : constellation1.conf, constellation2.conf, constellation3.conf
5. enode_id_x : are used to generate respective enode URIs
6. static-nodes.json : list of enode addreses (used by raft protocol for consensus and quorum for node discovery) 
7. cnode_data : constellation node data for all 3 nodes 
8. qdata : quorum node data for all 3 nodes

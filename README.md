ClusterCoin
=====================================

http://clustercoin.org

Copyright (c) 2014 ClusterCoin Developers

What is ClusterCoin?
=====================================

In this project we are going to change the fundamental rule of block chain generation and improve block confirmation timing to mere few seconds. 
The key factor that currently prevents us to do this is a requirement to synchronize block chain between all parts of the network, located all over the world. If blocks will be generated too fast and users will not receive new blocks fast enough we have a huge risk to trigger fork in block chain that will eventually have a devastating effect on the currency and the market. 
For this project we invented a completely new clustering algorithm that will aggregate all transactions within several geographic clusters in order to minimize transmission time of transactions within certain cluster. each cluster will process transactions independently and then periodically synchronize transactions between geographic clusters. 
This approach will allow significantly speed up the block chain refresh rate on all nodes of the network, that will allow reduce block generation time and consequently reduce the time of transaction confirmation.

For more information, as well as an immediately useable, binary version of
the ClusterCoin software, see http://clustercoin.org/

ICO - Initial Coin Offering
=====================================
In order to fund the development of ClusterCoin we decided to organize the Initial Coin Offering. A total of 7,000,000 CLSTR (19% of total coins) will be sent upon the end of ICO to ICO investors. ICO service hosted by Bittrex

https://bittrex.com/Market/Index?MarketName=BTC-CLSTR

ClusterCoins reserved for ICO: 7,000,000 CLSTR (~19% of total coins)
ClusterCoin ICO price: 10,000 satoshi = 0.00010000 BTC
ICO success criteria: at least 10% of max amount sold in the ICO, i.e. at least 700,000 CLSTR

To achieve these truly ambitious goals that we set in the white paper we would need a considerable amount of funds. Our team consists of 4 experts in C/C++, web development and PR. We love crypto too! However, bitcoin has many shortcomings and we are going to significantly improve it. Anyone will be able to use ClusterCoin in their everyday life as blazing fast, anonymous and secure currency!

Message from Bittrex:
Bittrex will be hosting the ClusterCoin ICO. As a reminder, we are providing as escrow for the development team. We are not endorsing this coin or any others on our exchange. Please do your own research before trading. Below are the terms of the ICO.

* We will review the walet before initially adding it.
* We will hold all Premine Coins - 7,000,000 CLSTR
* The ICO will run for 7 days starting August 15th, 2014
* If success conditions are met, we will destroy all remaining coins.
* If success conditions are NOT met, we will buy back all outstanding coins at the ICO price
* Once the ICO is over we will verify there is working wallet and block explorer
* We will hold onto the funds in escrow for 3 days - at which time, we will release the funds.
* No sales of the coin will be allowed until after the ICO ends
* ALL SALES ARE FINAL AND THERE WILL BE NO REFUNDS - except if the success criteria isn't met.


FAQ
=====================================

So how do we collect and analyze information about previous transaction and make a decision for Geo-cluster creation?
----------------

Any coin consists of two types of nodes. Transaction nodes  – nodes that generate only transactions (common users) and Block nodes – nodes that generate blocks and transactions (pools). It is important to mention that not all of the transaction nodes have direct contact with pools – many of them only contact pools via other nodes. From the network synchronization perspective latency between pool and node becomes critical if we want to reduce confirmation time. I.e. How fast information reaches from a node that initiate transaction to the pool and how fast block information reaches from the pool back to the node.  This information can easily be gathered and used in order to make a decision about the requirement of introducing or destroying additional managed fork. Practically, we will use statistical analyses of latency time between nodes. We are planning to use all of the nodes in the network within this process.

How node will choose appropriate fork to work with its transaction?
----------------

Every node connected to the network will constantly determine effective latency for all fork gateways. The closest gateway will be used to serve this node. For example, if you live in the USA and you use your wallet installed on a smartphone – your managed fork will be one of the North American forks – all transactions (buys/sells) that you generate will be served by this fork. Then at some point you take a flight to the China. As soon as you arrive and connect your smartphone to the Internet your wallet automatically detects that now nearest fork – is one of the Chinas forks. While in China all your transactions will be served by the nearest Asian fork.

How do I make an inter-fork transactions? 
----------------

In between synchronizations each node will receive only blocks that belong to its nearest fork. Therefore, local transaction (i.e. Payment in the local store) will be confirmed very fast. Information of the transactions in other forks will be received as soon as the next synchronization block is generated (maximum 109 seconds). This is absolutely adequate timing of the international transactions, presuming that amount of such transactions will be relatively low compared to the local transactions.

So this means that now everyone will know my location?
----------------

No. Everyone will know what fork is serving you. We expect that single fork will be able to serve thousands of miles and millions of users. Besides, big brother already knows about you much more than just that.

Who will generate synchronization blocks? 
----------------

Synchronization blocks will be generated by pools located all over the world. In order to maintain high speed of block generation, those polls will maintain a direct connection to each other and coordinate each synchronization block generation. There will be no reward for this kind of blocks.

How do we deal with unstable block generation speed in managed artificial forks? 
----------------

It is common knowledge that block generation time have not constant but rather approximate value. In fact, all blocks are generated only close to the value that is defined in coin specification. This is why sometimes before generating block some of the forks will not be fast enough to process through usual 99 blocks. In this case we will use a custom algorithm in order to form special dummy-blocks that will fill remaining blocks in block chain. 

Will this require rebuilding all mining software?
----------------

No. All pools will be able to continue use of stratum-mining and mpos/nomp. The only difference in pools is that every pool will be now mining only one of the managed forks. Synchronization blocks will be generated by coin daemon without pool software interference.

How big will be changes in BitCoin source?
----------------

Huge. In order to test and implement such changes we will have to completely rewrite Bit Coin source and we will require quite a lot of resources to do that. This is probably most ambitious project in AltCoin history, but we got clear vision how to make it work. 

I saw your timeline, its pretty tight are you sure you will be able to deliver results that fast?
----------------

Yes, we are confident that we will be able to show first results in the days following coin launch. We are not just starting this project from scratch. We planned and prepared for this for the past 6 months and a lot of preliminary work is already done. 

Anonimity
----------------

We do not prioritize anonymity over speed of transaction, however it is clear that after each synchronization all of the transactions will be automatically mixed. Therefore Inter - Cluster transactions are practically unbreakable. If you are willing to sacrifice transaction confirmation speed to extra anonymity - you may enable "Use Sunc pool as mixing pool option" and send all your, even In-cluster, transactions through Sunc pool. The price is 109 second confirmation time instead of 3 seconds. 


---
layout: post
toc: true
title: "区块链的可扩展性：执行、存储和共识"
categories: 技术
tags: [区块链]
author:
  - chenleyi
---


# Blockchain Scalability: Execution, Storage, and Consensus 区块链的可扩展性：执行、存储和共识

August 9, 2023 2023 年 8 月 9 日

**DEFINITION 定义**

Blockchain scalability is the ability of a blockchain to process transactions, store data, and reach consensus as additional users are added to the network.
区块链的可扩展性是指随着网络用户的增加，区块链处理交易、存储数据和达成共识的能力。

Trust minimization is a valuable security property that [blockchain technology](https://chain.link/education-hub/blockchain) is uniquely positioned to generate—replacing handshakes, brand reputation, and paper contracts with guarantees based on computer code, cryptography, and decentralized consensus. These superior guarantees provided by blockchains form the basis of [cryptographic truth](https://blog.chain.link/what-is-cryptographic-truth/).
信任最小化是区块链技术独一无二的安全属性，它以基于计算机代码、密码学和去中心化共识的保证取代了握手言和、品牌声誉和纸质合同。区块链提供的这些卓越保证构成了加密真理的基础。

![ Cryptographic truth bring trust minimization to backend computing of applications and record keeping.](https://assets-global.website-files.com/5f75fe1dce99248be5a892db/643e9da76a474fa6a0f0c028_Cryptographic-Truth-Diagrams_Cryptographic-Truth-Venn.webp)

Cryptographic truth bring trust minimization to backend computing of applications and record keeping.
加密真理为应用程序和记录保存的后台计算带来了信任最小化。

Blockchains have succeeded in bringing trust minimization to new use cases including monetary policy (e.g. Bitcoin) and digital asset trading (e.g. [DEXs](https://chain.link/education-hub/what-is-decentralized-exchange-dex)). However, blockchains have historically struggled to maintain trust minimization for use cases that require speeds and costs comparable to traditional computing systems. These scalability limitations can be felt by users in the form of high transaction costs and cause developers to doubt whether blockchains can support high-value use cases that hinge on handling data in real time.
区块链已成功地将信任最小化引入新的使用案例，包括货币政策（如比特币）和数字资产交易（如DEX）。然而，区块链在要求速度和成本与传统计算系统相当的用例中，一直难以保持信任最小化。用户可以通过高昂的交易成本感受到这些可扩展性限制，并导致开发人员怀疑区块链是否能够支持依赖于实时处理数据的高价值用例。

With the ultimate goal of unlocking blockchain technology for all users and use cases, scalability is at the forefront of blockchain research and development as a key element in [smart contracts](https://chain.link/education/smart-contracts) becoming the preferred backend of major industries such as finance, supply chain, gaming, and beyond. The following post provides an overview of blockchain scalability, focusing on how blockchains differ from traditional computing before outlining the advantages and tradeoffs of different approaches to scaling the execution, storage, and consensus layers of blockchains.
区块链技术的最终目标是为所有用户和用例解锁区块链技术，因此可扩展性是区块链研究和开发的最前沿，是智能合约成为金融、供应链、游戏等主要行业首选后台的关键因素。以下文章概述了区块链的可扩展性，重点介绍了区块链与传统计算的不同之处，然后概述了扩展区块链执行层、存储层和共识层的不同方法的优势和权衡。

********Note:\*** *This blog is not an exhaustive list of every approach and aspect of blockchain scalability, as solutions are constantly being researched, tested, deployed, and updated due to the cutting-edge nature of blockchain research and development.*
***注：本博客并没有详尽列举区块链可扩展性的所有方法和方面，因为由于区块链研究和开发的前沿性，解决方案一直在不断研究、测试、部署和更新。

## Blockchains vs. Traditional Computing 区块链与传统计算

Before discussing how to scale blockchains, it’s important to first understand why blockchain computing is fundamentally different from traditional computing. In general, blockchains are valuable for three reasons:
在讨论如何扩展区块链之前，首先要了解为什么区块链计算与传统计算有本质区别。一般来说，区块链的价值在于以下三个原因：

- **Deterministic computation**—predefined coded logic executes exactly as written with a very high level of certainty.
  确定性计算--预定义的编码逻辑完全按照写入的内容执行，确定性非常高。
- **Credible neutrality**—there is no central administrator and no special network privileges, meaning anyone can submit transactions without fear of censorship or discrimination.
  可信的中立性--没有中央管理员，也没有特殊的网络特权，这意味着任何人都可以提交交易，而不必担心审查或歧视。
- **End-user verification**—the historical and current state of the blockchain’s ledger and the code underpinning the client software are auditable by anyone in the world.
  终端用户验证--世界上任何人都可以对区块链账本的历史和当前状态以及支持客户端软件的代码进行审计。

At a more technical level, blockchains are tasked with managing an internal ledger of data, which can represent asset ownership, contract state, or simply raw information. Most blockchain networks are managed by two overlapping yet distinct sets of participants: block producers and full nodes.
在更高的技术层面上，区块链的任务是管理内部的数据分类账，这些数据可以代表资产所有权、合同状态或简单的原始信息。大多数区块链网络由两组相互重叠但又截然不同的参与者管理：区块生产者和完整节点。

Block producers gather unconfirmed transactions submitted by users, check their validity, and place them into data structures called blocks. Block producers are generally referred to as miners in Proof-of-Work (PoW) chains or validators in Proof-of-Stake (PoS) chains, with PoW and PoS acting as Sybil-resistance mechanisms to ensure that blockchain ledgers remain live and immune to censorship.
区块生产者收集用户提交的未经确认的交易，检查其有效性，并将其放入称为区块的数据结构中。区块生产者在工作证明（PoW）链中通常被称为矿工，在摄取证明（PoS）链中则被称为验证者，PoW 和 PoS 充当了抵御假冒伪劣的机制，以确保区块链账本保持实时性并免受审查。

The blocks submitted by block producers are then accepted or rejected by [full nodes](https://en.bitcoin.it/wiki/Full_node)—entities that independently store a full copy of the chain’s ledger and continually validate new blocks but are not required to participate in block production. Full nodes are run by most block producers but also include end-users and key economic actors such as exchanges, RPC providers, and stablecoin issuers. Ultimately, full nodes keep block producers honest by rejecting invalid blocks, even in a situation where the [majority of block producers are malicious](https://dankradfeist.de/ethereum/2021/05/20/what-everyone-gets-wrong-about-51percent-attacks.html). This makes the creation of invalid blocks a waste of time and money, assuming a sufficient number of honest full nodes exist.
区块生产者提交的区块会被完整节点接受或拒绝--完整节点是独立存储链分类账完整副本并持续验证新区块的实体，但无需参与区块生产。全节点由大多数区块生产者运行，但也包括最终用户和主要经济参与者，如交易所、RPC 提供商和稳定币发行商。最终，全节点通过拒绝无效区块来保证区块生产者的诚实，即使在大多数区块生产者都是恶意的情况下也是如此。这使得创建无效区块成为浪费时间和金钱的行为，前提是存在足够数量的诚实完整节点。

![Users leverage full nodes to submit transaction to blockchains while miners/validators submit blocks to full nodes for validation.](https://assets-global.website-files.com/5f75fe1dce99248be5a892db/643e9df20d812209efa5e76e_Blockchain-Architecture_V2%20(1).webp)

Users leverage full nodes to submit transaction to blockchains while miners/validators submit blocks to full nodes for validation.
用户利用全节点向区块链提交交易，而矿工/验证者则向全节点提交区块进行验证。

Furthermore, the separation of full nodes and block producers prevents miners/validators from corrupting the blockchain by arbitrarily changing the protocol’s rules. This is part of a checks and balances system where block producers only have the power to order transactions but do not dictate the rules of the blockchain. The rules are governed by the full node community, which ideally anyone can easily participate in. To obtain a deeper understanding of the underlying architecture of blockchains, check out [Cryptographic Truth: The Future of Trust-Minimized Computing and Record-Keeping](https://blog.chain.link/what-is-cryptographic-truth/).
此外，全节点和区块生产者的分离可以防止矿工/验证者通过任意改变协议规则来破坏区块链。这是制衡系统的一部分，在这个系统中，区块生产者只有下达交易指令的权力，而不能主宰区块链的规则。规则由整个节点社区管理，理想情况下，任何人都可以轻松参与其中。要深入了解区块链的底层架构，请参阅《加密真理：信任最小化计算和记录保存的未来》（Cryptographic Truth: The Future of Trust-Minimized Computing and Record-Keeping）。

Reducing hardware requirements is crucial to [lowering the barrier to entry for running a full node](https://vitalik.ca/general/2021/05/23/scaling.html), which is historically how blockchains have remained decentralized—a critical component to generating trust minimization. However, decentralization is also the property that generally makes blockchains slow, since the network can for the most part only operate at the speed of the slowest node. This dynamic is described by the “blockchain trilemma”—also called the [scalability trilemma](https://vitalik.ca/general/2021/04/07/sharding.html)—which states that traditional blockchains can only maximize two out of the three properties: scalability, decentralization, and security.
降低硬件要求对于降低运行完整节点的门槛至关重要，这也是区块链一直保持去中心化的历史原因--这是产生信任最小化的关键要素。然而，去中心化也是通常使区块链运行缓慢的特性，因为网络在大多数情况下只能以最慢节点的速度运行。区块链三难"（也称可扩展性三难）描述了这一动态，指出传统区块链只能最大化可扩展性、去中心化和安全性这三项属性中的两项。

![The blockchain trilemma showcases the tradeoff that has to be made by traditional blockchains when attempting to maximize scalability, security, and decentralization.](https://assets-global.website-files.com/5f75fe1dce99248be5a892db/643e9e38fd4836aaad7519af_Blockchain-Trilemma-Multi-Chain-Execution-Sharding-Diagrams_Blockchain-Trilemma.webp)

The blockchain trilemma showcases the tradeoff that has to be made by traditional blockchains when attempting to maximize scalability, security, and decentralization.
区块链三难困境展示了传统区块链在试图最大限度地提高可扩展性、安全性和去中心化时必须做出的权衡。

One limitation of traditional blockchain models is that achieving scalability usually requires sacrificing decentralization, security, or some degree of both. For instance, a scalable and decentralized network will need to incentivize a large number of active participants to achieve high security. A scalable and secure network will generally raise the cost of running a node at the expense of decentralization. Furthermore, decentralized and secure networks keep node requirements low and the cost of attacks high but end up with scalability bottlenecks.
传统区块链模式的一个局限性是，要实现可扩展性，通常需要牺牲去中心化、安全性或两者的某种程度。例如，一个可扩展的去中心化网络需要激励大量活跃的参与者来实现高安全性。可扩展的安全网络通常会提高节点的运行成本，从而牺牲去中心化。此外，去中心化的安全网络对节点的要求较低，攻击成本较高，但最终会出现可扩展性瓶颈。

Unlike blockchains, traditional computing environments do not have to worry about decentralization since maximizing trust minimization is not their primary objective. This is why traditional computing networks are generally centralized and operated by for-profit companies, naturally reducing their cost and increasing their speed since the network is managed by a single entity that doesn’t have to design around making its computation independently verifiable by end-users.
与区块链不同，传统计算环境不必担心去中心化问题，因为最大化信任最小化并不是它们的首要目标。这就是为什么传统计算网络一般都是中心化的，由营利性公司运营，由于网络由单一实体管理，无需围绕使其计算可由终端用户独立验证进行设计，因此自然降低了成本，提高了速度。

As a result, the trust model of traditional computation environments is based on brand and legal contracts. In contrast, blockchain trust models rely on cryptography and game theory, offering independent verifiability and often supporting direct user participation. The trust model of traditional computing environments is simply not compatible with blockchain networks since they are subject to chokepoints such as external influence, single points of failure and control, and processes that can’t be audited by users.
因此，传统计算环境的信任模式以品牌和法律合同为基础。相比之下，区块链信任模式依赖于密码学和博弈论，提供独立的可验证性，通常支持用户直接参与。传统计算环境的信任模式与区块链网络根本不兼容，因为它们会受到外部影响、单点故障和控制以及用户无法审计的流程等阻塞点的影响。

These dynamics get at the essence of blockchain scalability: How do blockchains achieve the speed and costs of traditional computing environments while still maintaining strong trust-minimization properties of security and decentralization?
这些动态因素触及了区块链可扩展性的本质：区块链如何实现传统计算环境的速度和成本，同时仍然保持安全和去中心化的强大信任最小化特性？

## Three Key Properties of Blockchain Scaling 区块链扩展的三个关键特性

Blockchain scaling can be broken down into three general categories: execution, storage, and consensus. Below, we define each property and look at the core problem it seeks to solve. In practice, scaling one property is often dependent on or results in the scaling of one or two other properties.
区块链扩展可分为三大类：执行、存储和共识。下面，我们将对每种属性进行定义，并探讨其所要解决的核心问题。在实践中，一个属性的扩展往往依赖于或导致其他一个或两个属性的扩展。

### Blockchain Execution 区块链执行

Blockchain execution is the computation required to execute transactions and perform state changes. Transaction execution involves checking the validity of transactions (e.g. verifying signatures and token balances) and executing the on-chain logic needed to calculate state changes. State changes are when full nodes update their copy of the ledger to reflect new token transfers, smart contract code updates, and data storage.
区块链执行是指执行交易和进行状态更改所需的计算。交易执行包括检查交易的有效性（如验证签名和代币余额），以及执行计算状态变化所需的链上逻辑。状态变化是指全节点更新其账本副本，以反映新的代币转移、智能合约代码更新和数据存储。

The scalability of blockchain execution is commonly thought of in terms of transactions per second (TPS), but on a more general level, it refers to the number of computations per second since transactions can vary in complexity and cost. The more transactions that flow through a network, the more computations that need execution at any given time.
区块链执行的可扩展性通常是指每秒的交易量（TPS），但在更广泛的层面上，它指的是每秒的计算量，因为交易的复杂程度和成本各不相同。流经网络的交易越多，在任何给定时间内需要执行的计算就越多。

When scaling the execution layer, the main problem to solve is how to achieve more computations per second without substantially increasing the hardware requirements on individual full nodes that validate the transactions in blocks.
在扩展执行层时，要解决的主要问题是如何在不大幅增加以块为单位验证交易的各个完整节点的硬件要求的情况下，实现每秒更多的计算量。

### Blockchain Storage 区块链存储

Blockchain storage refers to the storage requirements of full nodes, which maintain and store a copy of the ledger. Blockchains have two general forms of storage:
区块链存储是指完整节点的存储需求，这些节点维护并存储账本的副本。区块链一般有两种存储形式：

- **Historical data** encompasses all the raw transactions and block data. Transaction data includes the origin and destination addresses, the amount sent, and the signature of every individual transaction. Block data includes the list of transactions and metadata from a specific block, such as its Merkle root, nonce, previous block hash, etc. Historical data doesn’t typically require quick access, and there only needs to be at least one honest entity making it available for download.
  历史数据包括所有原始交易和区块数据。交易数据包括每笔交易的起始地址和目的地地址、发送量和签名。区块数据包括交易列表和特定区块的元数据，如 Merkle 根、nonce、上一个区块的哈希值等。历史数据通常不需要快速访问，只需要至少有一个诚实的实体提供历史数据供下载。
- **Global state** is a snapshot of all the data that smart contracts can read from or write to, such as account balances and the variables within all smart contracts. Global state can be generally thought of as the database of a blockchain, which is required to validate incoming transactions. State is commonly stored within tree structures (e.g. Merkle trees) where access and modifications can be easily and quickly made by a full node.
  全局状态是智能合约可以读取或写入的所有数据的快照，例如账户余额和所有智能合约中的变量。全局状态一般可视为区块链的数据库，是验证传入交易所必需的。状态通常存储在树形结构（如梅克尔树）中，全节点可以方便快捷地对其进行访问和修改。

Full nodes need access to historical data in order to sync to the blockchain for the first time and global state in order to validate new blocks and execute new state changes. As the ledger and associated storage grow, computation of state becomes slower and more expensive because nodes require more time and computations to read from and write to state. If a node’s memory storage becomes full, it will need to use disk space storage, which further slows down computation since nodes need to swap between storage environments during execution.
全节点需要访问历史数据，以便首次同步到区块链，还需要访问全局状态，以便验证新区块和执行新的状态更改。随着分类账和相关存储的增长，状态计算会变得更慢、更昂贵，因为节点需要更多的时间和计算来读取和写入状态。如果节点的内存存储空间已满，则需要使用磁盘空间存储，这将进一步减慢计算速度，因为节点在执行过程中需要在存储环境之间交换。

Blockchains with increasing storage requirements often experience state bloat—a situation in which, without hardware upgrades, it becomes harder for full nodes to stay synced to the current version of the ledger (i.e. the chain tip) and for users to sync up new full nodes. Some factors that may affect whether a blockchain experiences state bloat include the historical length of the ledger, the frequency of new block additions, the max size per block, and the amount of data that must be stored on-chain to verify transactions and execute state changes.
存储需求不断增加的区块链通常会出现状态膨胀--在这种情况下，如果不升级硬件，全节点就很难与当前版本的账本（即链尖）保持同步，用户也很难同步新的全节点。影响区块链是否会出现状态膨胀的一些因素包括分类账的历史长度、新区块添加的频率、每个区块的最大大小，以及为验证交易和执行状态更改而必须存储在链上的数据量。

When scaling the storage layer, the main problem to solve is how to allow blockchains to process and validate more data without increasing storage requirements for full nodes; i.e., where can data be stored long term without major changes to the trust assumptions of blockchains?
在扩展存储层时，要解决的主要问题是如何在不增加全节点存储需求的情况下让区块链处理和验证更多数据；也就是说，在不对区块链的信任假设产生重大改变的情况下，数据可以长期存储在哪里？

### Blockchain Consensus 区块链共识

Blockchain consensus is the method by which nodes in a decentralized network reach an agreement on the current state of the blockchain. Consensus is mostly concerned with achieving an honest majority in the face of a certain threshold of malicious actors and reaching finality; i.e., transactions are accurately processed and highly unlikely to ever be reversed. Blockchain consensus is generally designed around minimizing communication overhead in order to increase the upper bound on decentralization for stronger Byzantine fault tolerance and lower the time to finality for faster settlement.
区块链共识是去中心化网络中的节点就区块链当前状态达成一致的方法。共识的主要目的是在面对一定数量的恶意行为者时实现诚实的多数，并达到最终结果；即交易得到准确处理，并且极不可能被逆转。区块链共识通常是围绕最大限度地减少通信开销而设计的，目的是提高去中心化的上限，以实现更强的拜占庭容错能力，并缩短最终时间，加快结算速度。

When scaling the consensus layer, the main problem to solve is how to reach finality faster, cheaper, and with more trust minimization—all in a predictable, stable, and accurate manner.
在扩展共识层时，要解决的主要问题是如何以可预测、稳定和准确的方式，更快、更便宜、更大限度地减少信任，实现最终共识。

## Scaling the Execution Layer 扩展执行层

Below are five different approaches currently being taken to scale the execution layer of blockchains along with the advantages and tradeoffs of each. In practice, some of these approaches are combined for even greater execution capacity.
以下是目前用于扩展区块链执行层的五种不同方法，以及每种方法的优势和权衡。在实践中，其中一些方法被结合起来，以获得更大的执行能力。

### Vertical Scaling of Validator Hardware Requirements 验证机硬件要求的纵向扩展

Blockchain execution can be scaled by increasing the hardware requirements for block producers. Higher hardware requirements lead to each validator being able to perform more computations per second.
区块链的执行可以通过提高对区块生产者的硬件要求来扩展。硬件要求越高，每个验证器每秒的计算量就越大。

**Advantages:** Having a single decentralized network made up of high-computing-capacity validators leads to blockchains that can support larger blocks, faster block times, and lower transaction costs while still maintaining on-chain composability between smart contracts and potentially higher trust minimization than traditional computing models. Such blockchains can be particularly useful for high-frequency trading, gaming, and other latency-sensitive use cases.
优势拥有一个由高计算能力验证器组成的单一去中心化网络，区块链就能支持更大的区块、更快的区块时间和更低的交易成本，同时还能保持智能合约之间的链上可组合性，与传统计算模式相比，信任最小化程度可能更高。这种区块链尤其适用于高频交易、游戏和其他对延迟敏感的用例。

**Tradeoffs:** Vertical scaling of validators will limit network decentralization given the higher cost of running a validator or full node. Node costs will often increase over time, making it hard for most users to participate. Remaining decentralized will become dependent on[ Moore’s law](https://en.wikipedia.org/wiki/Moore's_law), which states that the number of transistors on a microchip doubles around every two years while the cost of computers halves. Higher full node costs can also increase the costs for end-users who want to directly verify activity happening on-chain, lowering trust minimization.
权衡：由于运行验证器或完整节点的成本较高，验证器的纵向扩展将限制网络的去中心化。节点成本往往会随着时间的推移而增加，导致大多数用户难以参与。摩尔定律指出，微芯片上的晶体管数量大约每两年翻一番，而计算机成本却减半。更高的全节点成本也会增加想要直接验证链上活动的最终用户的成本，从而降低信任最小化。

### Horizontal Scaling via Multi-Chain Ecosystems 通过多链生态系统实现横向扩展

An alternative to vertical scaling is horizontal scaling through the use of multiple independent blockchains or sidechains within a single ecosystem. Horizontal scaling spreads the computation of transactions in an ecosystem across many independent blockchains, with each chain having its own block producers and execution capacity.
纵向扩展的另一种方法是横向扩展，即在一个生态系统中使用多个独立的区块链或侧链。横向扩展将生态系统中的交易计算分散到多个独立的区块链上，每个区块链都有自己的区块生产者和执行能力。

**Advantages:** Multi-chain ecosystems enable the execution layer of each individual chain to have fully customizable features such as node hardware requirements, privacy features, gas token usage, virtual machine (VM) choice, permission settings, and more. This design is why multi-chain ecosystems sometimes result in dApp chains, where individual blockchains specialize in supporting individual dApps or small collections of dApps. Self-sovereign blockchains can also help isolate security risks, with one chain’s design choice for security not always affecting other chains in the ecosystem.
优势：多链生态系统使每个独立链的执行层具有完全可定制的功能，如节点硬件要求、隐私功能、气体令牌使用、虚拟机（VM）选择、权限设置等。这种设计就是多链生态系统有时会产生 dApp 链的原因，即单个区块链专门支持单个 dApp 或小型 dApp 集合。自主权区块链还有助于隔离安全风险，一个链的安全设计选择不会总是影响生态系统中的其他链。

**Tradeoffs:** Multi-chain ecosystems require each blockchain to bootstrap its own security through a native token that’s issued in an inflationary manner. Though this is standard in the early growth stages of blockchains, it may prove difficult to move towards a less dilutive, more sustainable economic model based on on-chain user fees since user fees will be spread across many independent blockchains. There are also composability challenges since dApps and tokens that want to interoperate don’t always exist on the same blockchain.
权衡：多链生态系统要求每个区块链通过以通货膨胀方式发行的本地代币来启动自身的安全性。虽然这是区块链早期发展阶段的标准做法，但由于用户费用将分摊到许多独立的区块链上，因此可能很难转向稀释性更低、可持续性更强的基于链上用户费用的经济模式。此外，由于希望互操作的 dApp 和代币并不总是存在于同一个区块链上，因此还存在可组合性方面的挑战。

### Horizontal Scaling via Execution Sharding 通过执行分片实现横向扩展

A similar yet unique approach to multi-chain scaling is having a single blockchain that supports parallel execution across many different shards. Each shard essentially acts as its own blockchain, meaning many blockchains can execute in parallel. There is also a single main chain that has the sole purpose of keeping all shards synced together.
多链扩展的一个类似但又独特的方法是让一个区块链支持在许多不同的分片上并行执行。每个分块本质上都是自己的区块链，这意味着许多区块链可以并行执行。此外，还有一条主链，其唯一目的就是让所有分块保持同步。

In execution sharding, there is one pool of validators that is split up across shards to execute transactions. Nodes are randomly and regularly rotated so they don’t always execute/validate the same shard, with the number of shards configured to make the risk of corrupting any single shard statistically insignificant.
在执行分片中，有一个验证器池被分割到各个分片中执行事务。节点会随机定期轮换，因此它们不会总是执行/验证同一个分区，分区的数量配置也会使破坏任何一个分区的风险在统计上变得微不足道。

**Advantages:** All execution shards pull from the same pool of nodes, so there’s no need to bootstrap security on new shards. Assuming there is a large pool of nodes, every execution environment can achieve the same level of security. Execution sharding also doesn’t require raising the hardware requirements for nodes, as nodes only perform execution on one shard at a time. Shards can also operate with the same VM or use different configurations to meet the unique requirements of certain use cases.
优点所有执行分片都从相同的节点池中提取，因此无需在新分片上进行安全引导。假设有一个大型节点池，每个执行环境都能达到相同的安全级别。执行分片也不需要提高节点的硬件要求，因为节点一次只在一个分片上执行。分片也可以使用相同的虚拟机运行，或使用不同的配置，以满足某些用例的独特要求。

**Tradeoffs:** Each shard is limited in flexibility given that all nodes must be able to support the computation of every shard. There is also generally a limit to the number of shards one blockchain can support due to the increasing computation requirements put on the main chain and the risk of having too few nodes per shard. Furthermore, there are frictions when it comes to load balancing as well as implementation risk given that shared security models mean that all shards may be subject to the same vulnerability.
权衡：由于所有节点都必须能够支持每个分块的计算，因此每个分块的灵活性有限。由于对主链的计算要求越来越高，以及每个分块节点太少的风险，一个区块链所能支持的分块数量通常也是有限的。此外，由于共享安全模型意味着所有分块都可能存在相同的漏洞，因此在负载平衡和实施风险方面也存在摩擦。

![Multi-chain ecosystems generally do not share security across blockchains while execution sharding distributes security across shards from one pool of node operators.](https://assets-global.website-files.com/5f75fe1dce99248be5a892db/643e9eb9c1eec1c032895ed7_Blockchain-Trilemma-Multi-Chain-Execution-Sharding-Diagrams_Multi-Chain-Execution-Sharding.webp)

Multi-chain ecosystems generally do not share security across blockchains while execution sharding distributes security across shards from one pool of node operators.
多链生态系统通常不会在各区块链之间共享安全性，而执行分片则是由一个节点操作员池在各分片之间分配安全性。

‍

### Horizontal Scaling via Modularity 通过模块化实现横向扩展

Another approach to horizontal scaling is[ modular blockchains](https://polynya.medium.com/rollups-data-availability-layers-modular-blockchains-introductory-meta-post-5a1e7a60119d), where the architecture of blockchains is separated into multiple different layers; i.e., isolating the execution, data availability (DA), and consensus components. The most popular way to perform execution in modular blockchain implementations is via[ rollups](https://vitalik.ca/general/2021/01/05/rollup.html), which move the computation and state off-chain into off-chain networks while storing transaction data on-chain. State changes computed off-chain are then proven on-chain proactively as valid using zero-knowledge proofs (zk-rollups) or invalid retroactively using fraud proofs (optimistic rollups).
横向扩展的另一种方法是模块化区块链，即把区块链的架构分成多个不同的层，即隔离执行、数据可用性（DA）和共识组件。在模块化区块链实现中，最常用的执行方式是通过卷积，将计算和状态从链上转移到链下网络，同时将交易数据存储在链上。链外计算的状态变化在链上使用零知识证明（zk-rollups）主动证明有效，或使用欺诈证明（乐观rollups）追溯无效。

**Advantages:** Modular blockchains offload transaction execution and state to a cheaper, leaner, and higher-throughput computing environment while still inheriting the security of the underlying blockchain used for settlement. This is because the consensus process, in which the validity of off-chain computation performed by the execution layer is verified, is carried out by an existing decentralized baselayer (i.e. L1) blockchain. Intuitively, this means the computational bandwidth of a baselayer blockchain can be used more efficiently because full nodes don’t need to execute every transaction. Full nodes just need to verify succinct proofs and store a small amount of transaction data.  
优势：模块化区块链可将交易执行和状态卸载到更便宜、更精简、吞吐量更高的计算环境中，同时仍可继承用于结算的底层区块链的安全性。这是因为共识过程是由现有的去中心化基层（即 L1）区块链执行的，在共识过程中，执行层执行的链外计算的有效性得到验证。直观地说，这意味着可以更有效地利用基层区块链的计算带宽，因为全节点不需要执行每一笔交易。全节点只需要验证简洁的证明并存储少量的交易数据。

Rollups can also support escape hatches for trust minimization; i.e., if a rollup network is not working properly, users can withdraw their crypto and submit it to the baselayer blockchain. Many modular networks can also amortize user costs; i.e., there are fixed costs for verifying the proof of a zk-rollup on the baselayer blockchain, meaning consensus costs can be reduced as usage increases since they are shared amongst a larger number of users. Furthermore, rollups have a 1-of-n trust model—only one honest node is required to ensure the correctness and liveness of the computation.
卷积网络还可以支持信任最小化的 "逃生舱"；也就是说，如果卷积网络无法正常运行，用户可以撤回他们的加密货币，并将其提交给基层区块链。许多模块化网络还可以摊销用户成本；也就是说，在基层区块链上验证 zk-rollup 的证明是有固定成本的，这意味着共识成本可以随着使用量的增加而降低，因为这些成本是由更多用户分摊的。此外，卷积具有 1-of-n 的信任模型，只需要一个诚实的节点就能确保计算的正确性和有效性。

**Tradeoffs:** Modular blockchains may not be as fast or as cheap as sidechains or standalone chains since most approaches leverage the use of a baselayer blockchain’s limited and sometimes expensive block space for security. Current approaches to modular networks also commonly carry upgradability risks that require governance intervention (outside immutable enshrined rollups) and may result in liquidity fragmentation and composability challenges if some dApps remain on a baselayer blockchain while others run across different off-chain execution layers. Finally, implementing a rollup or other modular blockchain designs is a newer and more complex process than launching a new standalone blockchain.
权衡：模块化区块链可能没有侧链或独立链那么快或便宜，因为大多数方法都是利用基层区块链有限的、有时甚至是昂贵的区块空间来保证安全性。目前的模块化网络方法通常还存在可升级性风险，需要治理干预（在不可变的嵌入式卷积之外），如果一些 dApp 保留在基层区块链上，而其他 dApp 在不同的链外执行层上运行，则可能导致流动性分散和可组合性挑战。最后，与推出新的独立区块链相比，实施卷积或其他模块化区块链设计是一个更新、更复杂的过程。

![A proposed way to scale Ethereum is modular blockchains, separating the execution, data availability, and consensus layers](https://assets-global.website-files.com/5f75fe1dce99248be5a892db/643e8d21b07072738dcdad9d_modular_blockchains.jpeg)

A proposed way to scale Ethereum is modular blockchains, separating the execution, data availability, and consensus layers ([source](https://coinyuppie.com/read-the-ethereum-era-of-modularity-in-one-article/)).
扩展以太坊的一种建议方式是模块化区块链，将执行层、数据可用性层和共识层分开（资料来源）。

### Payment and State Channels 付款和国家渠道

Payment and state channels can be used for blockchain scaling by allowing users to lock cryptocurrency into a multisig smart contract with other parties and then exchange signed messages off-chain representing a transfer of asset ownership and/or change of state without making any on-chain transactions. Users only need to make on-chain transactions when opening a channel and closing a channel.
支付和状态通道可用于区块链扩展，允许用户将加密货币锁定到与其他方签订的多位智能合约中，然后在链下交换代表资产所有权转移和/或状态变化的签名消息，而无需进行任何链上交易。用户只需在打开通道和关闭通道时进行链上交易即可。

The multisig contract is used to ensure the correct settlement of the channel by having users cryptographically sign each interaction, with each signature accompanied by a nonce so the smart contract can verify the correct order of transactions.
多签名合约用于确保通道结算的正确性，它让用户对每次交互进行加密签名，每次签名都附带一个 nonce，这样智能合约就能验证交易的正确顺序。

**Advantages:** Payment and state channels allow transfers of cryptocurrency to happen in real-time for zero cost and near-instant latency. Payment channels make micropayments feasible, which are often not possible on a baselayer blockchain. They also allow the cryptocurrency locked in the channel to be settled swiftly on-chain if both parties cooperate.
优势：支付和状态通道允许以零成本和近乎即时的延迟实时转移加密货币。支付通道使小额支付成为可能，这在基层区块链上通常是不可能的。如果双方合作，它们还能让锁定在通道中的加密货币在链上迅速结算。

**Tradeoffs:** State/payment channels require each participating party of a channel to be connected to the Internet to ensure their counterparties are not trying to use old messages to settle the channel on-chain. This often necessitates the use of watchtowers to continually monitor the channel and protect user funds. Payment channels also need to be pre-funded with liquidity, which can make large payments difficult and result in capital inefficiency.
权衡利弊：状态/支付通道要求通道的每个参与方都连接到互联网，以确保其交易对手不会试图使用旧信息在链上结算通道。这通常需要使用监视塔来持续监控通道并保护用户资金。支付渠道还需要预先注入流动资金，这可能会使大额支付变得困难，并导致资本效率低下。

Efficiently routing payments across a network of channels is a [difficult problem](https://en.wikipedia.org/wiki/Travelling_salesman_problem) that can result in failed transfers or the creation of a more centralized hub-and-spoke model to ensure participants have access to sufficient liquidity and short routes. Generally, state/payment channels work best between a known set of static participants but don’t work well with a dynamic or unbounded set of participants. There is also the ownership problem, where it’s difficult or often impossible for channels to represent objects that do not have a clear logical owner (e.g. DEX liquidity pool).
在渠道网络中有效地进行支付是一个棘手的问题，可能导致转账失败，也可能导致建立一个更加集中的中心辐射模式，以确保参与者获得足够的流动性和短路线。一般来说，状态/支付渠道在已知的静态参与者之间效果最佳，但在动态或无限制的参与者之间效果不佳。此外还有所有权问题，即通道很难或通常不可能代表没有明确逻辑所有者的对象（如 DEX 流动性池）。

## **Scaling Data Storage 扩展数据存储**

Below are six different approaches currently being taken to scale the storage layer of blockchains. In practice, some of these approaches are combined for even greater storage improvements.
以下是目前用于扩展区块链存储层的六种不同方法。在实践中，其中一些方法被结合起来，以实现更大的存储改进。

### Vertical Scaling of Blockchain Nodes 区块链节点的垂直扩展

Similar to vertical scaling of blockchain execution, vertical scaling of blockchain storage involves raising the hardware requirements of running a full node.
与区块链执行的纵向扩展类似，区块链存储的纵向扩展涉及提高运行一个完整节点的硬件要求。

**Advantages:** Blockchains with higher storage limits for full nodes can offer a large volume of cheap storage; i.e., full nodes can store more historical data and larger amounts of state. Direct full node storage enables easier access to on-chain data given that there are no additional storage layers or external dependencies.
优势：全节点存储限额较高的区块链可以提供大量廉价存储；也就是说，全节点可以存储更多历史数据和更大量的状态。由于没有额外的存储层或外部依赖关系，直接全节点存储可以更方便地访问链上数据。

**Tradeoffs:** Since there is more and more data to store over time, the decentralization of the blockchain becomes increasingly at risk as the costs of running a full node increase. With less decentralization, fewer trust-minimized assurances can be provided to users that data will be available and correct. State bloat can also lead to slower execution of blocks over time, increasing the strain on the network as a whole.
权衡利弊：随着时间的推移，需要存储的数据越来越多，随着运行一个完整节点的成本增加，区块链的去中心化风险也越来越大。去中心化程度越低，为用户提供的数据可用性和正确性的信任保证就越少。随着时间的推移，状态臃肿还会导致区块执行速度减慢，增加整个网络的压力。

### Data Sharding on Layer-1 Blockchains 第 1 层区块链上的数据分片

Another approach to scaling the data storage of blockchains is[ data sharding](https://vitalik.ca/general/2021/04/07/sharding.html). Data sharding splits the storage of the ledger and/or the data used to recreate the ledger across many shards, reducing an individual node’s storage requirements at any given time to that of a single shard or small set of shards.
扩展区块链数据存储的另一种方法是数据分片。数据分片将分类账和/或用于重建分类账的数据的存储分割到多个分片中，从而将单个节点在任何给定时间的存储需求减少到单个分片或一小组分片的存储需求。

**Advantages:** Data sharding allows blockchains to increase their capacity to store data cheaply without increasing the hardware requirements for individual nodes. Such an approach is beneficial for maintaining decentralization since it increases the ability of users to run their own nodes. Data sharding also provides greater storage capacity for rollups that store transaction data on baselayer blockchains—a requirement to rebuild the rollup’s state. Moreover, approaches such as Danksharding allow for a merged fee market for better load-balancing and inclusion of data.  
优势：数据分片允许区块链在不增加单个节点硬件要求的情况下，提高廉价存储数据的能力。这种方法有利于保持去中心化，因为它提高了用户运行自己节点的能力。数据分片还为在基层区块链上存储交易数据的卷积提供了更大的存储容量--这是重建卷积状态的要求。此外，Danksharding 等方法允许合并收费市场，以更好地平衡负载和纳入数据。

**Tradeoffs:** There may be limits on the number of shards one blockchain can support due to the increased load on the main chain. There is also a need for [data availability sampling](https://hackmd.io/@vbuterin/sharding_proposal) (DAS), which proves that historical data needed to reconstruct part of the ledger was available at one point (i.e. when the block was produced) without nodes actually having to download all the data themselves. Additionally, data sharding requires communication overhead to pass storage between nodes when rotating nodes to different shards. It also requires a large number of nodes to maintain high security—there must be a certain level of decentralization per shard, so the total pool of nodes needs to be large since it’s split out amongst all shards.
权衡：由于主链的负载增加，一个区块链可支持的分片数量可能会受到限制。此外，还需要进行数据可用性采样（DAS），以证明重建部分账本所需的历史数据在某一时刻（即区块产生时）是可用的，而无需节点自己下载所有数据。此外，数据分片需要通信开销，以便在将节点旋转到不同分片时在节点之间传递存储。它还需要大量节点来维持高安全性--每个分片必须有一定程度的去中心化，因此节点的总池需要很大，因为它被分割到所有分片中。

### Compressed On-Chain Data Storage With Modular Blockchains 利用模块化区块链进行压缩链上数据存储

Modular blockchains perform computation off-chain and then store transaction data or state differences either on-chain or off-chain. The data allows other nodes or users to rebuild the current or historical state of the ledger. When rollups employ on-chain data storage, transaction data is often[ compressed](https://research.arbitrum.io/t/compression-in-nitro/20) off-chain prior to being stored on-chain.
模块化区块链在链外执行计算，然后在链上或链外存储交易数据或状态差异。这些数据允许其他节点或用户重建账本的当前或历史状态。当卷积采用链上数据存储时，交易数据通常会在链上存储之前在链下进行压缩。

**Advantages:** Compressed on-chain data storage is the most secure form of data storage for modular blockchains because data is stored by all full nodes on the network. It also reduces the cost of storing data on the layer-1 blockchain. When combined with data sharding, rollups are provided access to a more efficient and cheaper on-chain storage environment for transaction data that scales better with increased usage.
优点压缩链上数据存储是模块化区块链最安全的数据存储形式，因为数据由网络上的所有完整节点存储。它还降低了在第一层区块链上存储数据的成本。当与数据分片相结合时，卷积可以访问更高效、更廉价的链上交易数据存储环境，并随着使用量的增加而更好地扩展。

**Tradeoffs:** On-chain storage availability is more expensive than off-chain storage, which may inhibit the ability of modular blockchains to match the scalability of less decentralized storage options. Compressing data may also drop parts of the data that are not strictly required for validation, potentially inhibiting a more granular analysis of chain activity based on that data.
权衡：链上存储的可用性比链下存储更昂贵，这可能会抑制模块化区块链的可扩展性，使其无法与去中心化程度较低的存储方案相媲美。压缩数据还可能会丢弃部分不需要严格验证的数据，从而可能阻碍根据这些数据对区块链活动进行更精细的分析。

### Off-Chain Data Storage in Modular Blockchain Designs 模块化区块链设计中的链外数据存储

Modular blockchains can store transaction data off-chain to further reduce on-chain storage requirements. This includes “validiums,” which publish zero-knowledge proofs on-chain while storing data off-chain. There are four main approaches to off-chain data storage by modular blockchains:
模块化区块链可以在链外存储交易数据，以进一步减少链上存储需求。这包括 "validium"，它在链上发布零知识证明，同时在链下存储数据。模块化区块链有四种主要的链外数据存储方法：

- **Centralized storage** consists of off-chain storage on a centralized platform. While it’s the cheapest way to store data, it can be subject to data withholding and security issues such as the centralized storage platform modifying data or going offline.
  集中存储包括集中平台上的离链存储。虽然这是最便宜的数据存储方式，但它可能会出现数据扣留和安全问题，如集中存储平台修改数据或离线。
- **Permissioned DACs** store data off-chain but provide on-chain attestations of that data being published correctly using a signature scheme from a small committee of trusted nodes, referred to as a data availability committee (DAC). The advantages and tradeoffs are similar to centralized storage solutions but with slightly better trust assumptions on availability.
  经授权的 DAC 在链外存储数据，但使用由可信节点组成的小型委员会（称为数据可用性委员会 (DAC)）提供的签名方案，在链上证明数据的发布是正确的。其优势和权衡与集中式存储解决方案类似，但在可用性方面的信任假设略胜一筹。
- **Permissionless DACs** store data off-chain but provide on-chain proofs using permissionless DACs with cryptoeconomic incentives to act honestly. Permissionless DACs are cheaper than on-chain storage solutions while being more secure than other off-chain solutions. The tradeoffs are that this is still less secure than on-chain storage and has yet to be achieved in production at scale with sustainable economics.
  无权限 DAC 在链外存储数据，但利用无权限 DAC 提供链上证明，并通过加密经济激励诚实行事。无权限 DAC 比链上存储解决方案更便宜，同时比其他链下解决方案更安全。但这样做的代价是，其安全性仍低于链上存储，而且尚未实现大规模生产，经济效益也难以为继。
- **Volitions** enable users to choose whether they want to store their transaction data on-chain or off-chain. Volitions are novel because they enable data availability solution options at the individual transaction level while allowing all transactions to share the same state root and consensus cost. However, this method is more complex than the others listed above and has yet to be achieved in production.
  Volitions 使用户能够选择将其交易数据存储在链上还是链下。Volitions 之所以新颖，是因为它可以在单个交易层面实现数据可用性解决方案选项，同时允许所有交易共享相同的状态根和共识成本。不过，这种方法比上面列出的其他方法更复杂，而且尚未投入生产。

### Data Pruning 数据剪枝

[Data pruning](https://eips.ethereum.org/EIPS/eip-4444) is a technique that enables blockchain full nodes to discard historical data beyond a specific block height. Data pruning is often paired with Proof-of-Stake checkpoints, where the transactions in blocks beyond the checkpoint are considered final; i.e. they can’t be reversed without major social consensus or a hard fork.
数据剪枝是一种技术，可使区块链全节点丢弃超过特定区块高度的历史数据。数据剪枝通常与 "认股证明"（Proof-of-Stake）检查点（checkpoints）配对使用，在检查点之外的区块中的交易被视为最终交易；也就是说，在没有达成重大社会共识或硬分叉的情况下，这些交易不能被逆转。

**Advantages:** Data pruning reduces the amount of data that a node needs to store or reference when participating in consensus—the ledger is smaller since historical data is already validated so it is safe to be pruned. Because the historical data has already been validated, it is no longer needed if the intent of operating a full node is just to validate future blocks as opposed to also offering historical look-backs.
优点数据剪枝减少了节点在参与共识时需要存储或引用的数据量--由于历史数据已经过验证，所以剪枝是安全的，这样账本就更小了。由于历史数据已经过验证，如果运行完整节点的目的只是验证未来区块，而不是同时提供历史回溯，则不再需要历史数据。

**Tradeoffs:** Data pruning relies on third parties (e.g. exchanges, block explorers, etc) to store historical data permanently in order to rebuild state back to the genesis block. However, it’s a 1-of-n trust model, so only one third party needs to store the data honestly in order for a full node to be able to recreate all historical state. With Proof-of-Stake offering checkpoints and [weak subjectivity](https://academy.binance.com/en/glossary/weak-subjectivity), this assumption becomes less relevant. However, such data is still important for on-chain analytics and block explorers.
权衡：数据修剪依赖于第三方（如交易所、区块探索者等）永久存储历史数据，以便将状态重建回创世区块。然而，这是一个 1-of-n 的信任模型，因此只需要一个第三方诚实地存储数据，全节点就能重建所有历史状态。有了 "股权证明 "提供的检查点和弱主观性，这一假设就变得不那么重要了。不过，这些数据对于链上分析和区块探索者来说仍然很重要。

### Statelessness, State Expiry, and State Rent 无国籍状态、国家失效和国家租金

There also exist methods focused around limiting the amount of state that full nodes have to store, particularly through state expiry,[ statelessness](https://notes.ethereum.org/@vbuterin/verkle_and_state_expiry_proposal), or state rent implementations.
此外，还有一些方法专注于限制全节点必须存储的状态量，特别是通过状态过期、无状态或状态租用来实现。

- **State expiry** designs allow nodes to prune state that hasn’t been accessed in a certain amount of time, yet utilize a type of merkle proof (called “witnesses”) to revive expired state if needed.
  状态过期设计允许节点删除在一定时间内未被访问的状态，并在需要时利用一种梅克尔证明（称为 "见证"）来恢复过期状态。
- **Statelessness** designs are where full nodes are not required to store state. Full nodes only need to validate new blocks with the inclusion of witnesses. Weak statelessness is when only block producers are required to store global state while all other nodes can verify blocks without storing state.
  无状态设计是指全节点无需存储状态。全节点只需要验证包含见证人的新区块。弱无状态设计是指只有区块生产者需要存储全局状态，而所有其他节点都可以验证区块，无需存储状态。
- **State rent** designs require that users pay to maintain limited state storage. State that is no longer being paid for is recycled and rented out to new users.
  国家租金设计要求用户付费以维持有限的国家存储。不再付费的状态将被回收并出租给新用户。

**Advantages:** Methods for limiting state storage requirements ultimately help cap the amount of state that individual nodes have to store. This helps alleviate state bloat, even amidst a growing ledger or increasing number of on-chain transactions. Limiting state storage is crucial for maintaining long-term end-user verification while still maintaining practical hardware requirements.
优点限制状态存储要求的方法最终有助于限制单个节点必须存储的状态量。这有助于缓解状态膨胀，即使在分类账不断增长或链上交易数量不断增加的情况下也是如此。限制状态存储对于保持长期的最终用户验证至关重要，同时还能满足实际的硬件要求。

**Tradeoffs:** Limiting state storage is a fairly novel approach and eliminates the idea of users paying a single time to have every single full node in the network store their state in perpetuity forever—a stark contrast to how blockchains handle state today. Furthermore, upgrading a blockchain that uses a traditional state storage model to a more limited state storage model is difficult and may break applications that made specific assumptions during development about state always being accessible. New state storage models may also make particular applications more expensive than they were previously.
权衡利弊：限制状态存储是一种相当新颖的方法，它消除了用户一次性付费让网络中每个完整节点永久存储其状态的想法--这与当今区块链处理状态的方式形成了鲜明对比。此外，将使用传统状态存储模型的区块链升级为更有限的状态存储模型非常困难，可能会破坏在开发过程中对状态始终可访问做出特定假设的应用程序。新的状态存储模型还可能使特定应用程序的成本比以前更高。

## **Scaling Consensus 扩大共识范围**

Below are four general goals when trying to scale blockchain consensus mechanisms as they pertain to more frequent block times, faster finality, and enhanced robustness against downtime or malicious attacks. Note that scaling consensus is not just about speed but also accuracy, stability, and security.
以下是在尝试扩展区块链共识机制时的四个总体目标，它们涉及更频繁的区块时间、更快的终结性以及增强对停机或恶意攻击的鲁棒性。请注意，扩展共识不仅要考虑速度，还要考虑准确性、稳定性和安全性。

### Increase Execution and Storage Capacity 提高执行和存储能力

A foundational component in scaling a blockchain’s consensus mechanism is increasing its computational and storage capacity without substantially raising the hardware requirements for full nodes. This will allow more nodes to participate in consensus or at least prevent existing nodes from dropping off the network as the ledger grows—helping maintain strong consensus guarantees around uptime, censorship resistance, accuracy, and security. If execution and storage capacity is raised to a significant level without meaningful impact on full nodes, blockchains may even be able to support faster block times and/or larger block sizes in a stable manner without sacrificing their core property of decentralization.
扩展区块链共识机制的一个基本要素是提高其计算和存储容量，同时不大幅提高对完整节点的硬件要求。这将允许更多节点参与共识，或至少防止现有节点随着分类账的增长而退出网络--有助于在正常运行时间、抗审查、准确性和安全性方面保持强有力的共识保证。如果在不对全节点产生重大影响的情况下将执行和存储容量提高到一个显著水平，区块链甚至可以在不牺牲其去中心化核心特性的情况下，稳定地支持更快的区块时间和/或更大的区块大小。

### Reduce Networking Bandwidth 减少网络带宽

Another way to approach scaling a blockchain’s consensus mechanism is to reduce networking bandwidth; i.e. the communication overhead (sending and receiving messages) required between full nodes in order to reach consensus. Instead of requiring that nodes be able to communicate between all other nodes (i.e. all-to-all voting), blockchains consensus can be designed so that nodes only need to communicate with a small portion of other nodes at any moment in time (e.g. sub-sampling). Some consensus designs do not use multi-round voting or communication schemes so the only communication required is the propagation of blocks, but this generally comes at the expense of probabilistic finality.
扩大区块链共识机制规模的另一种方法是减少网络带宽，即减少全节点之间为达成共识所需的通信开销（发送和接收消息）。区块链共识的设计可以不要求节点能够与所有其他节点进行通信（即全对全投票），而是使节点在任何时刻都只需要与一小部分其他节点进行通信（如子采样）。有些共识设计不使用多轮投票或通信方案，因此唯一需要的通信就是区块的传播，但这通常是以牺牲概率最终性为代价的。

### Increase Network Latency 增加网络延迟

There are also methods focused on trying to reduce network latency during consensus, particularly as it relates to lowering the time to finality. Some blockchain consensus mechanisms have instant finality either through multi-round sub-sampling or all-to-all voting rounds. Other blockchains implement checkpoints secured by a supermajority consensus of validators after a period of time, meaning blocks are considered final past the checkpoint since there can no longer be in-protocol re-orgs beyond it. Often a tradeoff between network latency and network bandwidth has to be made, although some hybrid approaches have been optimized for both.
还有一些方法专注于减少共识过程中的网络延迟，特别是与缩短最终时间有关的延迟。一些区块链共识机制通过多轮子抽样或全对全投票轮实现即时终结。其他区块链则在一段时间后通过验证者的超级多数共识实现检查点，这意味着区块在检查点之后被视为最终区块，因为在检查点之后就不能再进行协议内重新修订。通常情况下，必须在网络延迟和网络带宽之间做出权衡，不过一些混合方法已对两者进行了优化。

### Increase the Security Budget 增加安保预算

The trust minimization of consensus can also be scaled by increasing the security budget that funds nodes participating in consensus. This is generally done by achieving a monetary premium, having inflationary token rewards, and/or growing transaction fee revenue because demand for block space exceeds supply. Higher security budgets open up more potential revenue for participants, which may then increase the network’s decentralization since more nodes are incentivized to join. Blockchains can also require nodes to put up more stake or computational power to participate in consensus, although this risks increasing the centralization of the network if requirements become too high.
还可以通过增加为参与共识的节点提供资金的安全预算来实现共识信任最小化。这通常是通过货币溢价、通胀代币奖励和/或因区块空间供不应求而增加交易费收入来实现的。更高的安全预算会为参与者带来更多潜在收入，从而提高网络的去中心化程度，因为更多的节点有动力加入。区块链还可以要求节点投入更多的股权或计算能力来参与共识，但如果要求过高，则有可能加剧网络的中心化。

## A Scalable and Secure Cross-Chain Future 可扩展、安全的跨链未来

Blockchain scalability is at an exciting point in its development as demonstrated by the plethora of solutions being built, tested, and launched into production. With a strong focus on scaling while preserving trust minimization, blockchains are poised to cement themselves as the go-to backend for a wide variety of industries and use cases.
区块链的可扩展性正处于一个令人兴奋的发展阶段，正在构建、测试和投入生产的大量解决方案就证明了这一点。区块链非常注重在保持信任最小化的同时进行扩展，因此有望成为各种行业和用例的首选后端。

In support of the expanding multi-chain ecosystem, the Cross-Chain Interoperability Protocol (CCIP) is actively being developed on top of Chainlink to enable users to securely exchange data and tokens between different blockchains based on user-defined logic. CCIP is being built with a strong focus on security, as demonstrated by the development of a Risk Management Network, to enable cross-chain smart contracts and secure token bridging in a manner that doesn’t break the trust assumptions of blockchains. For more information about CCIP, check out: [Unlocking Cross-Chain Smart Contract Innovation With CCIP](https://blog.chain.link/unlocking-cross-chain-smart-contract-innovation-with-ccip/).
为支持不断扩大的多链生态系统，Chainlink 正在积极开发跨链互操作性协议（CCIP），使用户能够根据用户定义的逻辑在不同区块链之间安全地交换数据和代币。正如风险管理网络的开发所表明的那样，CCIP的构建非常注重安全性，以不破坏区块链信任假设的方式实现跨链智能合约和安全代币桥接。有关 CCIP 的更多信息，请查阅利用 CCIP 开启跨链智能合约创新。

![The proposed architecture of CCIP.](https://assets-global.website-files.com/5f75fe1dce99248be5a892db/64d0dcb2cc5b3055912e77b1_cross-chain-stack-v3.png)

The proposed architecture of CCIP.
CCIP 的拟议架构。

To learn more about Chainlink, visit the [Chainlink website](https://chain.link/) and follow the official [Chainlink Twitter](https://twitter.com/chainlink) to keep up with the latest Chainlink news and announcements.
欲了解更多有关 Chainlink 的信息，请访问 Chainlink 网站并关注 Chainlink 官方 Twitter，了解 Chainlink 的最新消息和公告。

## Related articles 相关文章 

[Verifiable Random Function (VRF)
可验证随机函数 (VRF)](https://chain.link/education-hub/verifiable-random-function-vrf)

[How To Thrive as a Web3 Founder
如何茁壮成长为 Web3 创始人](https://chain.link/education-hub/web3-founder)

[The Importance of Network Effects in Web3
网络效应在 Web3 中的重要性](https://chain.link/education-hub/web3-network-effects)

[Why True Randomness Is Important in Web3
为什么真正的随机性在 Web3 中非常重要](https://chain.link/education-hub/randomness-web3)

[Digital Identity on the Blockchain: Securing User Data With Chainlink
区块链上的数字身份：利用链克保护用户数据](https://chain.link/education-hub/blockchain-identity)

[What Is Staking? Blockchains, Oracles, and DeFi
什么是定价？区块链、](https://chain.link/education-hub/what-is-staking-crypto)

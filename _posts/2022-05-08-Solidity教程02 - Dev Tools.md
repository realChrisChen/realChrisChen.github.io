---
layout: post
toc: true
title: "Solidity教程02 - Dev Tools"
categories: Code
tags: [Solidity,区块链,eth]
author:
  - Chris Chen
---

### 必备的网站
* Solidity 视屏教学 [https://m.youtube.com/playlist?list=PLHmOMPRfmOxQ3HSlId8KAKxnt8yuyTZVk]
* Rinkeby Faucet[https://rinkebyfaucet.com/]
* Rinkeby 区块链浏览器[https://rinkeby.etherscan.io/]
* Remix 在线编写部署合约[https://remix.ethereum.org/#optimize=false&runs=200&evmVersion=null&version=soljson-v0.7.1+commit.f4a555be.js]
* Metamask 浏览器钱包 [https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn]


### 步骤

1. 在MetaMask创建一个Ether钱包
2. 在RinkebyFaucet上领取测试Ether
3. 在Remix上连接MetaMask钱包以及编写编译部署合约
4. 在Etherscan上查看合约状况以及使用合约


### 注意

1. 在浏览器上执行合约 Environment 选择 Javascript VM(London)就行，而要将合约部署到测试网则需要选择Injected web 3.
2. 版本选择 0.7.1 勾上 Auto compile 以实现自动编译
3. 在Etherscan上的Contract中，可以选择 verify and publish, 这样可以验证你的代码并将其开源
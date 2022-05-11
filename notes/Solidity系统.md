
## 1. 什么是智能合约

### Account 有两种

具体来说就是一种有Contract Code，另一种没有 

* External Owned Account(aka EOA)
有Address,有Account State(nonce, balance)
* Contract Account
有Address,有Account State(nonce, balance,storage hash[合约中可能有需要永久储存的记忆体空间就放这里面, Contract执行完后这个值不会被清掉],code hash[合约代码就放这里面])


### EOA
三种功能：  
* 转 Ether (Call)
* 部署 Contract (Create Contract)
* 呼叫 Contract 里面的特定 Function (Call Contract)


### EOA - Call

重要栏位  

* From： 送出者
* To: 接受者
* Value： 给多少Ether
* Data: 转账的备注


### EOA - Create Contract
重要栏位  
* From： 发送者
* To：留空，告诉大家这笔transaction要部署合约
* Data: 把Bytecode放进来
* Value：可以将Ether顺便送进你的合约

### EOA - Call Function
* 合约不会自己执行
* 想执行时必须送出一笔transaction

### 合约执行在哪里
* Ethereum 有一个沙盒环境叫做Ethereum Virtual Machine
* 避免每个人的电脑跑起来结果不同
* 统一的opcode，每个opcode/storage的规格固定(保证每个人执行合约时的话费相对公平)
* 没有随机性的opcode

### EVM 长什么样


<img src="https://i.postimg.cc/1zNDZMYg/Screenshot-20220508-134121-Kiwi-Browser.jpg">

为了储存资料，总共是会有三种结构
* Stack[很短的资料如Function的参数会放在这上面，执行借宿后会消失]
* Memory[如果你申请了一个很大的数组, 执行结束后会消失]
* Storage[运算结束之后，如果有一些特殊的值想永久留下，就会写入Storage]

### 如何跟智能合约互动
* 需要用到ABI (Application Binary Interface)

<img src = "https://i.postimg.cc/8Ps1zCLv/Screenshot-20220508-135840-Kiwi-Browser.jpg">

## 2. Dev Tools

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

## 3. Solidity代码的结构

### 1. 代码许可证
* 开放，开源
    * //SPDX-License-Identifier: <License>
        * Apache: 他人修改后可以闭源，修改过的文件都必须放置版权说明
        * MIT：他人修改后可以闭源，修改过的文件不必放版权说明，衍生软件广告可以用你的名字促销
        * BSD：他人修改后可以闭源，修改过的文件不必放版权说明，衍生软件广告不能用你的名字促销
* 不开放，自己使用，闭源
    * //SPDX-License-Identifier: UNLICENSED

### 2. Pragmas
* 更编译器相关的设定
* 目前只会用到与版本相关的



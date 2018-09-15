 ## **Requirements:**

> 5000 ZCR

> Dedicated IP

> Port 17291 Available

> Wallet ready, if you use linux [compile it](https://github.com/zcore-coin/source-code/wiki/How-to-compile-ZCore-on-Linux)
_(we will use zcored to rpc server and zcore-cli to rpc client)_




### 1) Make sure you know where is your ZCore data folder:

https://github.com/zcore-coin/zcore-source/wiki

### 2) To generate a new address, run:

`$ zcore-cli getnewaddress`

_This is the wallet that will receive the earnings of the masternode_
_You can use all earning without any problem, 5000 keeps locked until undo the masternode_

### 3) Now send exactly 5000 ZCR to the address generated at the 2nd step

### 4) Wait 15 confirmations 

### 5) Generate the masternode key:

`$ zcore-cli masternode genkey`

_Keep it for later_

### 6) After you waited 15 confirmations, close the wallet:

`$ zcore-cli stop`

### 7) In the folder of the 1st step, create an file or open it, with the name: zcore.conf

### 8) In the zcore.conf file, change or insert this lines:

```
rpcuser={ANY USER OF YOUR CHOICE}
rpcpassword={ANY PASSWORD OF YOUR CHOICE}
listen=1
server=1
daemon=1
logtimestamps=1
maxconnections=256
masternode=1
masternodeprivkey={GENKEY}
bind={EXTERNAL IP}:17291
```
 
#### **GENKEY** is the same from step 5
 
#### **EXTERNAL IP** must be a dedicated one, otherwise it wont work.

#### Do not use { }

### 9) Now start your wallet and check for the masternode status:
`$ zcore-cli masternode status`

***

## **FAQ**

**Will I receives every block?**

A. No, there's a line to be followed here, so you will have to wait your turn.

**Tip**: Keep eyes on the block winners with this commands: 

**masternode winners**

**masternode list rank**

**How much Masternode receives as reward?**

A. Masternodes receives 50% of the block generated, so will be paid 50% of the actual block reward.

There's 25% of halving every 394200 blocks.

**What means the following status "Node just started, not yet activated"?**

A. Your Masternode is starting and synchronizing... Wait a little bit.

**What means the following status "Masternode successfully started"?**

A. Your Masternode was successfully started... 

**What means the following status "Not capable masternode: Masternode not in masternode list"?**

A. You didnt pay the right price. Generate a new address, or make sure that your current address has 5000 ZCR. 

**What means the following status "Masternode input must have at least 15 confirmations"?**

A. Wait 15 confirmations to the 5000 ZCR before start the Masternode.

**My daemon is frozen?**

A. In the zcore.conf make sure that you have the line 'daemon=1' before start the daemon.
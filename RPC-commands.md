## Follow all rpc commands.

### For specific usage, download wallet and run: help "command"
### In order to use zcore-cli (RPC Client), you need to configure zcore.conf:

https://github.com/zcore-coin/zcore-source/wiki#ZCore-Data-Folder

#### Add/Change these lines:
```
rpcuser=ruser
rpcpassword=rpassword
rpcport=51314
listen=1
daemon=1
server=1
```

### Linux - RPC Client: 
`./zcore-cli COMMAND`

### Curl 
`curl --user 'User' --data-binary '{"jsonrpc":"1.0","id":"curltext","method":"getinfo","params":[]}' -H 'content-type:text/plain;' http://127.0.0.1:RPCPORT`

*User is the same **rpcuser **in zcore.conf
*Password is the same **rpcpassword **in zcore.conf
*PORT is the same **rpcport **in zcore.conf

### Desktop Wallet:
Go to **Tools / Debug Console** and run the command.


 Command          | Description                        | Params         | Sector
 -----------------|------------------------------------|----------------|-----------
getaddressbalance | Receive Balance from valid address | string         | AddressIndex
getaddressdeltas  | Receive deltas about addresses     | string         | AddressIndex     
getaddressmempool | Receive address mempol info        | string         | AddressIndex
getaddresstxids   | Receive all address txid           | string         | AddressIndex
getaddressutxos   | Receive all address txos           | string         | AddressIndex
getbestblockhash  | Receive best block hash till now   |                | Blockchain
getblock          | Receive block raw info             | string         | Blockchain
getblockchaininfo | All blockchain info                |                | Blockchain
getblockcount     | Actual block count                 |                | Blockchain
getblockhash      | Get best hash from a block         | int64          | Blockchain
getblockhashes    | Get best block hash between two timestamps | timestamp, timestamp | Blockchain
getblockheader    | Receive a block header             | string         | Blockchain
getblockheaders   | Receive block headers array            | string         | Blockchain
getchaintips      | Get chain tips blocks            |          | Blockchain
getdifficulty     | Get network actual difficulty            |          | Blockchain
getmempoolinfo    | Get local mempool info            | | Blockchain
getrawmempool     | Get raw info from mempool            |          | Blockchain
getspentinfo      | Verify spent info from a block            | string | Blockchain
gettxout          | Verify txid output | string | Blockchain
gettxoutproof     | Get hex data from txid array | string | Blockchain
gettxoutsetinfo   | Get last block txout | | Blockchain
verifychain       | Verify chain integrity | | Blockchain
verifytxoutproof  | Verify txid proof | | Blockchain
debug | Change debug category level | string | Control
getinfo | Get wallet and chain stats | string | Control
help | Get commands info | string(not required) | Control
stop | Close the wallet | | Control
generate | Generate blocks | int64 | Generating 
getgenerate | Get wallet generate status | | Generating  
setgenerate generate | Set generate status and proccessor cores to use | bool int64 | Generating  
getblocktemplate | Get next block template | | Mining
getmininginfo | Get local mining info | | Mining
getnetworkhashps | Get actual network hashrate | | Mining
prioritisetransaction | Accepts the transaction into mined blocks at a higher | string float64 int64 | Mining
submitblock | Attempts to submit new block to network | string | Network
addnode | Add a new node to local wallet | string string | Network
clearbanned | Clear all nodes banned | | Network
disconnectnode "node" | Disconnect an node not banned | | Network
getaddednodeinfo | Get addnode info | bool | Network
getconnectioncount | Get connections in local wallet | | Network
getnettotals | Get network info in local wallet| | Network
getnetworkinfo | Get local network info in a local wallet | | Network
getpeerinfo | Get connected peers in a local wallet | | Network
listbanned | | | Network
ping | | | Network
setban | | | Network
createrawtransaction | | | Rawtransactions 
decoderawtransaction | | | Rawtransactions 
decodescript | | | Rawtransactions 
fundrawtransaction | | | Rawtransactions 
getrawtransaction | | | Rawtransactions 
sendrawtransaction | | | Rawtransactions 
signrawtransaction | | | Rawtransactions 
createmultisig | | | Util 
estimatefee | Estimates the approximate fee per kilobyte | int | Util 
estimatepriority | Estimates the approximate priority a zero-fee transaction | int | Util 
estimatesmartfee | | | Util 
estimatesmartpriority | | | Util 
validateaddress | Validate an address | string | Util 
verifymessage | Verify a signed address message | string string | Util 
abandontransaction | Abbadon an not registered in blockchain transaction| | Wallet 
addmultisigaddress | | | Wallet 
backupwallet | Create a new backup | string | Wallet 
dumpprivkey | Dump address private key | string | Wallet 
dumpwallet | Dump all addresses private keys into a file | string | Wallet 
getaccount | Get an address account | string | Wallet 
getaccountaddress | Get an account address | string | Wallet 
getaddressesbyaccount | Get multiply addresses from a  account| string | Wallet 
getbalance | Get local balance | | Wallet 
getnewaddress | Get new address | string | Wallet 
getrawchangeaddress | Get next used address | | Wallet 
getreceivedbyaccount | Get all balance received into an account | string | Wallet 
getreceivedbyaddress | Get all balance received into an address | string | Wallet 
gettransaction | Get detailed information about in-wallet transaction | | Wallet 
getunconfirmedbalance | Get balance still unconfirmed | | Wallet 
getwalletinfo | Get local wallet info | | Wallet 
importaddress | Adds a script (in hex) or address that can be watched as if it were in your wallet but cannot be used to spend. | string string bool bool | Wallet 
importelectrumwallet | | | Wallet 
importprivkey | Import a private key address | string | Wallet 
importpubkey | Import a public key address | string | Wallet 
importwallet | Import a dumped wallet private keys file | string | Wallet 
instantsendtoaddress | Send an ammount to a address using InstantSend | string float64 | Wallet 
keepass | | | Wallet 
keypoolrefill | | | Wallet 
listaccounts | List all accounts balance | | Wallet 
listaddressgroupings | List all addresses and accounts balance | | Wallet 
listlockunspent | | | Wallet 
listreceivedbyaccount | List all accounts balance received  | | Wallet 
listreceivedbyaddress | List all txid to all addresses | | Wallet 
listsinceblock | List all receive,send,generated, before a block hash | string(not required) | Wallet 
listtransactions | List transactions from local wallet | | Wallet 
listunspent | List unspent tx | | Wallet 
lockunspent | Lock unspent | | Wallet 
move  | Move inside wallet, from one account to another | string string float64 | Wallet 
sendfrom  | Sent from an account to a address | string string float64 | Wallet 
sendmany  | Send multiple times. Amounts are double-precision floating point numbers. | string json| Wallet 
sendtoaddress  | Send to an address | string float64 | Wallet 
setaccount  | Set an address account name | string string | Wallet 
settxfee  | Set the transaction fee per kB. Overwrites the paytxfee parameter | float64 | Wallet 
signmessage  | | | Wallet 
walletlock  | Lock wallet, if does have an passphrase | | Wallet 
walletpassphrase  | Unlock wallet | string int64 | Wallet 
walletpassphrasechange  | Change actual passphrase | string string | Wallet 
getgovernanceinfo | Get governance stats | | ZCore 
getpoolinfo | Get pool info and privatesend | | ZCore
getsuperblockbudget | Returns the absolute maximum sum of superblock payments allowed.| | ZCore
gobject | Useful gobject interaction | string | ZCore
masternode  | Useful masternode interaction | | ZCore
masternodebroadcast  | Create an broadcast between masternodes | | ZCore
masternodelist  | List all masternodes | | ZCore
mnsync  | Masternode status | string | ZCore
privatesend  | Useful privatesend interaction | | ZCore
spork  | Sporks status | | ZCore
voteraw  | Compile and relay a governance vote with provided external signature instead of signing vote internally | string int string string string timestamp string | ZCore
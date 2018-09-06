Availabe Configuration commands to be set in zcore.conf or after zcore-cli / zcore-qt binaries.

Category | Command | Description
-|-|-
wallet | -? | Show all commands list.
wallet |-version| Print version and exit 
wallet |-alertnotify=<cmd>| Receive and display P2P network alerts (default: 1) 
wallet |-blocknotify=<cmd>| Execute command when a relevant alert is received or we see a really long fork (%s in cmd is replaced by message) 
wallet |-checkblocks=<n>| Execute command when the best block changes (%s in cmd is replaced by block hash) 
wallet |-checklevel=<n>| How many blocks to check at startup (default: 288, 0 = all) 
wallet |-conf=<file>| How thorough the block verification of -checkblocks is (0-4, default: 3) 
wallet |-datadir=<dir>| Specify data directory 
wallet |-dbcache=<n>| Set database cache size in megabytes (4 to 16384, default: 100)
wallet |-loadblock=<file>| Imports blocks from external blk000??.dat file on startup 
wallet |-maxorphantx=<n>| Keep at most <n> unconnectable transactions in memory (default: 100) 
wallet |-maxmempool=<n>| Keep the transaction memory pool below <n> megabytes (default: 300) 
wallet |-mempoolexpiry=<n>| Do not keep transactions in the mempool longer than <n> hours (default: 72) 
wallet |-par=<n>| Set the number of script verification threads (-2 to 16, 0 = auto, <0 = leave that many cores free, default: 0) 
wallet |-prune=<n>| Reduce storage requirements by pruning (deleting) old blocks. This mode is incompatible with -txindex and -rescan. Warning: Reverting this setting requires re-downloading the entire blockchain. (default: 0 = disable pruning blocks, >550 = target size in MiB to use for block files) 
wallet |-reindex| Rebuild block chain index from current blk000??.dat files on startup 
wallet |-txindex| Maintain a full transaction index, used by the getrawtransaction rpc call (default: 1) 
wallet |-addressindex| Maintain a full address index, used to query for the balance, txids and unspent outputs for addresses (default: 0) 
wallet |-timestampindex| Maintain a timestamp index for block hashes, used to query blocks hashes by a range of timestamps (default: 0) 
wallet |-spentindex| Maintain a full spent index, used to query the spending txid and input index for an outpoint (default: 0) 
connection |-addnode=<ip>|Add a node to connect to and attempt to keep the connection open 
connection |-banscore=<n>|Threshold for disconnecting misbehaving peers (default: 100) 
connection |-bantime=<n>|Number of seconds to keep misbehaving peers from reconnecting (default: 3600) 
connection |-bind=<addr>|Bind to given address and always listen on it. Use [host]:port notation for IPv6 
connection |-connect=<ip>|Connect only to the specified node(s) 
connection |-discover|Discover own IP addresses (default: 1 when listening and no -externalip or -proxy) 
connection |-dns|Allow DNS lookups for -addnode, -seednode and -connect (default: 1) 
connection |-dnsseed|Query for peer addresses via DNS lookup, if low on addresses (default: 1 unless -connect) 
connection |-externalip=<ip>|Specify your own public address
connection |-forcednsseed|Always query for peer addresses via DNS lookup (default: 0) 
connection |-listen|Accept connections from outside (default: 1 if no -proxy or -connect) 
connection |-listenonion|Automatically create Tor hidden service (default: 1) 
connection |-maxconnections=<n>|Maintain at most <n> connections to peers (temporary service connections excluded) (default: 125) 
connection |-maxreceivebuffer=<n>|Maximum per-connection receive buffer, <n>*1000 bytes (default: 5000) 
connection |-maxsendbuffer=<n>|Maximum per-connection send buffer, <n>*1000 bytes (default: 1000) 
connection |-onion=<ip:port>|Use separate SOCKS5 proxy to reach peers via Tor hidden services (default: -proxy) 
connection |-onlynet=<net>|Only connect to nodes in network <net> (ipv4, ipv6 or onion) 
connection |-permitbaremultisig|Relay non-P2SH multisig (default: 1) 
connection |-peerbloomfilters|Support filtering of blocks and transaction with bloom filters (default: 1) 
connection |-port=<port>|Listen for connections on <port> (default: 17291 or testnet: 27291) 
connection |-proxy=<ip:port>|Connect through SOCKS5 proxy 
connection |-proxyrandomize|Randomize credentials for every proxy connection. This enables Tor stream isolation (default: 1)
connection |-seednode=<ip>|Connect to a node to retrieve peer addresses, and disconnect 
connection |-timeout=<n>|Specify connection timeout in milliseconds (minimum: 1, default: 5000) 
connection |-torcontrol=<ip>:<port>|Tor control port to use if onion listening enabled (default: 127.0.0.1:9051) 
connection |-torpassword=<pass>|Tor control port password (default: empty) 
connection |-upnp|Use UPnP to map the listening port (default: 0) 
connection |-whitebind=<addr>|Bind to given address and whitelist peers connecting to it. Use [host]:port notation for IPv6 
connection |-whitelist=<netmask>|Whitelist peers connecting from the given netmask or IP address. Can be specified multiple times. Whitelisted peers cannot be DoS banned and their transactions are always relayed, even if they are already in the mempool, useful e.g. for a gateway 
connection |-whitelistrelay|Accept relayed transactions received from whitelisted peers even when not relaying transactions (default: 1) 
connection |-whitelistforcerelay|Force relay of transactions from whitelisted peers even they violate local relay policy (default: 1)
connection |-maxuploadtarget=<n>|Tries to keep outbound traffic under the given target (in MiB per 24h), 0 = no limit (default: 0) 
wallet | -disablewallet | Do not load the wallet and disable wallet RPC calls 
wallet | -keypool=<n> | Set key pool size to <n> (default: 1000) 
wallet | -fallbackfee=<amt> | A fee rate (in ZCR/kB) that will be used when fee estimation has insufficient data (default: 0.0002) 
wallet | -mintxfee=<amt> | Fees (in ZCR/kB) smaller than this are considered zero fee for transaction creation (default: 0.0001) 
wallet | -paytxfee=<amt> | Fee (in ZCR/kB) to add to transactions you send (default: 0.00) 
wallet | -rescan | Rescan the block chain for missing wallet transactions on startup 
wallet | -salvagewallet | Attempt to recover private keys from a corrupt wallet.dat on startup 
wallet | -sendfreetransactions | Send transactions as zero-fee transactions if possible (default: 0) 
wallet | -spendzeroconfchange | Spend unconfirmed change when sending transactions (default: 1) 
wallet | -txconfirmtarget=<n> | If paytxfee is not set, include enough fee so transactions begin confirmation on average within n blocks (default: 2) 
wallet | -maxtxfee=<amt> | Maximum total fees (in ZCR) to use in a single wallet transaction; setting this too low may abort large transactions (default: 0.20) 
wallet | -upgradewallet | Upgrade wallet to latest format on startup 
wallet | -wallet=<file> | Specify wallet file (within data directory) (default: wallet.dat) 
wallet | -walletbroadcast | Make the wallet broadcast transactions (default: 1) 
wallet | -walletnotify=<cmd> | Execute command when a wallet transaction changes (%s in cmd is replaced by TxID) 
wallet | -zapwallettxes=<mode> | Delete all wallet transactions and only recover those parts of the blockchain through -rescan on startup (1 = keep tx meta data e.g. account owner and payment request information, 2 = drop tx meta data) 
wallet | -createwalletbackups=<n> | Number of automatic wallet backups (default: 10) 
wallet | -walletbackupsdir=<dir> | Specify full path to directory for automatic wallet backups (must exist) 
wallet | -keepass | Use KeePass 2 integration using KeePassHttp plugin (default: 0) 
wallet | -keepassport=<port> | Connect to KeePassHttp on port <port> (default: 19455) 
wallet | -keepasskey=<key> | KeePassHttp key for AES encrypted communication with KeePass 
wallet | -keepassid=<name> | KeePassHttp id for the established association 
wallet | -keepassname=<name> | Name to construct url for KeePass entry that stores the wallet passphrase 
wallet | -windowtitle=<name> | Wallet window title 
debug | -uacomment=<cmt> | Append comment to the user agent string 
debug | -debug=<category> | Output debugging information (default: 0, supplying <category> is optional). If <category> is not supplied or if <category> = 1, output all debugging information.<category> can be: addrman, alert, bench, coindb, db, lock, rand, rpc, selectcoins, mempool, mempoolrej, net, proxy, prune, http, libevent, tor, zmq, zcore (or specifically: privatesend, instantsend, masternode, spork, keepass, mnpayments, gobject), qt. 
debug | -gen | Generate coins (default: 0) 
debug | -genproclimit=<n> | Set the number of threads for coin generation if enabled (-1 = all cores, default: 1) 
debug | -help-debug | Show all debugging options (usage: --help -help-debug) 
debug | -logips | Include IP addresses in debug output (default: 0) 
debug | -logtimestamps | Prepend debug output with timestamp (default: 1) 
debug | -minrelaytxfee=<amt> | Fees (in ZCR/kB) smaller than this are considered zero fee for relaying, mining and transaction creation (default: 0.0001) 
debug | -printtoconsole | Send trace/debug info to console instead of debug.log file 
debug | -printtodebuglog | Send trace/debug info to debug.log file (default: 1) 
debug | -shrinkdebugfile | Shrink debug.log file on client startup (default: 1 when no -debug) 
chain | -testnet | Use the test chain 
chain | -litemode=<n> | Disable all ZCore specific functionality (Masternodes, PrivateSend, InstantSend, Governance) (0-1, default: 0) 
masternode | -masternode=<n> | Enable the client to act as a masternode (0-1, default: 0) 
masternode | -mnconf=<file> | Specify masternode configuration file (default: masternode.conf) 
masternode | -mnconflock=<n> | Lock masternodes from masternode configuration file (default: 1) 
masternode | -masternodeprivkey=<n> | Set the masternode private key 
privatesend | -enableprivatesend=<n> | Enable use of automated PrivateSend for funds stored in this wallet (0-1, default: 0) 
privatesend | -privatesendmultisession=<n> | Enable multiple PrivateSend mixing sessions per block, experimental (0-1, default: 0) 
privatesend | -privatesendrounds=<n> | Use N separate masternodes for each denominated input to mix funds (2-16, default: 2) 
privatesend | -privatesendamount=<n> | Keep N ZCR anonymized (default: 1000) 
privatesend | -liquidityprovider=<n> | Provide liquidity to PrivateSend by infrequently mixing coins on a continual basis (0-100, default: 0, 1=very frequent, high fees, 100=very infrequent, low fees) 
instantsend | -enableinstantsend=<n> | Enable InstantSend, show confirmations for locked transactions (0-1, default: 1) 
instantsend | -instantsenddepth=<n> | Show N confirmations for a successfully locked transaction (0-9999, default: 5) 
instantsend | -instantsendnotify=<cmd> | Execute command when a wallet InstantSend transaction is successfully locked (%s in cmd is replaced by TxID) 
node | -bytespersigop | Minimum bytes per sigop in transactions we relay and mine (default: 20) 
node | -datacarrier | Relay and mine data carrier transactions (default: 1) 
node | -datacarriersize | Maximum size of data in data carrier transactions we relay and mine (default: 83) 
node | -mempoolreplacement | Enable transaction replacement in the memory pool (default: 0) 
block | -blockminsize=<n> | Set minimum block size in bytes (default: 0) 
block | -blockmaxsize=<n> | Set maximum block size in bytes (default: 750000) 
block | -blockprioritysize=<n> | Set maximum size of high-priority/low-fee transactions in bytes (default: 10000) 
rpc server | -server | Accept command line and JSON-RPC commands 
rpc server | -rest | Accept public REST requests (default: 0) 
rpc server | -rpcbind=<addr> | Bind to given address to listen for JSON-RPC connections. Use [host]:port notation for IPv6. This option can be specified multiple times (default: bind to all interfaces) 
rpc server |-rpccookiefile=<loc> | Location of the auth cookie (default: data dir) 
rpc server |-rpcuser=<user> | Username for JSON-RPC connections 
rpc server |-rpcpassword=<pw> | Password for JSON-RPC connections 
rpc server |-rpcauth=<userpw> | Username and hashed password for JSON-RPC connections. The field <userpw> comes in the format: <USERNAME>:<SALT>$<HASH>. A canonical python script is included in share/rpcuser. This option can be specified multiple times 
rpc server |-rpcport=<port> | Listen for JSON-RPC connections on <port> (default: 18292 or testnet: 28292) 
rpc server |-rpcallowip=<ip> | Allow JSON-RPC connections from specified source. Valid for <ip> are a single IP (e.g. 1.2.3.4), a network/netmask (e.g. 1.2.3.4/255.255.255.0) or a network/CIDR (e.g. 1.2.3.4/24). This option can be specified multiple times 
rpc server |-rpcthreads=<n> | Set the number of threads to service RPC calls (default: 4) 
ui | -choosedatadir | Choose data directory on startup (default: 0) 
ui | -lang=<lang> | Set language, for example "de_DE" (default: system locale) 
ui | -min | Start minimized 
ui | -rootcertificates=<file> | Set SSL root certificates for payment request (default: -system-) 
ui | -splash | Show splash screen on startup (default: 1) 
ui | -resetguisettings | Reset all settings changes made over the GUI 


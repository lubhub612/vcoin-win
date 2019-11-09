# Vcoin 1.0.0

 **What is Vcoin?**

Vcoin is an implementation of the "Zerocash" protocol. Based on Bitcoin's code, it intends to offer a far higher standard of privacy through a sophisticated zero-knowledge proving scheme that preserves confidentiality of transaction metadata.

This software is the Vcoin node and command-line client. It downloads and stores the entire history of Vcoin transactions; depending on the speed of your computer and network connection, the synchronization process could take a day or more once the blockchain has reached a significant size.

**Join the conversation on Discord:
 https://discord.gg/38euHQX**
 
 **Join the conversation on Telegram:
  https://t.me/themoonroomchat**

# Vcoin  Windows Command Line Wallet
**Keep running wallet to strengthen the Vcoin  network. Backup your wallet in
many locations & keep your coins wallet offline.**

### Ports:
- RPC port: 16424
- P2P port: 16425

# How to install vcoin in windows

- Go to vcoin-win zip folder and click download button

- Download vcoin-win zip file & extract

- Download sprout.key & sapling.key files

   https://z.cash/downloads/sapling-output.params
   
   https://z.cash/downloads/sapling-spend.params
   
   https://z.cash/downloads/sprout-proving.key
   
   https://z.cash/downloads/sprout-verifying.key
   
   https://z.cash/downloads/sprout-groth16.params



- Copy & paste sprout-proving.key & sprout-verifying.key files to ZcashParams directory
  Run in command line (cmd)
```
make directory 
mkdir %APPDATA%\%ROAMING%\ZcashParams
cd %APPDATA%\%ROAMING%\ZcashParams

```
- Create vcoin.conf in Vcoin directory
```
make directory
mkdir %APPDATA%\%ROAMING%\Vcoin
echo  "rpcuser=myusername" > %APPDATA%\%ROAMING%\Vcoin\vcoin.conf
echo  "rpcpassword=mypassword" > %APPDATA%\%ROAMING%\Vcoin\vcoin.conf

```

Replace rpcuser & rpcpass by secure user & password.

```
notepad %APPDATA%\%ROAMING%\Vcoin\vcoin.conf

```

- Complete the vcoin.conf file

```
please add those  command  in vcoin.conf file to complete vcoin.conf
notepad %APPDATA%\%ROAMING%\Vcoin\vcoin.conf

listen=1
daemon=1
rpcport=16424
#rpcallowip=10.1.1.34
#rpcallowip=192.168.*.*
#rpcallowip=1.2.3.4/255.255.255.0
rpcallowip=127.0.0.1
rpctimeout=30
addnode=178.128.222.68
addnode=104.248.156.151
gen=1
equihashsolver=tromp
showmetrics=1
 #Use Secure Sockets Layer (also known as TLS or HTTPS) to communicate
# with vcoin -server or moonroomcashd
#rpcssl=1
# OpenSSL settings used when rpcssl=1
#rpcsslciphers=TLSv1+HIGH:!SSLv2:!aNULL:!eNULL:!AH:!3DES:@STRENGTH
#rpcsslcertificatechainfile=server.cert
#rpcsslprivatekeyfile=server.pem

```

- Run moonroomcashd.exe and wait few minutes to get synched.


# Check vcoin rpc commands in windows
 Run  vcoin-cli and check RPC commands
```
Run vcoin-cli in windows , then to go vcoin-win folder where it downloaded
first go to command-line(cmd)
like C:\Users\DD\Documents\src\vcoin-win>vcoin-cli  

```
```
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getinfo 
Returns an object containing various state info.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli help
user will get all rpc commands of vcoin
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli stop
Vcoin server stopping
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getnewwadress
will get a (T-address)  start with M1
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_getnewaddress
will get a (z-address) start with z
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_validateaddress "zaddress"
check address is validate or not
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli validateaddress "t-address"
check t-address is validate or not
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getwalletinfo
get various  wallet state info
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli listaddressgroupings
Lists groups of addresses which have had their common ownership
made public by common use as inputs or as the resulting change
in past transactions
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_listaddresses
Returns the list of Sprout shielded addresses belonging to the wallet.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_sendmany "fromaddress" '[{"address": "toaddress" ,"amount": xxx}]'
Send multiple times. Amounts are double-precision floating point numbers.
Change generated from a taddr flows to a new taddr address, while change generated from a zaddr returns to itself.
When sending coinbase UTXOs to a zaddr, change is not allowed. The entire value of the UTXO(s) must be consumed.
Before Sapling activates, the maximum number of zaddr outputs is 54 due to transaction size limits
1. "fromaddress"          The taddr or zaddr to send the funds from.
2. "amount"              An array of json objects representing the amounts to send.
3. "toaddress"           The address is a taddr or zaddr
Result:
"operationid"          (string) An operationid to pass to z_getoperationstatus to get the result of the operation.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_getoperationstatus (["operationid", ... ]) 
Result:
"    [object, ...]"      (array) A list of JSON objects
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_getoperationresult (["operationid", ... ]) 
Result:
"    [object, ...]"      (array) A list of JSON objects
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli listunspent
Returns array of unspent transaction outputs
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli listtransactions
Returns array of  transaction outputs in account
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli "vcoinaddress"
Returns the balance of a Vcoin address (taddr or zaddr) belonging to the node’s wallet.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getbalance
Returns the node's total available balance
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_gettotalbalance 
Return the total amount  of vcoin (both t-address and z-address) stored in the node’s wallet.
Result:
{
  "transparent": xxxxx,     (numeric) the total balance of transparent funds
  "private": xxxxx,         (numeric) the total balance of private funds (in both Sprout and Sapling addresses)
  "total": xxxxx,           (numeric) the total balance of both transparent and private funds
}
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getblock "blockhash" 
get serialized, hex-encoded data for the block
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getblockchaininfo
Returns an object containing various state info regarding block chain processing. 
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getpeerinfo
Returns data about each connected network node as a json array of objects.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli getmempoolinfo
Returns details on the active state of the TX memory pool.

Result:
{
  "size": xxxxx                (numeric) Current tx count
  "bytes": xxxxx               (numeric) Sum of all tx sizes
  "usage": xxxxx               (numeric) Total memory usage for the mempool
}
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli  getdifficulty

Returns the proof-of-work difficulty as a multiple of the minimum difficulty
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli setgenerate true -1
Set 'generate' true to turn generation on
Generation is limited to 'genproclimit' processors, -1 is unlimited.
See the getgenerate call for the current setting.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli setgenerate false
false to turn generation off.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli dumpprivkey "t-addr"
Reveals the private key corresponding to 't-addr'.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli backupwallet "/root/ws/vcoin-wallet-back-up"
give The full path of the destination file
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli encryptwallet "passphrase" 
WARNING: encryptwallet is disabled.
To enable it, restart zcashd with the -experimentalfeatures and
-developerencryptwallet commandline options, or add these two lines
to the vcoin.conf file:

experimentalfeatures=1
developerencryptwallet=1

Encrypts the wallet with 'passphrase'. This is for first time encryption.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli dumpwallet "filename"
Dumps taddr wallet keys in a human-readable format.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli gettransaction "txid"
Get detailed information about in-wallet transaction <txid>
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli importaddress "address"
Adds an address or script (in hex) that can be watched as if it were in your wallet but cannot be used to spend.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli importprivkey "vcoinprivkey"
Adds a private key (as returned by dumpprivkey) to your wallet.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli  importwallet "filename" 
Imports taddr keys from a wallet dump file (see dumpwallet).
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_importkey "zkey"
Adds a zkey (as returned by z_exportkey) to your wallet.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_importviewingkey "vkey"
Adds a viewing key (as returned by z_exportviewingkey) to your wallet.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_importwallet "filename"
Imports taddr and zaddr keys from a wallet export file (see z_exportwallet).
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_exportkey "zaddr"
Reveals the zkey corresponding to 'zaddr'.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_exportviewingkey "zaddr"
Reveals the viewing key corresponding to 'zaddr'.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_exportwallet "filename"
Exports all wallet keys, for taddr and zaddr, in a human-readable format.
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_listunspent
Results are an array of Objects
C:\Users\DD\Documents\src\vcoin-win>vcoin-cli z_listoperationids
Returns the list of operation ids currently known to the wallet.

```
 

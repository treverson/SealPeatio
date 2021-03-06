# SealPeatio

Most exchange platforms today use software hot wallets to store virtual currencies. Those hot wallets have been frequently abused by hackers or inside employees to steal funds.

SealBlock is a next generation wallet product that leverages hardware enclave technology and policy management to maximize security protection of crypto funds while allowing them to be accessible for legitimate uses.

The SealPeatio project is an upgrade of the popular open source exchange software Peatio that significantly improves crypto fund security. SealPeatio replaces the software-based deposit and withdraw wallets of Peatio with SealBlock hardware wallets that have multi-signature and whitelist policies enforced.

Using SealBlock's technology, even a rogue employee would have a very difficult time stealing funds from the wallets, not to mention an outside attacker.

## Platforms/tools/libraries used

1. [peatio](https://github.com/peatio/peatio "peatio")  
Peatio is an open-source cryptocurrency exchange implementation. We modified it a bit to meet our needs.

2. [geth](https://geth.ethereum.org/ "geth")  
Geth(full name Go Ethereum) is one of the original implementations of the Ethereum protocol.

3. Python  
Python is used to implement Sealblock multisig agent, the interface with SealBlock SGX.  
In addition to the standard Python library, other python packages and modules used are:  
  * zerorpc
  * ecdsa
    * SigningKey, SECP256k1
  * rlp
    * decode, encode
  * bitcoin
  * sha3
  * jsonrpclib
    * SimpleJSONRPCServer

4. Node.js  
Used to implement admin interface.

## Instructions to run the code

Although peatio is modified, the using method is not changed. [README.md](https://github.com/peatio/peatio/blob/master/README.md) file in the project's repository on GitHub helps to understand how to run the whole process.

Our customized go-ethereum is based the oringinal one, we replaced the backend implementation of geth.

To compile it, you will need to install Chocolatey, Git, Go, Mingw.

Compile Instructions:

1. install Chocolatey

2. install needed libs:

 ```
 choco install git
 choco install golang
 choco install mingw
 ```

3. run:

 ```
 set "GOPATH=%USERPROFILE%"
 set "Path=%USERPROFILE%\bin;%Path%"
 setx GOPATH "%GOPATH%"
 setx Path "%Path%"
 cd go-ethereum
 go install -v .\cmd\geth\
 ```

4.find *get.exe* in folder *go/bin*


# Chapter One: Introducing Bitcoin
# 第一章 : 介紹比特幣

These tutorial will lead you through basic Bitcoin usage and programming, highlighting a variety of techniques from the command line to scripting. However, before you should get started, you should have a basic understanding of what Bitcoin is, and how it works. This chapter provides that overview. Many more definitions will appear within the document itself; this is only intended to lay the foundation.

這些教程將引導您了解基本的比特幣使用和編程，強調從命令行到腳本的各種技術。然而，在你開始之前，你應該對比特幣是什麼以及它是如何工作有一個基本的了解。本章提供了這個概述。文件本身會出現更多的定義。這只是打算打下基礎。


## Objectives for this Chapter
## 本章目標



After working through this chapter, a developer will be able to:

   * Assess the Parts of the Bitcoin System
   * Decide Whether Blockchain is Right for Them
   
   
完成本章後，開發人員將能夠：
    * 評估比特幣系統的各個部分
    * 決定區塊鍊是否適合他們
    

Supporting objectives include the ability to:

   * Understand What Bitcoin Is
   * Understand What Blockchain Transactions Are
   * Understand What Blockchain Is
   
為支持達成目標包括以下能力：
   * 了解比特幣是什麼
   * 了解什麼是區塊鏈交易
   * 了解區塊鍊是什麼

   
## What Is Bitcoin?
## 什麼是比特幣?

Bitcoin is a programmatic system that allows for the transfer of the bitcoin currency. It is enabled by a peer-to-peer system of nodes, which include full nodes, wallets, and miners. Working together, they ensure that bitcoin transactions are fast and non-repudiable.


比特幣是一個允許轉換比特幣的程序系統。它是由點對點的節點系統實現的，節點包括完整的節點，錢包和礦工。一起工作，他們確保比特幣交易是快速和不可抵賴的。

### How Are Coins Transferred?
### 比特幣如何交易 ?

Bitcoin currency isn't physical coins. Instead it's an endless series of ownership reassignments. When one person sends coins to another, that transfer is stored as a transaction. It's the transaction that actually records the ownership of the money, not any token local to the owner's wallet or their machine.


比特幣貨幣不是物理硬幣。相反，這是一個無盡的所有權重新分配系列。當一個人將硬幣發送給另一個人時，該轉賬被存儲為交易。這是交易實際上記錄的錢的所有權，而不是所有者的錢包或他們的機器本地的任何令牌。



### Who Can You Send Transactions To?
### 你可以發送交易給誰 ?


The vast majority of bitcoin transactions are sent to individual people (or at least to individual Bitcoin addresses). However, more complex methodologies can be used to send bitcoins to groups of people or to scripts. These various methodologies have names like P2PKH, multisig, and P2SH.

絕大多數比特幣交易被發送給個人（或者至少個人比特幣地址. 但是, 可以使用更複雜的方法將比特幣發送給團體或腳本.這些不同的方法有 P2PKH , multisig 和P2SH .


### How Are Transactions Stored?
### 交易如何儲存?

Transactions are combined into larger blocks of data, which are stored on the network. A block is built in such a way that it can not be replaced or rewritten once several blocks have been built after it. This is what makes bitcoins non-repudiable: the decentralized global ledger where everything is recorded is effectively a permanent and unchangeable database.

交易被組合成更大的數據塊, 存儲在網絡上. 一個程序塊的構建方式是, 一旦在程序塊之後建立了幾個程序塊, 它就不能被替換或重寫. 這就是使得比特幣不可追溯的原因: 記錄一切的分散式全局分類賬實際上是一個永久的，不可改變的數據庫。


However, the process of building these blocks is stochastic: it's somewhat random, and so you can never be assured that a transaction will be placed in a specific block. Moreso, there can be changes in blocks if they're very recent, but only if they're _very_ recent. So, things become non-repudiable (and permanent and unchangeable) after a little bit of time.

然而, 構建這些塊的過程是隨機的: 這是隨機的, 所以你永遠不能放心, 交易將被放置在一個特定的塊. 而且, 如果他們是最近的, 可能會有變化, 但是只有在他們最近的時候. 所以, 在一小段時間之後, 事情變得不可否認(永久且不可改變).


### How Are Transactions Protected?
### 交易是如何被保護的?

The funds contained in a Bitcoin transaction are locked with a cryptographic puzzle. These puzzles are designed so that they can be easily solved by the person who the funds were sent to. This is done using the power of public-key cryptography. 

比特幣交易中包含的資金是被鎖定在密碼拼圖上的. 這些難題的設計使得資金被送到的人很容易解決. 這是使用公鑰密碼學的功能完成的.


### How Are Transactions Written?
### 交易如何寫入?


The heart of each Bitcoin transaction is a FORTH-like scripting language that is used to lock the transaction. To respend the money, the recipient provides specific information to the script that proves he's the intended recipient.

However, these Bitcoin scripts are the lowest level of Bitcoin functionality. Much Bitcoin work is done through the `bitcoind` Bitcoin daemon, which is controlled through RPC commands. Many people send those RPC commands through the `bitcoin-cli` program, which provides an even simpler interface. Non-programmers don't even worry about these minutia, but instead use programmed wallets with simpler interfaces.

每個比特幣交易的核心是一種類似 FORTH 的腳本語言, 用於鎖定交易. 為了補償金錢, 收件人向腳本提供了證明他是預期收件人的特定信息.

但是，這些比特幣腳本是比特幣功能的最低級別. 很多比特幣工作都是通過比特幣守護進程完成的, 這個守護進程是通過RPC命令控制的. 很多人通過 `bitcoin-cli` 程序發送這些RPC命令, 這提供了一個更簡單的界面. 非程序員甚至不用擔心這些細節, 而是使用編程的錢包和更簡單的界面.



### Bitcoin — In Short
### 比特幣 - 簡介

One way to think of Bitcoin is as: _a sequence of atomic transactions: each of which is enabled by the sender with the solution to a previous cryptographic puzzle that was stored as a script; each of which is locked for the recipient with a new cryptographic puzzle that is stored as a script; and each of which is recorded in an immutable global ledger._

一種思考比特幣的方式是： _一系列原子交易: 發件人使用每一個原子交易來解決前一個加密難題的問題. 每一個被鎖定的收件人與一個新的密碼拼圖存儲為一個腳本; 並且每一個都記錄在一個不可變的全局分類帳中._


## What Is Public-Key Cryptography?

Public-key cryptography is a mathematical system for protecting data and proving ownership through an asymmetric pair of linked keys: the public key and the private key.

### What Is a Public Key?

A public key is the key given out to other people. In a typical public-key system, a user generates a public key and a private key, then he gives the public key to all and sundry. Those recipients can encrypt information with the public key, but it can't be decrypted with the same public key because of the asymmetry of the key pair.

### What Is a Private Key?

A private key is linked to a public key in a key pair. In a typical public-key system, a user keeps his private key secure and uses it to decrypt messages sent to him, encrypted with the public key.

### What Is a Signature?

A message (or more commonly, a hash of a message) can be signed with a private key, creating a signature. Anyone with the corresponding public key can then validate the signature, which verifies that the signer owns the private key associated with the public key in question. 

### What Is a Hash Function?

A hash function is an algorithm frequently used with cryptograpy. It's a way to map a large, arbitrary amount of data to a small, fixed amount of data. Hash functions used in cryptography are one-way and collision-resistant, meaning that a hash can very reliably be linked to the original data, but the original data can not be regenerated from the hash. Hashes thus allow the transmission of small amounts of data to represent large amounts of data, which can be important for efficiency and storage requirements. 

### Public-Key Cryptography — In Short

One way to think of public-key cryptography is: _a way for anyone to protect data such that only an authorized person can access it, and for that authorized person to prove that he will have that access._

## What Is Blockchain?

Blockchain is the generalization of the methodology used by Bitcoin to create a distributed global ledger. Bitcoin is a blockchain as are any number of alt-coins, each of which lives in its networks and writes to its own chain. Sidechains like Liquid are blockchains too. Blockchains don't even need to have anything to do with finances. For example, there have been many discussions of using blockchains to protect self-sovereign identities.

### Why Is It Called a Chain?

Each block in the blockchain stores a hash of the block before it. This links the current block all the way back the original "genesis block" through an unbroken chain. It's a way to create absolute order among possibly conflicting data. This also provides the security of blockchain, because each block stacked atop an old one makes it harder to recreate the old block due to the proof-of-work algorithms used in block creation. Once several blocks have been built atop a block in the chain, it's essentially irreversible. 

### What is a Fork?

Occasionally two blocks are created around the same time. This temporarily creates a one-block fork, where either current block could be the "real" one. Every once in a while, a fork might expand to become two blocks, three blocks, or even four blocks long, but pretty quickly one side of the fork is determined to be the real one, and the other is "orphaned". This is part of the stochastic process of block creation, and demonstrates why several blocks must be built atop a block before it can be considered truly trustworthy and non-repudiable.

### Blockchain — In Short

One way to think of blockchain is: _a linked series of blocks of unchangeable data, going back in time_. Another way is: _a linked series of blocks that absolutely order data that could be conflicting_.

## Is Blockchain Right for Me?

If you want to transact bitcoins, then obviously Bitcoin is right for you. However, more widely, Blockchain has become a popular buzz-word even though it's not a magic bullet for all technical problems. With that said, there are many specific situations where blockchain is a superior technology.

Blockchains probably _will_ be helpful if:

  * Users don't trust each other.
    * Or: Users exist across various borders.
  * Users don't trust central authorities.
    * And: Users want to control their own destinies.
  * Users want transparent technology.
  * Users want to share something.
    * And: Users want what's shared to be permanently recorded.
  * Users want fast transaction finality.
    * But: Users don't need instant transaction finality.
    
Blockchains probably _will not_ be helpful if:

  * Users are trusted:
    * e.g.: transactions occur within a business or organization.
    * e.g.: transactions are overseen by a central authority.
  * Secrecy is required:
    * e.g.: Information should be secret.
    * e.g.: Transactions should be secret.
    * e.g.: Transactors should be secret.
  * Users need instant transaction finality, in less than an hour.
  
Do note that there may still be solutions for some of these situations within the Bitcoin ecosystem. For example, payment channels are rapidly addressing questions of liquidity and payment finality. 

## Summary: Introducing Bitcoin

Bitcoin is a peer-to-peer system that allows for the transfer of funds through transactions that are locked with puzzles. These puzzles are dependent upon public-key cryptography. When you generalize the ideas behind Bitcoin, you get blockchains, a technology that's currently growing and innovating.

## What's Next?

Advance through "Preparing for Bitcoin" with [Chapter Two: Setting Up a Bitcoin-Core VPS](02_0_Setting_Up_a_Bitcoin-Core_VPS.md).

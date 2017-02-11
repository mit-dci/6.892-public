# 6.892 Spring 2017
# Shared Public Ledgers: Cryptocurrencies, Blockchains, and Other Marvels

### NOTE:  This document is a draft and is subject to change.

## Information

Instructors:  Neha Narula ([narula@media.mit.edu](narula@media.mit.edu)) and Silvio Micali ([silvio@csail.mit.edu](silvio@csail.mit.edu))

Time:  Fridays 1-4 PM 

Place:  36-155 

Contact: [6.892-sp17-staff@mit.edu](6.892-sp17-staff@mit.edu)

Description: This course is about the principles and core techniques
of shared public ledgers, with an emphasis on Bitcoin and distributed
consensus.  Topics include Bitcoin, Byzantine agreement, authenticated
data structures, Lightning networks, proof of stake, and new
techniques to implement a shared public ledger.

[course announcement](6892_course_announcement.pdf)

## Schedule

NOTE:  The schedule is in flux and subject to change.

| # | Date | Lecturer | Topic | Readings |
|---|------|----------|-------|----------|
| 1 | 2/10 | Neha and Silvio | Introduction. Signatures, hashing, hash chains, e-cash, and motivation | [Untraceable Electronic Cash](http://www.wisdom.weizmann.ac.il/~/naor/PAPERS/untrace.pdf) |
| 2 | 2/17 | Neha | Bitcoin: how it works | [whitepaper](https://bitcoin.org/bitcoin.pdf), [SoK sections 1 and 2](http://www.jbonneau.com/doc/BMCNKF15-IEEESP-bitcoin.pdf), [how it works](http://www.michaelnielsen.org/ddi/how-the-bitcoin-protocol-actually-works/) |
| 3 | 2/24 | Neha | Bitcoin: mining and incentives | [script](https://en.bitcoin.it/wiki/Script), [pooled mining](https://en.bitcoin.it/wiki/Pooled_mining), [hardware](https://en.bitcoin.it/wiki/Mining_hardware_comparison) |
| 4 | 3/3  | Tadge Dryja and Maurice Herlihy | Payment channels and the Lightning Network, concurrency in smart contracts |  |
| 5 | 3/10 | Joe Bonneau | Proof-of-stake and alternatives to proof-of-work |  |
| 6 | 3/17 | abhi shelat and Rafael Pass | Analysis of Bitcoin, Fruitchains | [Analysis of the Blockchain Protocol in Asynchronous Networks](http://eprint.iacr.org/2016/454.pdf), [Fruitchains](https://eprint.iacr.org/2016/916.pdf) |
| 7 | 3/24 | Alessandro Chiesa and Madars Virza | SNARKs and Zerocash | |
| - | 3/31 |  | Spring Break -- no class | |
| 8 | 4/7  | Silvio | Byzantine Agreement | [Byzantine General's Problem](http://research.microsoft.com/en-us/um/people/lamport/pubs/byz.pdf) |
| 9 | 4/14 | Silvio | Algorand | |
| 10 | 4/21 | Silvio | Algorand | |
| 11 | 4/28 | Silvio | Algorand | |
| 12 | 5/5 | | Special topics |  |
| 13 | 5/12 |  | Special topics |  |  |

## Labs and Problem Sets

* Lab 1: Bitcoin treasure hunt

## Final Projects

A final project is encouraged, but not required, as this is an
experimental course. You may form groups of 1-4 students and prepare a
presentation and a 4 page paper on one of the following:

1.  Design and implement an application or system ([project ideas](projects.md))
2.  Add a new feature to an existing system like Bitcoin, Ethereum, or another cryptocurrency or shared ledger implementation
3.  Propose a formalization in this space for a topic that has not been formalized yet  
4.  Pose and solve an interesting problem

## Readings and Resources

* [Untraceable Electronic Cash](http://www.wisdom.weizmann.ac.il/~/naor/PAPERS/untrace.pdf)
* [Universal Electronic Cash](http://link.springer.com/chapter/10.1007/3-540-46766-1_27)
* [Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf)
* [How the Bitcoin Protocol Actually Works](http://www.michaelnielsen.org/ddi/how-the-bitcoin-protocol-actually-works/)
* [Bitcoin Systemization of Knowledge](http://www.jbonneau.com/doc/BMCNKF15-IEEESP-bitcoin.pdf)
* [Princeton textbook](http://bitcoinbook.cs.princeton.edu/) ([pre-published online verison](https://d28rh4a8wq0iu5.cloudfront.net/bitcointech/readings/princeton_bitcoin_book.pdf))
* [Princeton class](https://piazza.com/princeton/spring2015/btctech/resources)
* [Stanford class](https://crypto.stanford.edu/cs251/syllabus.html)
* [UIUC class](http://soc1024.ece.illinois.edu/teaching/ece598am/fall2016/)
* [Byzantine General's Problem](http://research.microsoft.com/en-us/um/people/lamport/pubs/byz.pdf)
* [Bitcoin Mining Pools: A Cooperative Game Theoretic Analysis](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.695.9873&rep=rep1&type=pdf)
* [The Economics of Bitcoin Mining, or Bitcoin in the Presence of Adversaries](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.364.5595&rep=rep1&type=pdf)
* [Analysis of the Blockchain Protocol in Asynchronous Networks](http://eprint.iacr.org/2016/454.pdf)
* [Fruitchains](https://eprint.iacr.org/2016/916.pdf)
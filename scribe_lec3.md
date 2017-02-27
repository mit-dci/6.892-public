# Incentives in Bitcoin

```
Lecturer: Neha Narula
Scribe: Nicola Greco
```

Topics
- Clients
- Mining
- Forks

## Payment Verification Problem
- Alice generates a transactions and sends it to Bob
- Bob wants to make sure that he received the payment.
- Bob must check:
  - Requirement 1: His transaction is in a block
  - Requirement 2: This block is included in the main blockchain

**Payment verification - Trial 1: Full blockchain**
- Bob must download 100GB of blockchain to verify

**Payment verification - Trial 2: Trusted party**
- Bob asks to another node Charlie if the transaction was included or not
- (However, Bob must trust Charlie)

**Digression on Merkle Trees**
- Case1: We could serialize transactions t1,t2,t3.. and h(t1, t2, t3, t4)
- Case2: Merkle trees are trees where every leaf and intermediate branch is recursively hashed until reaching the root
- Why Merkle Tree over serialization hash?
  - Checking for membership (check if a transaction is inside a block) takes O(|txs|), instead, using the merkle tree, it needs O(log|txs|)
  - In practice, in order for Bob to check his transaction, it needs only log(|txs|) to prove his transaction is in a block

**Payment verification - Trial 3: Simple Payment Verification**
- Bob asks Charlie if a transaction is included or not
- Charlie gives:
  - The branch in the Merkle tree - this proves that a block includes his transaction
  - Enough proof of work after this block - this proves that enough miners have included this block in their chain
- Q: Does the Merkle tree only commits to the transactions? Yes

**How to verify if a block is included in the blockchain?**
- In order for Alice to trick Bob, Alice must mine a valid block (it is very expensive about 12k USD)
- One block is not enough, you better be waiting until the block is burried inside the chain (6 reccomended blocks)
  - Q: Why would this be unlikely to be rewritten?
    - Alice would loose money for not receiving money
    - Alice would have to spend so much money
    - Alice won't be enough mining power to keep on going
    - Bob can detect that Alice is really slow (if they are in real time)
  - Q: Can someone create a longer chain?
    - If someone put enough money to do so, yes!

When is that you don't have the network?
- Selfish miner
- Someone cut you off from the rest of the network

## Different mining strategies

- CPU mining: 20Mh/s
  ```
mr = make_merkle_tree(txs)
while (guess a nonce) {
  if (sha256(sha256(make_block_header(mr, nonce))))
}
  ```
- GPU mining: 200Mh/s
- FPGS mining: 1Bh/s (never really took off, too expensive cost/hash)
- ASICS (Application Specific Integration Circuits)
  - Specialized hardware to run SHA256 operations
  - AntMiner 59 $2.3K 13.5 Trillion hashes/sec
  - Earnings about 3.36 BTC/year
  - It takes 4 years until you find a block
  - Q: Can someone come up with better ASICS? Yes, they are getting better
- Mining pools!

**Mining pools**
- Actors:
  - Miners get together
    - why? Getting in a pool reduce the amount of variance
  - Pool managers manages the key that gets the rewards
    - they get a fee
    - Q: How many pools are there now? There are about 10 pools
    - Q: How much share of the hash power they have?
      - AntPool 16.8%, F2Pool 13.5%, BitFury 11.8%, BW.COM 7.8%, BTCC 6.7%
    - Q: Isnt this already 51% ? Yes
- Strategies:
  - Pay-per-share: one gets paid on the amount of great hashes they find
    - Only hashes with 70s are valid for bitcoin, but nodes are paid proportionally to the amount of 0s they find
    - Block witholding attack? A participant in a pool has no incentive to not propagate a winning hash (unless she wants the pool manager & her not to make money!)

**Miners Strategies**
- Choices miners make:
  - What transactions to put (default: > min txn fee)
  - Which blocks to mine on (default: longest chain)
  - If they see two blocks, they need to choose one (default: pick the first one you see)
  - When to announce new blocks that they find (default: immediately)
- Types of attacks:
  - Forking attack: worth it? detectable? actually not seen it in practice
  - Gold Finger attack: if someone wants to destroy Bitcoin
  - Bribe attack: pay miners not to include a transaction
  - Selfish mining/Block witholding
  - Q: Can miners get together to take over Bitcoin?
    - Yes, they could but they would loose the economic value of the currency!
    - However, they could throw a Gold Finger attack: "I just want to destroy Bitcoin"

## Forks
- When do we need to change the rules?
  - Fixing bugs
  - Add new features
  - Change parameters of the software
- Two types of changes
  - *Restrict* the set of rules: valid -> invalid
  - *Expand the set of rules*: invalid -> valid
  - Q: How do you get people to use your upgrade? Online communication :D
- Soft forks: old software still consider new transactions good, upgraded software would see it as invalid
- Hard forks: you take something that was previously invalid, and you make it valid
  - even if more than 50% of the hash power agrees, we will have two chains => two versions of history
  - really dangerous! SPV proofs can generate fake proofs!
  

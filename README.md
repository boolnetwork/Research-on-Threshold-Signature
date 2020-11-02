# Cryptographic Techniques in Boolnetwork
This repository contains a growing set of research documents about the underlying cryptography techniques that will be used in boolnetwork.
Content may include BLS signature, threshold signature, zero-knowledge proof, homomorphic encryption, multi-party computation, etc. More content will be added as with the development of boolnetwork in the future.

## Threshold Signature
At present, we start with introducing the threshold signature(TSS) techniques and its comparisons with other similar techniques. TSS is an advanced cryptographic technique that is used to protect key security by allowing multiple players to share the power to generate a signature on a message. More specifically, a private key is shared among n players, and a threshold parameter t is defined such that any subgroup of t players can jointly generate a signature, whereas any adversary can neither forge a signature nor learn any information about the private key even the adversary corrupts up to t-1 players. In TSS, the expensive distributed key generation and signation generation are all performed off-chain, and only one signature verification is performed onchain. Hence, TSS is flexible, efficient, and compatible with most of the blockchains and offers higher degrees of privacy than other similar techniques, such as multi-signature. A more detailed introduction about TSS can be seen in this [document](https://github.com/boolnetwork/Cryptographic-techniques-in-boolnetwork/blob/master/document.pdf)

### (EC)DSA Signature
A threshold ECDSA signature differs from the ordinary ECDSA signature in two phases, which are the distributed key generationa and distributed sign phases, but the verification phase is identical. ECDSA is the elliptic curve derivative of the standard Digital Signature Algorithm (DSA), and is widely used in many cryptocurrencies. The algorithm of an ordinary ECDSA scheme is presented in [this](https://github.com/boolnetwork/Cryptographic-techniques-in-boolnetwork/blob/master/ECDSA.pdf) document.

### Paillier Encryption
Many threshold ECDSA signature schemes rely on the techniques of Paillier encryption as the building block. Paillier encryption is a public encryption scheme that is additively homomorphic modulo a large integer. The additively homomorphic feature means that the addition of two ciphetext which are encryption two different messages is actually the encryption of the addition of the two messages (i.e.,c1=E(m1),c2=E(m2),c1+c2=E(m1+m2 mod n)). More details about Paillier encryption scheme is presented in [this](https://github.com/boolnetwork/Cryptographic-techniques-in-boolnetwork/blob/master/Paillier-encryption.pdf) document.

## Zero Knowledge Proof
In cryptography, a zero-knowledge proof or zero-knowledge protocol is a method by which one party (the prover) can prove to another party (the verifier) that they know a statement, without reveal any information apart from the statement itself. The essence of zero-knowledge proofs is that it is trivial to prove that one possesses knowledge of certain statement by simply revealing it; the challenge is to prove such possession without revealing the knowledge or any additional knowledge which can be deduced from the provided information. 

The key benefit of zero knowledge is that it provides strong privacy guarantee. This is especially important in blockchain space, as all data are public on chain, meaning that any adversary can collect the onchain data to extract some information that undermines user privacy. By using the techniques of zero-knowledge proofs, one can prove the authenticity of a transaction on the blockchain without leaking any useful information. Hence, the adversary is not able to extract any useful information about the transaction. There are already projects using zero-knowledge proof techniques to create cryptocurrency with strong privacy protection. The most famous one is Zcash, which uses zk-snarks to realize efficient transaction authentication with strong privacy preserving. Besides this, zero-knowledge proof is a cryptographic primitive that can be used to build advanced cryptographic protocols with privacy preserving. For example, the clasic Schnorr proof is a zero-knowledge proof that is used in many protocols to prove the ownership of a discrete logarithm that satisfy a certain statement. 

### ZK-SNARKs
A more detailed introduction about zero-knowledge proof and zk-snarks is give in [this](https://github.com/boolnetwork/Cryptographic-techniques-in-boolnetwork/blob/master/Introduction%20to%20zkSNARK.pdf) document.

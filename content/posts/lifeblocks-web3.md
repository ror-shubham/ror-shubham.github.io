---
date: '2017-10-01T00:00:00+05:30'
title: 'LifeBlocks: Trustless Certificate Verification on Ethereum'
summary: 'Developed a blockchain system using Solidity and React enabling institutions to issue verifiable digital certificates.'
tags: ['Web3', 'Ethereum', 'Solidity', 'React', 'Full Stack', 'Smart Contracts']
categories: ['Projects']
ShowToc: false
weight: 8
---

During my time at IIT Roorkee, long before Web3 became a saturated buzzword, my team built **LifeBlocks** — a trustless certificate verification system leveraging the Ethereum blockchain.

**🔗 Links:**
- [Devpost Submission](https://devpost.com/software/lifeblocks-g3siwl)
- [GitHub Repository](https://github.com/ror-shubham/lifeblocks-public)

## The Problem

Verifying academic degrees, bootcamp certificates, and employment history is a slow, manual process. Employers must contact issuing institutions, who then manually verify their records. Digital PDFs are easily forged. 

We wanted to create a system where a certificate is issued once and can be mathematically verified instantly by anyone, without trusting a central database.

## Architecture

I worked as the full-stack developer on the project, spanning both the decentralized backend and the user-facing web app.

### The Smart Contract (Solidity)
We wrote Ethereum smart contracts in **Solidity** to serve as the immutable ledger. 
- Institutions register on the platform and are granted issuing rights.
- When a certificate is issued, a cryptographic hash of the certificate data is stored on the Ethereum blockchain, tied to the issuer's address and the recipient.
- The actual private data remains off-chain, while the verifiable proof lives on-chain.

### The Frontend (React)
A blockchain backend is useless without an accessible interface. I built the frontend using **ReactJS** and **Web3.js**:
- Integrated MetaMask for user authentication and transaction signing.
- Built dashboards for institutions to issue certificates in bulk.
- Created a simple verification public portal: an employer drops a certificate file or inputs an ID, the app hashes the data, checks it against the smart contract, and instantly returns a "Verified" or "Invalid" status.

## Tech Stack

`Ethereum` · `Solidity` · `ReactJS` · `JavaScript` · `Web3.js`

---

*This project was my deep-dive into distributed systems and the concept of trustless architecture.*

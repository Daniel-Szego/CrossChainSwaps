# CrossChainSwaps

Experimental implementation of several different cross chain swaps

workshop slides can be found at: 
https://docs.google.com/presentation/d/1v2pJ5A90hEDm7kPlvFesA6z0LAYHrx0cUSVHkJMBBhM/edit?usp=sharing

HTLC Hash TimeLock Contracts:
- Alice HTLC on Chain 1
- Bob HTLC on Chain 2
- Simplified HTLC in ethereum
- ERC 1630 Ethereum proposal for standard HTLC:  https://github.com/ethereum/EIPs/issues/1631

Simple atomic swap protocol with HTLC
1. Alice creates hash and digest and agrees in expiration time with Bob
2. Alice deploys AliceHTLC_Chain1 contract on chain 1 and transfers money to the contract (meaning that the money has been conditionally transferred to Bob)
3. Bob deploys BobHTLC_Chain2 on chain 2 and transfers money to the contract (meaning that the money has been conditionally transferred to Alice)
4. Alice claims her money from Bob on chain 2 unveiling the secret by calling the BobHTLC_Chain2 contract. 
5. Bob see the secret key, so he can claim his money from Alice on chain 1 by calling the claim function of the AliceHTLC_Chain1 contract with the secret. 
 



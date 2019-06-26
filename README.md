What is this?

- This contract is a fork of origin dice2-win contract that provably fair bets on ethereum network.
We added some functions to handle the TrueDice Token distribution when playing TrueDice.Win games.

How does it work?

- truedice.win picks a secret random number and provides you with its hash.
- You send your bet in Ethereum transaction to our smart contract along with the hash from previous step.
- At this point truedice.win has already commited to a number, prior to you chosing an outcome.
- Once your transaction is confirmed by the network, the contract stores the hash and bet details.
- Our croupier bot "reveals" the number by sending a bet settling transaction.
- The contract accepts the transaction if and only if the hash of provided number is the same as the stored one.
- The contract mixes the number and block hash of the bet transaction to get a random number.
- The contract decides whether you won or lost and sends you the winning amount of Ether.

Can truedice.win tamper with the results? 

- Nope, as the contract keeps track of secret number's hash, meaning the operator cannot change the number after the bet has been accepted. Mixing the block hash with the numbers makes the result totally random yet disallows miners from crafting winning bets. On the other hand, truedice.win themselves cannot control bet outcomes either because of block hash component. This is a well-known "commitment scheme" which enables truedice.win to provide gambling-grade random number generation allowing for big bets, jackpots and quick settlements while being fully transparent.

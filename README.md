# Plutus-Pioneer-Program


* UTxO model :- They are transaction outputs that are outputs from previous transactions that happened on the blockchain that have not yet been spent.

* The EUTxO Model
So to recapitulate in extending the normal UTxO model, we replace public key addresses from the normal UTxO model with scripts, Plutus scripts, and instead of legitimizing the consumption of new UTxO by digital signatures, as in the simple UTxO model, arbitrary data called redeemer is used on the input side. And we also add arbitrary custom data on the output side. And the script as context when it runs, sees the spending transaction, the transaction one, in this example. So given the redeemer and the datum and the transaction with its other inputs and outputs, the script can run arbitrary logic to decide whether it's okay for this transaction to consume the output or not. And that is how Plutus works.

* The Auction Contract in the EUTxO Model
What really happens is that the old auction UTxO is spent and a new one is created, but it has the feel of updating the state of the auction UTxO
This time we again use the Bid redeemer. This time the script has to check that the deadline has been reached, that the bid is higher than the previous bid, it has to check that the auction UTxO is correctly created and it has to check that the previous highest bidder gets their bid back.

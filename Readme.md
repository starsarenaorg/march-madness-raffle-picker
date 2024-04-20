## How did we pick the winners ? 
* A snapshot is taken at 12 PM EST 20.04.2024 which can be found under`data/snapshot.json`.
* The keccak256 hash of the snaphot file will be attested on chain to prove that the contents  hasn't been modified.
* A Random number which will be used as the randomness seed will be taken from Chainlink VRF, the contract can be found under : https://snowtrace.io/address/0x847B953fE0D759011dF7Bc89d5700d757eC73Efa
* This seed will be hashed with keccack256 95 times to provide the random numbers for each winner. We start from the lowest prize tier to pick the winners and each participant can win more than once. However, each win decreases the amount of tickets by 1, so a user with only 1 ticket can win only once, and a user with with N tickets can hypotetically win N times, alltough there is a very low probability for that to happen.  
* The whole process it 100 percent transparent and can be verified by any third party.

## How can verify the process ?
Run the verify script with `node verify.mjs`, which will:
1. Hash the `snapshot.json` under `data`.
2. Fetch the random number seed associated with this hash.
4. Re-run the whole picking process and compare the results with the published results. 
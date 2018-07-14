# DelegateTestToken-Deployer

This test allows access to an ERC20 deployed on address 0x1a073cbe88718403c3e521494e1d0d263252ecb3, with a signed transfer function which allows function call delegation to a third party to pay for gas.

Test defaults to 1% transfer fees, which will be calculated on top of the total token transfer sum.

![alt text](https://pictr.com/images/2018/07/14/tauU1.md.png)

Requires:
1. **Private key of token holder (Token Deployed At)**
   >The token holder itself. The private key is meant to sign the transaction, to be ran on the client end without ever needing the private key to be transmitted out of the client device. Once the transaction is signed by the holder, it is being delegated to the deploying address for deployment.
   
   >Currently the token holder is 0x794398c00aE32e62B4f3b90Fe050D32D55A59878, and the private key is embedded in the test executable (12ed9149b9202ccf46e7bdd856788cfc4e4c5b598ee445653f6bbccc7899ce84). This address holds tokens from 0x1a073cbe88718403c3e521494e1d0d263252ecb3, but has no ethers to pay for gas.
   
   > Example tx: https://rinkeby.etherscan.io/tx/0x5e5051062f0df5b1cb6ca95a1d09d6f86543bb5cab72dd4d1b1773e5dffc51bf


2. **To address (where the tokens should be sent to).**
   >The token receiving address.


3. **Amount (number of tokens to send).**
   >Number of tokens to send. Numeric.


4. **Deployer Private Key**
   >Private keys to the deploying address. This address will execute the signed transfer, and will require to hold some ethers to pay for gas. Just use any account with some Rinkeby ethers.
   
   >In return for the incurred gas cost, 1% of the transferred token sum is calculated and sent to the deploying address, which acts as a deployment fee. This is specified within the smart contract.




Full credits to @juanfranblanco for his lovely Nethereum library (https://github.com/Nethereum/Nethereum)

# Run a Gencex Validator
## Setting up a node
1. Git clone https://github.com/infura1/GencexNetwork.git

2. Copy source form node-example to root folder
```
cp -r GencexNetwork/node-example/Gencex  /root/
```
3. Create an Account

```
cd /root/Gencex
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake Gencex coin, all you should do is sending your Gencex coin to the Gencex Consensus contract address over the Gencex network from the validator address.
    The Gencex Consensus contract address: 0x2E3a40c77B170416688eb5A42e024C02840BBb2d
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to Gencex and send the Gencex coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /Gencex/nodes/validator/keys/Gencex/UTC--xxxx
    /Gencex/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.

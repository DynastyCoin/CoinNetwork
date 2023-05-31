# Run a DNY Validator
## Setting up a node
1. Git clone https://github.com/DynastyCoin/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/DNY  /root/
```
3. Create an Account

```
cd /root/DNY
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

    To stake DNY coin, all you should do is sending your DNY coin to the DNY Consensus contract address over the DNY network from the validator address.
    The DNY Consensus contract address: 0x8466DAe7A0be6d24CedE83219094c0c52EbB9DBB
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to DNY and send the DNY coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /DNY/nodes/validator/keys/DNY/UTC--xxxx
    /DNY/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.

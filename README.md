# nolus-testnet

Nolus core is a blockchain built using Cosmos SDK and Tendermint

<p align="center">
  <img src="https://raw.githubusercontent.com/Nolus-Protocol/nolus-core/6cafc7e8120ea81ab37ff08cbbb2bd10a2cde2f4/docs/nolus-core-logo.svg" alt="alt text" width="150" height="150">
</p>

## Snapshot height `1 206 255` (01.03.2023) 11.3gb

- pruning: nothing
- indexer: null
- version: v0.1.43

# Instructions

### 1. Stop the service

```
sudo systemctl stop nolusd
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/data/priv_validator_state.json.backup
rm -rf $HOME/.nolus/data
```

### 2. Download latest snapshot

```
wget http://65.109.85.155:8000/snapshot-nolus-1206255.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.nolus
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

### 3. Restart the service and check the log

```
sudo systemctl start nolusd && sudo journalctl -u nolusd -f --no-hostname -o cat
```

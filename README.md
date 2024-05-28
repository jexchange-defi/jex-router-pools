![Logo](https://app.jexchange.io/logo256.png)

# JEX router pools

Configuration of liquidity pools used in JEX DEX aggregator.

# How to add a pool

**Note that pools from JEXchangeDefi, xExchange, OneDex, AshSwap and VestaDEX are automatically added to the DEX aggregator.**

**No configuration is required for these pool.**

Create a pull request on https://github.com/javier-nft/jex-router-pools with the following changes.

Add the pool in the corresponding file in [pools]() folder.

A pool is a JSON structure composed of:

- name = pool name
- sc_address = address of the smart contract
- tokens_in = list of input token identifiers
- tokens_out = list of output token identifiers
- type = type of pool among:
  - "ashswap_stablepool"
  - "ashswap_v2"
  - "exrond"
  - "hatom_money_market_mint" = deposit in lending on Hatom
  - "hatom_money_market_redeem" = redeem from lending on Hatom
  - "jexchange" = JEXchange orderbook
  - "jexchange_lp" = JEXchange liquidity pools
  - "jexchange_stablepool" = JEXchange stable pools
  - "onedex"
  - "vestadex"
  - "xexchange"

Examples:

```json
{
  "name": "AshSwap: USDC/USDT",
  "sc_address": "erd1qqqqqqqqqqqqqpgqs8p2v9wr8j48vqrmudcj94wu47kqra3r4fvshfyd9c",
  "tokens_in": ["USDC-c76f1f", "USDT-f8c08c"],
  "tokens_out": ["USDC-c76f1f", "USDT-f8c08c"],
  "type": "ashswap_stablepool"
}
```

```json
{
  "name": "xExchange: CYBER/EGLD",
  "sc_address": "erd1qqqqqqqqqqqqqpgq5g7xxmpuf6nmux3r3spjxv0wleyypz8q2jpsyc3nh8",
  "tokens_in": ["CYBER-489c1c", "WEGLD-bd4d79"],
  "tokens_out": ["CYBER-489c1c", "WEGLD-bd4d79"],
  "type": "vestadex"
}
```

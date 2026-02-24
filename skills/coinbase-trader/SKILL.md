# Coinbase Trader (Safe Wrapper)

You can ONLY interact with Coinbase via this wrapper command:

`node skills/coinbase-trader/bin/coinbase-wrapper.mjs <command> [args]`

## Allowed commands (read-only)
- `accounts`
- `best_bid_ask BTC-EUR`
- `best_bid_ask ETH-EUR`

## Trading command (requires approval)
- `place_order <PRODUCT> <buy|sell> <EUR>`

## Safety commands
- `halt`
- `resume`

## Hard rules
- Never attempt withdrawals or transfers.
- Never run any other commands than the wrapper.
- Default to read-only. Only trade if explicitly instructed and TRADING_ENABLED is true.
- Before any trade: present a short plan with risk + size + reason.
- After any trade: report result and update day summary.
- If any error or uncertainty happens: run `halt` and notify the user.

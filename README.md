# Savage Protocol — Fairness Verifier

Independent, open-source tool to verify any round of Savage Protocol.

- Runs entirely in your browser
- Fetches data directly from Solana RPC — no Savage servers
- SHA256 entropy derivation + winner selection — fully transparent

## How to use

1. Visit [https://savage0099.github.io/savage-verifier](https://savage0099.github.io/savage-verifier)
2. Enter a round number
3. Click VERIFY

Or open `index.html` locally in any browser.

## How it works

1. **Commit** — Switchboard VRF commits a hidden random value on-chain before the round starts
2. **Reveal** — After the round ends, the VRF reveals the value
3. **Draw** — SHA256 entropy is derived, winning ticket = `u128_le(entropy[8..24]) % total_tickets`

All inputs are read directly from the Solana blockchain. No one — including Savage — can manipulate the result.

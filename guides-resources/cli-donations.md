<img src="https://sparkibc.zone/images/Logo.svg" alt="spark ibc logo" width=96 height=96 >

# CLI Donations

## Prerequisites

---

- Junod installed
    
    Please follow the guide here: [https://docs.junonetwork.io/validators/getting-setup](https://docs.junonetwork.io/validators/getting-setup)
    
- Import your private key into junod to execute signed transactions
    
    ```bash
    junod keys add <name> --recover
    ```
    
    <br>

## General & Campaign Fund Donations

---

1. Set Chain ID and transaction config
    ```bash
    CHAIN_ID="juno-1"
    TXFLAG="--chain-id ${CHAIN_ID} --gas-prices 0.025ujuno --gas auto --gas-adjustment 1.3 --broadcast-mode block"
    ```
2. Choose which to fund:

    **Campaign** (Use campaign name as seen in UI)
    ```bash
    EXECUTE_FUND='{"fund":{"fund_campaign":{"campaign_name": "CAMPAIGN_NAME_HERE","donor_address_type":"Private"}}}'
    ```
    **General**
    ```bash
    EXECUTE_FUND='{"fund":{"fund_general":{"donor_address_type":"Private"}}}'
    ```

3. Replace `AMOUNT` below with the amount you'd like to contribute multiplied by 1000000. The transaction is sent in uUSDC denomination, so `1000000uUSDC == 1USDC`.

    ```bash
    AMOUNT="1000000"
    TXAMOUNT="${AMOUNT}ibc/EAC38D55372F38F1AFD68DF7FE9EF762DCF69F26520643CF3F9D292A738D8034"
    ```

4. Run the transaction command (I recommend piping to jq if installed)
    Make sure to replace `<junod key name>` with the junod key name you'd like to contribute with

    ```bash
    junod tx wasm execute juno1a6rna5tcl6p97rze6hnd5ug35kadqhudvr5f4mtr6s0yd5mruhss8gzrdy "$EXECUTE_FUND" \
    --from <junod key name> \
    --node "https://rpc-juno.itastakers.com:443/" $TXFLAG \
    --amount "$TXAMOUNT"
    ```

5. Thanks so much for your contribution! **Now go check it out on the [leaderboard](https://sparkibc.zone/leaderboard) 🏅** and set a username/alias!

    <br>

    ### Need help?
    Give us a shout over on the [Spark IBC discord](https://discord.gg/RkxcNDtvkJ).
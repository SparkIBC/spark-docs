# Assumptions

- Campaign details have been fleshed out and are ready to implement into the website and smart contract
- Admin wallet access
- Some juno in the admin wallet
- `Junod` installed

# 🧾 Contract

1. Head to the multisig [here](https://daodao.zone/dao/juno1zc8j08w84ex0qhuq0q5tkegs9zzlgcpjzhm0ht7hxv8a92dvmzwq8afz9l/proposals)
2. Create a new proposal and enter in the campaign details as seen below

```JSON
{
    "wasm": {
        "execute": {
        // Ensure contract address below is the correct funding contract
        "contract_addr": "juno1a6rna5tcl6p97rze6hnd5ug35kadqhudvr5f4mtr6s0yd5mruhss8gzrdy",
        "msg": {
            "add_campaign" : {
                // Campaign Name (example shown below)
                "campaign_name": "Cosmos $JOE",
                // Where the funds will be routed on donation (example shown below)
                "campaign_address": "juno1wmtep3pn8tjughhzpjag78fd9gj3n4z7ucfdy2",
            }
        },
        "funds": []
        }
    }
}
```

# 🌐 Frontend

1. Add newly created campaign

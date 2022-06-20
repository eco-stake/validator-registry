# Cosmos Validator Registry

This repository has been ripped from REStake and roughly re-organised into a cohesive structure.

Rather than making a REStake specific repository, this can be used to hold any validator attributes that can't be stored on-chain.

The intention is for this to move to the [Cosmos](https://github.com/cosmos) organisation once it's proven itself. It's dream is to be the validator version of the [Chain Registry](https://github.com/cosmos/chain-registry)

**This is very much a work in progress, and any and all comments are welcome.** Please submit an Issue if you have any ideas or suggestions. 

## Structure

Each validator operation has their own directory. Within that directory are currently two files:

### profile.json

Overall name for your operation and [keybase.io](https://keybase.io/) PGP fingerprint identity. This isn't used in REStake currently but it helps annotate your entry.

```JSON
{
  "$schema": "../profile.schema.json",
  "name": "ECO Stake 🌱",
  "identity": "5992A6D423A406D6"
}
```

### chains.json

Chain information and REStake attributes for your validators.

```JSON
{
  "$schema": "../chains.schema.json",
  "name": "ECO Stake 🌱",
  "chains": [
    {
      "name": "akash",
      "address": "akashvaloper1xgnd8aach3vawsl38snpydkng2nv8a4kqgs8hf",
      "restake": {
        "address": "akash1yxsmtnxdt6gxnaqrg0j0nudg7et2gqczud2r2v",
        "run_time": [
          "09:00",
          "21:00"
        ],
        "minimum_reward": 1000
      }
    },
    {
      "name": "cerberus",
      "address": "cerberusvaloper1tat2cy3f9djtq9z7ly262sqngcarvaktr0w78f",
      "restake": {
        "address": "cerberus1yxsmtnxdt6gxnaqrg0j0nudg7et2gqczd38dxa",
        "run_time": "every 15 minutes",
        "minimum_reward": 100000000
      }
    },
    ...
}
```

## JSON API 

The Validator Registry is available via a JSON API at [validators.cosmos.directory](https://validators.cosmos.directory). The structure of this API might change in the near future until we reach a major version number.

Example endpoints:

- [validators.cosmos.directory](https://validators.cosmos.directory)
- [validators.cosmos.directory/ecostake](https://validators.cosmos.directory/ecostake)
- [validators.cosmos.directory/ecostake/profile](https://validators.cosmos.directory/ecostake/profile)
- [validators.cosmos.directory/ecostake/chains](https://validators.cosmos.directory/ecostake/chains)
- [validators.cosmos.directory/chains/osmosis](https://validators.cosmos.directory/chains/osmosis)

## Contributing

Make any changes you want to your operation. Submit a PR and it will be merged as soon as possible - REStake automatically updates from this repository so this will speed up the process a lot. 

If you want to contribute to improving the registry as a whole, check the issues or get in touch on Discord/Twitter/email/wherever.

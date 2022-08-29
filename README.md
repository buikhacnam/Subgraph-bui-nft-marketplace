# bui-nft-marketplace Subgraph

Documentation: https://thegraph.com/en/

Update the `schema.graphql` file based on the contract events

Every time you update the `schema.graphql` file, you need to run the below to update the generated files.

```bash
graph codegen
```

Update all the logics of event handlers in the `src/nftmarketplace.ts` file

Update a startBlock in `subgraph.yaml` file. Note the block number will be the block in the network minus 1:

```yaml
 dataSources:
  - kind: ethereum
    name: nftmarketplace
    network: rinkeby
    source:
      address: "0x99701f665b1CcE2F4b88ba7275606BFa71b28008"
      abi: nftmarketplace
      startBlock: 11274595

```
## AUTH & DEPLOY
Authenticate within the CLI, build and deploy your subgraph to the Studio.

AUTHENTICATE IN CLI
```bash
graph auth --studio YOUR_KEY
```


BUILD SUBGRAPH

```bash
graph codegen && graph build
```

DEPLOY SUBGRAPH
```bash
graph deploy --studio bui-nft-marketplace
```


RESULT
```

Build completed: QmRyAQWuagnEJmpiH8yzTPQ1XykLzvmWAgJan1v24Cu69n

Deployed to https://thegraph.com/studio/subgraph/bui-nft-marketplace

Subgraph endpoints:
Queries (HTTP):     https://api.studio.thegraph.com/query/33567/bui-nft-marketplace/v0.0.1

```
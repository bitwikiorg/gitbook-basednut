# 📒 Glossary

## Based NUT DeFi Glossary

### Core Market Terms

> 1. **Slippage:** The difference between the quoted trade result and the result received when the transaction executes. It can arise from price movement, transaction ordering, fees, transfer taxes, or changes in pool balances. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/8643794102669-Price-Impact-vs-Price-Slippage)

> 2. **Slippage tolerance:** The maximum unfavorable difference a trader permits between the quoted and executed result before the transaction reverts. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/8643879653261-How-to-change-slippage-on-the-Uniswap-Web-app)

> 3. **Minimum output:** The smallest output amount a swap is permitted to return under the user’s slippage settings. [Learn more: Uniswap swaps](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 4. **Price impact:** The price movement directly caused by the size of a trade relative to the pool’s active liquidity. **Based NUT:** NUT trade size is measured relative to available pool liquidity, not merely by the visible fraction of one NUT being traded. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/8671539602317-What-is-Price-Impact)

> 5. **Spot price:** The pool’s current marginal exchange rate before accounting for the complete size of a proposed trade. [Learn more: Uniswap v2 whitepaper](https://docs.uniswap.org/whitepaper.pdf)

> 6. **Execution price:** The average exchange rate received across the entire trade after fees and movement along the pool curve. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/8643794102669-Price-Impact-vs-Price-Slippage)

> 7. **Quote:** An estimate of a transaction’s route, input, output, fees, price impact, and minimum received amount. [Learn more: Uniswap quoting](https://docs.uniswap.org/sdk/v3/guides/swaps/quoting)

> 8. **Base asset:** The asset being priced in a market pair. The meaning depends on the notation used by the interface. **Based NUT:** NUT is also called the base asset in Mint Club curves where users deposit NUT to mint child tokens. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 9. **Quote asset:** The asset used to express the price of another asset. In NUT/WETH, WETH is the quote asset when NUT’s price is stated in WETH. [Learn more: Coinbase](https://www.coinbase.com/learn/crypto-basics/what-is-a-trading-pair)

> 10. **Pair token:** The asset traded or deposited alongside another asset in a two-token pool. **Based NUT:** NUT pair tokens include WETH, AERO, cbBTC, and ecosystem tokens in their respective pools. [Learn more: Uniswap pairs](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 11. **Price discovery:** The process through which market transactions establish an exchange price. **Based NUT:** NUT price discovery occurs across its Uniswap and Aerodrome markets. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 12. **Price divergence:** A difference between prices quoted by separate markets for the same asset. **Based NUT:** NUT prices can be compared across its separate liquidity venues. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/25845512413069-Why-is-a-pool-out-of-sync)

> 13. **Price convergence:** Movement of separate market prices toward one another, commonly through arbitrage. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/25845512413069-Why-is-a-pool-out-of-sync)

> 14. **Depeg:** A departure from an asset’s intended reference price, exchange rate, or redemption relationship. [Learn more: Chainlink](https://chain.link/education-hub/what-is-a-stablecoin)

> 15. **Volatility:** The magnitude and frequency of price changes during a period. [Learn more: Coinbase](https://www.coinbase.com/learn/crypto-basics/what-is-volatility)

> 16. **Market capitalization:** Token price multiplied by circulating supply. `market cap = token price × circulating supply` . **Based NUT:** Because circulating supply can differ from total supply, NUT market capitalization and NUT FDV are separate concepts. [Learn more: CoinMarketCap](https://coinmarketcap.com/academy/glossary/market-capitalization-market-cap-mcap)

> 17. **Fully diluted valuation / FDV:** Token price multiplied by the maximum or fully issued supply. `FDV = token price × maximum supply` . **Based NUT:** With a maximum total supply of one whole NUT, NUT FDV is numerically equal to the market price of one whole NUT. [Learn more: NUT contract](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df)

> 18. **Trading volume:** The total value or quantity traded during a selected period. [Learn more: CoinGecko](https://www.coingecko.com/learn/crypto-trading-volume)

> 19. **Route:** The sequence of pools and tokens used to execute a swap. [Learn more: Uniswap routing](https://docs.uniswap.org/contracts/v3/concepts/advanced-topics/routing)

> 20. **Multi-hop swap:** A swap that passes through one or more intermediate tokens or pools before reaching the requested output token. **Based NUT:** A NUT-linked trade may route through WETH, cbBTC, AERO, VIRTUAL, an LP token, or another ecosystem asset. [Learn more: Uniswap routing](https://docs.uniswap.org/contracts/v3/concepts/advanced-topics/routing)

***

### Liquidity and Liquidity Provision

> 1. **Liquidity:** Assets available for immediate trading, borrowing, redemption, or withdrawal. [Learn more: Uniswap](https://docs.uniswap.org/concepts/protocol/liquidity)

> 2. **Liquidity depth:** The amount that can be traded near the current price without substantially changing that price. It depends on both total capital and its position along the pricing curve. [Learn more: Uniswap concentrated liquidity](https://developers.uniswap.org/docs/get-started/concepts/liquidity-providers/concentrated-liquidity)

> 3. **Active liquidity:** Liquidity positioned at the current market price and therefore available to execute trades. [Learn more: Uniswap](https://docs.uniswap.org/concepts/protocol/concentrated-liquidity)

> 4. **Inactive liquidity:** Deposited liquidity positioned outside the current active price range. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/32514988932877-What-does-out-of-range-liquidity-mean)

> 5. **Full-range liquidity:** Liquidity distributed across the protocol’s complete possible price range. Uniswap v2 positions are full range by design. [Learn more: Uniswap v2](https://docs.uniswap.org/whitepaper.pdf)

> 6. **Concentrated liquidity:** Liquidity assigned to selected price intervals rather than the entire price curve. [Learn more: Uniswap v3](https://developers.uniswap.org/docs/get-started/concepts/liquidity-providers/concentrated-liquidity)

> 7. **One-sided liquidity:** A position containing only or primarily one asset. A concentrated position can become one-sided when the market moves outside its selected range. **Based NUT:** NUT’s genesis liquidity began as a one-sided NUT position. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/32514988932877-What-does-out-of-range-liquidity-mean)

> 8. **Liquidity provision / LPing:** Depositing assets into a market so users can trade against them. The provider receives the position’s fees and assumes the position’s asset exposure. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/20902968738317-What-is-liquidity-providing)

> 9. **Liquidity provider / LP:** A wallet, treasury, vault, or contract that supplies liquidity. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/20902968738317-What-is-liquidity-providing)

> 10. **Liquidity pool:** A smart contract holding assets and applying defined rules for deposits, withdrawals, swaps, and pricing. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 11. **LP token:** A token representing ownership of a liquidity pool. Redeeming it returns the holder’s proportional underlying assets according to the pool’s rules. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 12. **LP-token pool / LP pool:** In this glossary, a pool where one of the deposited assets is itself an LP token. **Based NUT:** Palm Grove structures use SNUT-related LP tokens as assets in another market. [Learn more: Balancer composability](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 13. **Metapool:** A pool connecting an asset to an established pool through that pool’s LP token. Exact metapool mechanics are protocol-specific. **Based NUT:** Palm Grove is described as an LP-token metapool. Learn more: Curve metapools

> 14. **Nested liquidity:** Liquidity composed recursively: tokens enter a pool, the LP token enters another pool, and the resulting position may enter another contract. **Based NUT:** pNUT, Palm Grove, vault shares, and NUT-backed assets can form nested liquidity layers. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 15. **Composable liquidity:** Tokenized liquidity positions that can be transferred or used inside other protocols. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 16. **Liquidity fragmentation:** Distribution of liquidity across separate pools, chains, pairs, fee tiers, or token standards. **Based NUT:** NUT liquidity is distributed across Uniswap, Aerodrome, Balancer-related structures, and bonding-curve markets. [Learn more: Uniswap routing](https://docs.uniswap.org/contracts/v3/concepts/advanced-topics/routing)

> 17. **Canonical pool:** The pool designated as the principal market or price reference for an asset. **Based NUT:** The NUT genesis pool is used as the ecosystem’s primary historical market reference. [Learn more: Uniswap pools](https://docs.uniswap.org/contracts/v3/reference/core/UniswapV3Pool)

> 18. **Genesis pool:** The initial pool used to establish a token’s first onchain market. **Based NUT:** The NUT/WETH Uniswap v3 pool is the NUT genesis pool. [Learn more: Uniswap pool initialization](https://docs.uniswap.org/contracts/v3/reference/core/UniswapV3Pool#initialize)

> 19. **Genesis liquidity:** The initial assets deposited when a market is created. **Based NUT:** NUT genesis liquidity established its original Uniswap v3 position and market price. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v3/reference/core/UniswapV3Pool#initialize)

> 20. **Protocol-owned liquidity / POL:** Liquidity whose LP position is controlled by a protocol treasury or protocol contract. [Learn more: Olympus DAO](https://docs.olympusdao.finance/main/overview/treasury/)

> 21. **Community-owned liquidity:** Liquidity independently owned by ecosystem participants. [Learn more: Uniswap LPs](https://support.uniswap.org/hc/en-us/articles/20902968738317-What-is-liquidity-providing)

> 22. **Liquidity mining:** Distribution of token incentives to liquidity providers. **Based NUT:** Eligible Aerodrome NUT pools can receive AERO emissions through gauges. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 23. **Mercenary liquidity:** An informal term for liquidity supplied primarily to collect temporary incentives. [Learn more: Curve gauges](https://resources.curve.finance/reward-gauges/understanding-gauges/)

> 24. **Sticky liquidity:** An informal term for liquidity that remains deposited over extended periods because of ownership, lockups, fees, incentives, or strategy. [Learn more: Curve vote locking](https://resources.curve.finance/vecrv/understanding-vecrv/)

> 25. **TVL / total value locked:** The estimated market value of assets deposited in a protocol, pool, curve, or vault. TVL and active trading depth measure different properties. [Learn more: DeFiLlama](https://defillama.com/docs/definitions)

> 26. **Volume-to-TVL ratio:** Trading volume divided by TVL over a specified period.

> `volume-to-TVL = trading volume ÷ TVL`

> [Learn more: DeFiLlama](https://defillama.com/docs/definitions)

> 27. **Capital efficiency:** The amount of active liquidity or trading capacity produced per unit of deposited capital. [Learn more: Uniswap v3](https://developers.uniswap.org/docs/get-started/concepts/liquidity-providers/concentrated-liquidity)

> 28. **Withdrawal liquidity:** Assets currently available to satisfy depositor withdrawals. [Learn more: Morpho liquidity](https://docs.morpho.org/curate/concepts/liquidity/)

> 29. **Dust:** A token balance too small to use economically relative to gas or protocol minimums. [Learn more: Ethereum glossary](https://ethereum.org/glossary/)

> 30. **Exit liquidity:** A colloquial term for market demand available to absorb a seller’s position. [Learn more: Investor.gov](https://www.investor.gov/introduction-investing/investing-basics/glossary/liquidity-or-marketability)

***

### Liquidity Position Mechanics and Risks

> 1. **Impermanent loss / IL:** The difference between the value of assets held directly and the value of the same assets deposited in an automatically rebalancing AMM position. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/20973834361037-What-is-Impermanent-Loss)

> 2. **Realized LP loss:** A difference relative to holding that becomes fixed when an LP position is closed or withdrawn. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/20973834361037-What-is-Impermanent-Loss)

> 3. **Inventory risk:** The possibility that a liquidity position accumulates one asset while traders remove the other. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/20973834361037-What-is-Impermanent-Loss)

> 4. **Range risk:** The possibility that a concentrated-liquidity position moves outside its selected interval. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/32514988932877-What-does-out-of-range-liquidity-mean)

> 5. **Out of range:** A concentrated-liquidity position whose selected range no longer contains the current price. It does not execute swaps or earn swap fees while outside the range. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/32514988932877-What-does-out-of-range-liquidity-mean)

> 6. **Rebalancing:** Changing a liquidity position’s assets, weights, or price range. [Learn more: Uniswap concentrated liquidity](https://docs.uniswap.org/concepts/protocol/concentrated-liquidity)

> 7. **Pool imbalance:** A departure between current pool balances and the balance relationship implied by its pricing formula or configured weights. [Learn more: Balancer weighted pools](https://docs.balancer.fi/concepts/explore-available-balancer-pools/weighted-pool/weighted-pool.html)

> 8. **Adverse selection:** Trading that occurs when one participant has more current information than the counterparty or passive liquidity position. [Learn more: LVR research](https://arxiv.org/abs/2208.06046)

> 9. **LVR / loss versus rebalancing:** A measure comparing an AMM position with a benchmark portfolio that rebalances at external market prices. [Learn more: LVR paper](https://arxiv.org/abs/2208.06046)

> 10. **Toxic flow:** An informal market-making term for order flow that systematically trades against stale or unfavorable quotes. [Learn more: LVR paper](https://arxiv.org/abs/2208.06046)

> 11. **Liquidity lock:** Placement of LP ownership inside a contract that restricts withdrawal until specified conditions are met. [Learn more: OpenZeppelin timelocks](https://docs.openzeppelin.com/contracts/4.x/api/token/erc20#TokenTimelock)

> 12. **LP-token burn:** Transfer or destruction of LP ownership tokens so their associated withdrawal claim is no longer usable. The pool’s underlying assets remain in the pool. [Learn more: Uniswap v2 LP tokens](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 13. **Liquidity burn:** Informal terminology for burning or sinking LP tokens rather than burning the assets held by the pool. [Learn more: Uniswap v2](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 14. **Permanent liquidity:** Liquidity whose withdrawal claim has been irreversibly removed or whose contract rules do not permit withdrawal. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 15. **Dead liquidity:** Informal terminology for liquidity whose LP ownership token is held by a conventional dead address. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

***

### AMMs and Pricing Systems

> 1. **AMM / automated market maker:** A smart contract that prices and exchanges assets through predefined mathematical rules rather than a conventional order book. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 2. **Invariant:** The mathematical relationship an AMM applies when calculating pool transactions. [Learn more: Uniswap v2](https://docs.uniswap.org/whitepaper.pdf)

> 3. **Constant-product AMM:** An AMM commonly represented by:

> `x × y = k`

> A swap changes the two reserves while preserving the invariant after accounting for fees. [Learn more: Uniswap v2](https://docs.uniswap.org/whitepaper.pdf)

> 4. **Constant-sum AMM:** An AMM represented by:

> `x + y = k`

> It maintains a constant exchange rate until one side is exhausted. [Learn more: AMM research](https://arxiv.org/abs/2103.12732)

> 5. **Hybrid invariant:** A pricing formula combining characteristics of multiple AMM models, such as constant-product and constant-sum behavior. [Learn more: Curve StableSwap](https://resources.curve.finance/whitepaper/stableswap-paper/)

> 6. **CLAMM / concentrated-liquidity AMM:** An AMM where liquidity is assigned to selected price intervals. [Learn more: Uniswap v3](https://developers.uniswap.org/docs/get-started/concepts/liquidity-providers/concentrated-liquidity)

> 7. **Virtual reserves:** Mathematical reserve values used by an AMM’s pricing logic that need not equal its directly held token balances. [Learn more: Uniswap v3 math](https://blog.uniswap.org/uniswap-v3-math-primer)

> 8. **Weighted pool:** A Balancer pool whose pricing invariant uses configurable normalized asset weights, such as 80/20 or 25/25/25/25. Actual token balances and market values change as swaps occur. **Based NUT:** pNUT uses four 25% normalized weights. [Learn more: Balancer](https://docs.balancer.fi/concepts/explore-available-balancer-pools/weighted-pool/weighted-pool.html)

> 9. **Stable pool:** A pool using specialized math for assets expected to follow a close or predictable exchange relationship. [Learn more: Balancer stable pools](https://docs.balancer.fi/concepts/explore-available-balancer-pools/stable-pool/stable-pool.html)

> 10. **Boosted pool:** A pool integrating yield-bearing assets so deposited capital can participate in an external yield source while remaining represented in pool accounting. [Learn more: Balancer boosted pools](https://docs.balancer.fi/concepts/explore-available-balancer-pools/boosted-pool/boosted-pool.html)

> 11. **Composable stable pool:** A stable pool designed so its BPT can participate as an asset in another Balancer pool. [Learn more: Balancer](https://docs.balancer.fi/concepts/explore-available-balancer-pools/composable-stable-pool/composable-stable-pool.html)

> 12. **Managed pool:** A Balancer pool implementation supporting defined management operations such as gradual weight changes or token configuration. [Learn more: Balancer](https://docs.balancer.fi/concepts/explore-available-balancer-pools/managed-pool/managed-pool.html)

> 13. **Liquidity bootstrapping pool / LBP:** A weighted pool whose configured weights change over time to distribute a token and establish market pricing. [Learn more: Balancer LBP](https://docs.balancer.fi/concepts/explore-available-balancer-pools/liquidity-bootstrapping-pool.html)

> 14. **Fee tier:** The swap-fee rate assigned to a pool. [Learn more: Uniswap fees](https://docs.uniswap.org/concepts/protocol/fees)

> 15. **Dynamic fee:** A swap fee that changes according to protocol state or custom logic. [Learn more: Uniswap v4](https://docs.uniswap.org/contracts/v4/concepts/dynamic-fees)

***

### Bonding Curves

> 1. **Bonding curve:** A predefined relationship between token supply and price. Purchases commonly deposit a reserve asset and mint tokens; sales burn tokens and return reserve assets. **Based NUT:** SALT and NUTINO use NUT as their Mint Club base asset. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 2. **Continuous bonding curve:** A curve where price changes continuously according to a mathematical function. [Learn more: Bonding curves](https://yos.io/2018/11/10/bonding-curves/)

> 3. **Discrete bonding curve:** A curve divided into predefined supply intervals, each with a specified price. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 4. **Mint Club bonding curve:** A discrete bonding curve composed of `BondStep` supply ranges and prices. Buying mints the asset and deposits its base asset; selling burns the asset and returns base assets. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 5. **Bond step / price interval:** A supply range within a discrete bonding curve that uses one predefined unit price. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 6. **Curve token:** The token or ERC-1155 asset created and destroyed through a bonding curve. **Based NUT:** SALT and NUTINO are NUT-reserve curve tokens. [Learn more: Mint Club](https://docs.mint.club/)

> 7. **Curve reserve / base asset:** The asset deposited into the bonding-curve contract and returned during redemption. **Based NUT:** NUT is the base asset for its nested Mint Club tokens. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 8. **Mint price:** The amount of base asset required to create the requested curve-token quantity. [Learn more: Mint Club minting](https://docs.mint.club/mintburn/minting)

> 9. **Burn price:** The amount of base asset returned when curve tokens are destroyed. [Learn more: Mint Club burning](https://docs.mint.club/mintburn/burning)

> 10. **Curve spread:** The difference between effective mint and burn execution created by price steps, royalties, or other curve rules. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 11. **Curve depth:** The amount that can be minted or burned before a transaction enters different price intervals. [Learn more: Mint Club curve design](https://docs.mint.club/tools/bonding-curve-design)

> 12. **Maximum minting supply:** The highest curve-token supply permitted by the deployed Mint Club configuration. [Learn more: Mint Club](https://docs.mint.club/create/token)

> 13. **Free minting allocation:** Curve-token or NFT supply issued to the creator during deployment without following the public curve purchase path. [Learn more: Mint Club](https://docs.mint.club/create/token)

> 14. **Average reserve per token:** Curve reserve divided by outstanding curve-token supply.

> `average reserve per token = curve reserve ÷ token supply`

> This value is not the same as Mint Club’s current marginal mint or burn price, which is determined by the active `BondStep` intervals. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 15. **Curve-backed token:** A token redeemable through a bonding-curve contract for its specified base asset. **Based NUT:** NUT-backed child tokens are curve-backed according to their deployed Mint Club rules. [Learn more: Mint Club](https://docs.mint.club/mintburn/mint-burn-overview)

> 16. **Liquidity versus backing:** Liquidity provides a trading route; backing provides an enforceable redemption relationship. **Based NUT:** A token paired with NUT has NUT liquidity, while a Mint Club token redeemable for NUT has a NUT reserve relationship. [Learn more: Mint Club](https://docs.mint.club/mintburn/mint-burn-overview)

***

### Oracles

> 1. **Oracle:** A mechanism that supplies a price or external fact to a smart contract. [Learn more: Chainlink](https://chain.link/education/blockchain-oracles)

> 2. **Oracle source:** The pool, exchange, reporting network, or data system from which an oracle obtains information. [Learn more: Chainlink](https://docs.chain.link/data-feeds)

> 3. **Spot oracle:** An oracle using a market’s current instantaneous price. [Learn more: Uniswap v2](https://docs.uniswap.org/whitepaper.pdf)

> 4. **TWAP / time-weighted average price:** A price averaged over a selected period, with each time interval contributing according to its duration. **Based NUT:** NUT’s Uniswap markets can provide observations used to calculate TWAPs. [Learn more: Uniswap](https://docs.uniswap.org/sdk/v3/guides/advanced/price-oracle)

> 5. **VWAP / volume-weighted average price:** An average price weighted by the amount traded at each price. [Learn more: Coinbase](https://www.coinbase.com/learn/advanced-trading/what-is-vwap)

> 6. **Oracle window:** The historical period included in an averaged oracle price. [Learn more: Uniswap](https://docs.uniswap.org/sdk/v3/guides/advanced/price-oracle)

> 7. **Oracle observation:** A stored price, tick, or cumulative-value checkpoint used to calculate an oracle result. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v3/reference/core/interfaces/pool/IUniswapV3PoolDerivedState)

> 8. **Oracle cardinality:** The number of historical observations a Uniswap v3 pool is configured to retain. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v3/reference/core/interfaces/pool/IUniswapV3PoolActions#increaseobservationcardinalitynext)

> 9. **Oracle latency:** The delay between a market change and its appearance in the oracle result. [Learn more: Chainlink](https://docs.chain.link/data-feeds/selecting-data-feeds)

> 10. **Oracle staleness:** A condition where the latest available oracle value is older than the consuming application permits. [Learn more: Chainlink](https://docs.chain.link/data-feeds/selecting-data-feeds)

> 11. **Oracle manipulation:** Trading or state manipulation intended to make an oracle report an artificial value. [Learn more: Uniswap v2](https://docs.uniswap.org/whitepaper.pdf)

> 12. **Manipulation cost:** The capital and trading loss required to move an oracle result by a selected amount and duration. [Learn more: Uniswap oracle guide](https://docs.uniswap.org/sdk/v3/guides/advanced/price-oracle)

> 13. **Oracle depth:** The active liquidity available in the market supplying oracle observations. **Based NUT:** NUT oracle depth is measured separately for each source pool. [Learn more: Uniswap concentrated liquidity](https://developers.uniswap.org/docs/get-started/concepts/liquidity-providers/concentrated-liquidity)

> 14. **Oracle deviation:** The difference between an oracle value and another selected reference value. [Learn more: Chainlink](https://docs.chain.link/data-feeds/selecting-data-feeds)

> 15. **Deviation threshold:** A configured difference that triggers an update, rejection, pause, or fallback action. [Learn more: Chainlink](https://docs.chain.link/data-feeds/selecting-data-feeds)

> 16. **Heartbeat:** The intended maximum interval between oracle updates. [Learn more: Chainlink](https://docs.chain.link/data-feeds/selecting-data-feeds)

> 17. **Fallback oracle:** A secondary source used when the primary oracle fails a defined validity condition. [Learn more: Chainlink architecture](https://docs.chain.link/architecture-overview/architecture-decentralized-model)

> 18. **Circuit breaker:** Logic that pauses or restricts operations when defined price, deviation, or system conditions occur. [Learn more: OpenZeppelin Pausable](https://docs.openzeppelin.com/contracts/5.x/api/utils#Pausable)

> 19. **Oracle pool:** A liquidity pool used as a source of price observations. **Based NUT:** NUT’s canonical oracle pool is the designated primary source within its wider oracle network. [Learn more: Uniswap](https://docs.uniswap.org/sdk/v3/guides/advanced/price-oracle)

> 20. **Oracle network:** A collection of independent or related oracle sources used together. **Based NUT:** The NUT oracle network refers to price information from its multiple liquidity venues. [Learn more: Chainlink](https://docs.chain.link/architecture-overview/architecture-decentralized-model)

***

### Tokenization and Token Standards

> 1. **Tokenization:** Representation of an asset, right, service, identity, position, membership, or economic relationship as an onchain token. **Based NUT:** The ecosystem tokenizes currencies, bonding-curve claims, pool ownership, NFTs, and agent-related assets. [Learn more: Ethereum token standards](https://ethereum.org/developers/docs/standards/tokens/)

> 2. **Fungible token:** A token whose units are interchangeable under the same contract rules. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 3. **Non-fungible token / NFT:** A token identified by a distinct token ID representing a unique asset or position. [Learn more: ERC-721](https://eips.ethereum.org/EIPS/eip-721)

> 4. **Semi-fungible token:** A token where units sharing one ERC-1155 ID are interchangeable, while different IDs represent separate asset classes. [Learn more: ERC-1155](https://eips.ethereum.org/EIPS/eip-1155)

> 5. **ERC-20:** The Ethereum token standard for fungible assets. One contract normally represents one interchangeable token. **Based NUT:** NUT, SNUT, fungible Mint Club tokens, BPTs, and vault shares use ERC-20-compatible interfaces. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 6. **ERC-721:** The Ethereum standard for non-fungible tokens identified by unique token IDs. [Learn more: ERC-721](https://eips.ethereum.org/EIPS/eip-721)

> 7. **ERC-1155:** A multi-token standard allowing one contract to manage multiple token IDs, each with its own supply and metadata. **Based NUT:** NUT-backed editions or item classes can be created as ERC-1155 assets. [Learn more: ERC-1155](https://eips.ethereum.org/EIPS/eip-1155)

> 8. **ERC-20 versus ERC-1155:** ERC-20 represents one fungible token per contract. ERC-1155 represents multiple token IDs under one contract, with each ID capable of having several interchangeable units. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20) · [ERC-1155](https://eips.ethereum.org/EIPS/eip-1155)

> 9. **ERC-4626:** A standardized interface for tokenized vaults that accept an underlying ERC-20 asset and issue ERC-20 shares. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 10. **Position NFT:** An NFT representing a unique financial position. **Based NUT:** Uniswap v3 liquidity positions involving NUT are commonly represented through the NonfungiblePositionManager. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v3/reference/periphery/NonfungiblePositionManager)

> 11. **BPT / Balancer Pool Token:** An ERC-20 token representing proportional ownership of a Balancer pool. **Based NUT:** pNUT is a Balancer v2 BPT. [Learn more: Balancer](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 12. **Vault share:** A token representing proportional ownership of a vault’s managed assets. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 13. **Receipt token:** A token recording a deposit, lending position, stake, or liquidity claim. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 14. **Yield-bearing token:** A token whose balance or redemption value reflects yield generated by underlying assets. [Learn more: Balancer](https://docs.balancer.fi/concepts/core-concepts/yield-bearing-tokens.html)

> 15. **Wrapped token:** A tokenized representation of another asset deposited, locked, or controlled through a wrapper system. [Learn more: Wrapped ETH](https://ethereum.org/wrapped-eth/)

> 16. **Wrap:** Deposit an asset into a wrapper and receive its tokenized representation. [Learn more: Wrapped ETH](https://ethereum.org/wrapped-eth/)

> 17. **Unwrap:** Return or burn a wrapped representation to recover its underlying asset. [Learn more: Wrapped ETH](https://ethereum.org/wrapped-eth/)

> 18. **Redemption:** Exchange a tokenized claim for its underlying assets according to the issuing contract’s rules. **Based NUT:** Mint Club child tokens are redeemed by burning them for NUT. [Learn more: Mint Club](https://docs.mint.club/mintburn/mint-burn-overview)

> 19. **Redeemability:** The contract-defined ability to exchange a token for an underlying asset or basket. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 20. **Backing:** Assets contractually available to satisfy a token’s redemption claim. **Based NUT:** NUT-backed Mint Club tokens have a NUT reserve path; NUT trading pairs provide liquidity rather than redemption backing. [Learn more: Mint Club](https://docs.mint.club/mintburn/mint-burn-overview)

> 21. **Collateralization:** Assignment of assets to secure debt or another enforceable obligation. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/ltv/)

> 22. **Nested token:** A descriptive term for a token whose reserve, redemption, liquidity, or pricing path depends on another token. **Based NUT:** SALT and NUTINO are nested beneath NUT through Mint Club curves. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 23. **Child token:** A secondary token issued beneath a parent asset or ecosystem. The exact relationship is defined by its contracts. **Based NUT:** SALT and NUTINO are child tokens using NUT as their curve reserve. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 24. **Parent token:** The higher-level asset used as a reserve, denomination, liquidity anchor, or reference for child tokens. **Based NUT:** NUT is the parent reserve asset for its nested Mint Club tokens. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 25. **Orbit token:** A Based NUT project term for a token whose reserve, liquidity, services, or incentives connect to NUT or another NUT-linked position. It is not an Ethereum token standard. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 26. **Meta-token:** A descriptive term for a token representing or coordinating lower-level tokens, pools, or financial positions. **Based NUT:** pNUT represents ownership of a multi-asset Balancer pool. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 27. **Basket token:** A token representing proportional exposure to multiple underlying assets. **Based NUT:** pNUT represents a basket containing cbETH, cbBTC, NUT, and SNUT. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 28. **NAV / net asset value:** The value of underlying assets minus liabilities, divided by outstanding shares. `NAV per share = (assets − liabilities) ÷ outstanding shares`

> **Based NUT:** pNUT NAV is calculated from the current value of its pool assets and outstanding BPT supply. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 29. **Premium to NAV:** A secondary-market price above calculated NAV. [Learn more: NAV](https://www.investopedia.com/terms/n/nav.asp)

> 30. **Discount to NAV:** A secondary-market price below calculated NAV. [Learn more: NAV](https://www.investopedia.com/terms/n/nav.asp)

> 31. **Backing chain:** A descriptive term for the sequence of contracts and assets connecting a token to its final redeemable reserve. **Based NUT:** A nested NUT asset may include a curve, LP token, metapool, or vault in its backing chain. [Learn more: Balancer composability](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 32. **Reserve path:** The contracts and assets used to redeem a token. **Based NUT:** A NUT-backed Mint Club token’s reserve path leads through its bonding curve to NUT. [Learn more: Mint Club](https://docs.mint.club/mintburn/mint-burn-overview)

> 33. **Liquidity path:** The markets and routers used to trade one token for another. A liquidity path is separate from a redemption path. [Learn more: Uniswap routing](https://docs.uniswap.org/contracts/v3/concepts/advanced-topics/routing)

***

### Token Supply, Minting, and Burning

> 1. **Raw token units:** Integer units recorded by a token contract before adjustment for decimals. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 2. **Decimals:** The display precision used to convert raw token units into human-readable amounts. **Based NUT:** NUT uses 18 decimals, so its one-token total supply is divisible. [Learn more: NUT contract](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df)

> 3. **Total supply:** The quantity reported by a token contract’s `totalSupply()` function. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 4. **Maximum supply:** The highest supply permitted by the token’s enforceable contract rules. [Learn more: OpenZeppelin ERC20Capped](https://docs.openzeppelin.com/contracts/5.x/api/token/erc20#ERC20Capped)

> 5. **Circulating supply:** An estimate of tokens considered economically available to the market. The calculation may exclude specified treasury, dead-address, vesting, or locked balances. [Learn more: CoinMarketCap](https://coinmarketcap.com/academy/glossary/circulating-supply)

> 6. **Accessible supply:** Tokens controlled by addresses capable of transferring them. **Based NUT:** NUT held at an inaccessible sink address remains in `totalSupply` but is excluded from accessible supply. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 7. **Free float:** Tokens realistically available for public trading after excluding selected locked, treasury, dead-address, or concentrated holdings. [Learn more: CoinMarketCap](https://coinmarketcap.com/academy/glossary/circulating-supply)

> 8. **Locked supply:** Tokens subject to contract-defined transfer restrictions or vesting conditions. [Learn more: OpenZeppelin VestingWallet](https://docs.openzeppelin.com/contracts/5.x/api/finance#VestingWallet)

> 9. **Treasury supply:** Tokens controlled by a protocol treasury. [Learn more: DeFiLlama treasuries](https://defillama.com/treasuries)

> 10. **Emission:** New token supply distributed according to a protocol schedule or rule. [Learn more: Ethereum issuance](https://ethereum.org/roadmap/merge/issuance/)

> 11. **Emission rate:** The amount of new token supply issued during a specified period. [Learn more: Aerodrome emissions](https://aerodrome.finance/docs)

> 12. **Inflation:** An increase in token supply over time. [Learn more: Ethereum issuance](https://ethereum.org/roadmap/merge/issuance/)

> 13. **Deflation:** A decrease in token supply. When the term refers only to accessible or circulating supply, that qualification should be stated explicitly. [Learn more: ERC-5679](https://eips.ethereum.org/EIPS/eip-5679)

> 14. **Dilution:** A decrease in an existing holder’s proportional claim caused by issuing new claims without proportional growth in associated assets or rights. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 15. **Non-dilutive share issuance:** Creation of new pool or vault shares against proportional deposits of underlying assets. **Based NUT:** pNUT supply expands when assets are deposited and contracts when BPT shares are redeemed. [Learn more: Balancer liquidity](https://docs.balancer.fi/concepts/vault/add-remove-liquidity.html)

> 16. **Mint:** Create new token units and increase token supply. **Based NUT:** Minting SALT or NUTINO deposits NUT into the corresponding Mint Club curve. [Learn more: ERC-5679](https://eips.ethereum.org/EIPS/eip-5679)

> 17. **Mint authority:** The address, role, or contract authorized to create token units. [Learn more: OpenZeppelin access control](https://docs.openzeppelin.com/contracts/5.x/access-control)

> 18. **Permissionless minting:** Minting available to any user who satisfies public contract rules. [Learn more: Mint Club](https://docs.mint.club/mintburn/minting)

> 19. **Collateralized minting:** Creation of tokens in exchange for deposited reserve or collateral assets. **Based NUT:** NUT-backed child-token minting is collateralized by NUT deposited into Mint Club. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 20. **Share minting:** Creation of pool or vault shares in exchange for deposits of underlying assets. **Based NUT:** Adding liquidity to pNUT creates BPT shares. [Learn more: Balancer](https://docs.balancer.fi/concepts/vault/add-remove-liquidity.html)

> 21. **Burn:** Destroy token units through contract logic. A true ERC-20 burn decreases `totalSupply`. [Learn more: OpenZeppelin ERC20Burnable](https://docs.openzeppelin.com/contracts/5.x/api/token/erc20#ERC20Burnable)

> 22. **Contract burn / true burn:** A burn implemented by the token contract that subtracts units from both an account balance and `totalSupply`. [Learn more: ERC-5679](https://eips.ethereum.org/EIPS/eip-5679)

> 23. **Burn function:** A callable method such as `burn()` or `burnFrom()` that destroys tokens under defined authorization rules. [Learn more: OpenZeppelin](https://docs.openzeppelin.com/contracts/5.x/api/token/erc20#ERC20Burnable)

> 24. **Zero address:** `0x0000000000000000000000000000000000000000`. Token standards commonly use transfers from or to this address as event notation for minting and burning. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 25. **Dead address / burn address:** A conventional sink address, commonly `0x000000000000000000000000000000000000dEaD`, whose private key is presumed unknown. It is an ordinary address unless the token contract gives it special treatment. [Learn more: ERC-5679](https://eips.ethereum.org/EIPS/eip-5679)

> 26. **Dead-address transfer:** A token transfer to a conventional sink address. It normally changes address balances but does not change `totalSupply`. **Based NUT:** NUT and SNUT sent to `0x…dEaD` are token sinks rather than confirmed contract burns. [Learn more: NUT ABI](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df#code)

> 27. **Economic burn:** Removal of tokens from practical circulation without necessarily decreasing contract-reported supply. **Based NUT:** This term describes NUT sent to a dead address because the verified NUT ABI exposes no burn method. [Learn more: NUT contract](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df#code)

> 28. **Token sink:** An address or mechanism that receives tokens and removes them from active circulation. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 29. **Burn rate:** The quantity or percentage of tokens destroyed or sunk during a defined period. The measurement should specify which burn definition is used. [Learn more: Ethereum issuance](https://ethereum.org/roadmap/merge/issuance/)

> 30. **Net issuance:** Newly minted tokens minus tokens destroyed through true contract burns.

> `net issuance = minted supply − contract-burned supply`

> [Learn more: Ethereum issuance](https://ethereum.org/roadmap/merge/issuance/)

> 31. **Buyback:** Use of protocol or treasury funds to purchase a token from a market. [Learn more: Token Terminal](https://tokenterminal.com/resources/metrics)

> 32. **Buyback-and-burn:** Purchasing tokens from a market and destroying them through contract burn logic. [Learn more: OpenZeppelin ERC20Burnable](https://docs.openzeppelin.com/contracts/5.x/api/token/erc20#ERC20Burnable)

> 33. **Buyback-and-sink:** Purchasing tokens and transferring them to a conventional dead address without changing `totalSupply`. **Based NUT:** This describes SNUT buybacks sent to the dead address. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 34. **Redemption burn:** Destruction of a tokenized claim in exchange for underlying assets. **Based NUT:** Mint Club child tokens are burned when redeemed for NUT. [Learn more: Mint Club](https://docs.mint.club/mintburn/burning)

> 35. **Burn proof:** Onchain evidence showing the token, amount, transaction, destination, and whether `totalSupply` changed. [Learn more: BaseScan](https://basescan.org/)

***

### Fees, Royalties, and Taxes

> 1. **Swap fee:** A percentage charged when assets are exchanged through a pool. [Learn more: Uniswap fees](https://docs.uniswap.org/concepts/protocol/fees)

> 2. **LP fee:** The portion of swap fees allocated to liquidity providers. [Learn more: Uniswap fees](https://docs.uniswap.org/concepts/protocol/fees)

> 3. **Protocol fee:** A fee retained by the protocol rather than allocated entirely to LPs. [Learn more: Balancer protocol fees](https://docs.balancer.fi/concepts/protocol-fee-model.html)

> 4. **Interface fee:** A fee charged by an application interface separately from the underlying protocol. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/20131678274957-Uniswap-Labs-Interface-Fee)

> 5. **Creator royalty:** A fee allocated to an asset creator when a specified action occurs. **Based NUT:** Mint Club supports separately configured mint and burn royalties for NUT-backed assets. [Learn more: Mint Club](https://docs.mint.club/royalties/creator-royalties)

> 6. **Mint royalty:** A creator royalty applied when a bonding-curve asset is minted. [Learn more: Mint Club](https://docs.mint.club/royalties/creator-royalties)

> 7. **Burn royalty:** A creator royalty applied when a bonding-curve asset is burned and redeemed. [Learn more: Mint Club](https://docs.mint.club/royalties/creator-royalties)

> 8. **Token tax / transfer tax:** Contract logic that deducts part of a token transfer and assigns it according to predefined rules. **Based NUT:** SNUT applies transfer-fee logic; NUT’s verified fixed-token contract does not. [Learn more: Uniswap token fees](https://support.uniswap.org/hc/en-us/articles/18673568523789-What-is-a-token-fee)

> 9. **Buy tax:** A token fee applied when a transfer is classified as a market purchase. [Learn more: Uniswap token fees](https://support.uniswap.org/hc/en-us/articles/18673568523789-What-is-a-token-fee)

> 10. **Sell tax:** A token fee applied when a transfer is classified as a market sale. [Learn more: Uniswap token fees](https://support.uniswap.org/hc/en-us/articles/18673568523789-What-is-a-token-fee)

> 11. **Wallet-to-wallet tax:** A token fee applied to transfers between ordinary addresses rather than only pool transactions. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 12. **Fee-on-transfer token:** A token where the recipient receives less than the nominal transfer amount because contract logic deducts a fee. **Based NUT:** SNUT is a fee-on-transfer token. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/18673568523789-What-is-a-token-fee)

> 13. **Entry fee:** A fee charged when assets enter a vault or managed position. [Learn more: OpenZeppelin ERC-4626](https://docs.openzeppelin.com/contracts/5.x/erc4626)

> 14. **Exit fee:** A fee charged when assets are withdrawn or redeemed. [Learn more: OpenZeppelin ERC-4626](https://docs.openzeppelin.com/contracts/5.x/erc4626)

> 15. **Performance fee:** A fee calculated from gains generated by a managed strategy. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 16. **Management fee:** A recurring fee calculated against managed assets or shares. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 17. **Tax exemption:** A contract rule excluding specified addresses or transactions from transfer fees. [Learn more: OpenZeppelin access control](https://docs.openzeppelin.com/contracts/5.x/access-control)

> 18. **Fee receiver:** The address or contract receiving a fee allocation. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 19. **Auto-liquidity fee:** A token fee allocated toward acquiring pool assets and adding liquidity. **Based NUT:** The SNUT fee configuration includes an allocation identified for liquidity. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 20. **Swapback:** Token logic that exchanges accumulated fee tokens and allocates the proceeds according to contract rules. [Learn more: Uniswap token fees](https://support.uniswap.org/hc/en-us/articles/18673568523789-What-is-a-token-fee)

> 21. **Reward fee:** A transfer-fee allocation used to distribute a reward asset to eligible holders. **Based NUT:** SNUT uses a reward-position allocation connected to NUT rewards. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 22. **Buyback fee:** A fee allocation reserved for token market purchases. **Based NUT:** A portion of SNUT fees is identified for buyback-and-sink operations. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 23. **Fee stacking:** The application of several independent fees within one transaction route, such as a pool fee, transfer tax, royalty, and interface fee. [Learn more: Uniswap token fees](https://support.uniswap.org/hc/en-us/articles/18673568523789-What-is-a-token-fee)

> 24. **Effective trade cost:** The total economic cost of execution.

> `effective cost = pool fees + token taxes + royalties + price impact + gas + MEV effects`

> [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/8643794102669-Price-Impact-vs-Price-Slippage)

***

### Arbitrage, Transactions, and MEV

> 1. **Arbitrage:** Trading against a price difference between markets or mechanisms. **Based NUT:** Arbitrage can connect NUT pools, Mint Club curves, NFT markets, and pNUT NAV. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/25845512413069-Why-is-a-pool-out-of-sync)

> 2. **Arbitrageur:** A trader, contract, or automated system that executes arbitrage. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 3. **Arbitrage bot:** Software that identifies, calculates, and submits arbitrage transactions. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 4. **Cross-venue arbitrage:** Buying an asset on one venue and selling it on another. **Based NUT:** NUT has separate Uniswap and Aerodrome venues. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/25845512413069-Why-is-a-pool-out-of-sync)

> 5. **Cross-pool arbitrage:** Trading between separate pools containing the same or economically related assets. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/25845512413069-Why-is-a-pool-out-of-sync)

> 6. **Triangular arbitrage:** Trading through at least three asset pairs and returning to the starting asset with more of it than the initial amount, before costs. [Learn more: Coinbase](https://www.coinbase.com/learn/advanced-trading/what-is-crypto-arbitrage-trading)

> 7. **Multi-hop arbitrage:** Arbitrage executed through several intermediate pools or assets. [Learn more: Uniswap routing](https://docs.uniswap.org/contracts/v3/concepts/advanced-topics/routing)

> 8. **Atomic arbitrage:** Arbitrage completed within one transaction so all steps succeed or all state changes revert. [Learn more: Ethereum transactions](https://ethereum.org/developers/docs/transactions/)

> 9. **Flash-loan arbitrage:** Atomic arbitrage funded by a flash loan that must be repaid within the same transaction. [Learn more: Aave](https://aave.com/docs/developers/flash-loans)

> 10. **Bonding-curve arbitrage:** Trading between a bonding curve and an external market when their executable prices differ. **Based NUT:** SALT and NUTINO have Mint Club curves and external DEX markets. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 11. **Mint arbitrage:** Minting a token when its total issuance cost is below its executable secondary-market value. [Learn more: Mint Club](https://docs.mint.club/mintburn/minting)

> 12. **Burn arbitrage:** Buying a redeemable token below its net redemption value and burning it to receive the reserve asset. [Learn more: Mint Club](https://docs.mint.club/mintburn/burning)

> 13. **NAV arbitrage:** Trading between a share token and the value of its redeemable underlying assets. **Based NUT:** pNUT market value can be compared with its Balancer pool NAV. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 14. **Basket arbitrage:** Trading between a basket token and the aggregate executable value of its components. **Based NUT:** pNUT represents a four-asset basket. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 15. **Arbitrage spread:** The gross difference between acquisition and disposal prices. [Learn more: Coinbase](https://www.coinbase.com/learn/advanced-trading/what-is-crypto-arbitrage-trading)

> 16. **Net arbitrage profit:** The remaining result after all execution costs.`net profit = gross spread − fees − taxes − royalties − gas − price impact − financing costs` . [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 17. **Arbitrage threshold:** The minimum price difference required for an arbitrage route to remain positive after its costs. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 18. **Execution risk:** The possibility that transaction conditions change between calculation and execution. [Learn more: Ethereum transactions](https://ethereum.org/developers/docs/transactions/)

> 19. **Revert:** Cancellation of a transaction’s state changes after execution fails. Gas used before the failure may still be charged. [Learn more: Ethereum transactions](https://ethereum.org/developers/docs/transactions/)

> 20. **Gas:** The measurement of computational work performed by an Ethereum-compatible network. [Learn more: Ethereum](https://ethereum.org/developers/docs/gas/)

> 21. **Gas fee:** The amount paid for transaction computation and block inclusion. [Learn more: Ethereum](https://ethereum.org/developers/docs/gas/)

> 22. **Priority fee:** An additional fee offered to a block producer for transaction inclusion. [Learn more: Ethereum](https://ethereum.org/developers/docs/gas/)

> 23. **Nonce:** A sequential account value used to order transactions and prevent replay. [Learn more: Ethereum transactions](https://ethereum.org/developers/docs/transactions/)

> 24. **Mempool:** A system holding pending transactions before block inclusion. [Learn more: Ethereum glossary](https://ethereum.org/glossary/)

> 25. **MEV / maximal extractable value:** Value obtained through transaction inclusion, exclusion, or ordering. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 26. **Front-running:** Executing before a known or anticipated transaction to act on its expected effects. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 27. **Back-running:** Executing directly after another transaction to act on the state change it creates. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 28. **Sandwich attack:** A transaction sequence that places one trade before and another after a user’s swap, changing the user’s execution and capturing the resulting difference. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

> 29. **Private order flow:** Transactions submitted through private infrastructure rather than broadcast directly to a public mempool. [Learn more: Ethereum MEV](https://ethereum.org/developers/docs/mev/)

***

### Lending, Liquidation, and Morpho Vaults

> 1. **Vault:** A contract accepting deposits and issuing shares representing proportional ownership of managed assets. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 2. **Strategy vault:** A vault allocating deposited assets according to one or more predefined strategies. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 3. **Lending vault:** A vault allocating deposited assets into lending markets. [Learn more: Morpho](https://docs.morpho.org/curate/concepts/liquidity/)

> 4. **Morpho market:** An isolated lending market defined by a loan asset, collateral asset, oracle, interest-rate model, and LLTV. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/market-mechanics/)

> 5. **Morpho Vault:** A tokenized vault that accepts a deposit asset and allocates it across authorized Morpho markets or adapters. Depositors receive proportional vault shares. [Learn more: Morpho](https://docs.morpho.org/curate/concepts/liquidity/)

> 6. **Vault curator:** The entity configuring authorized markets, adapters, caps, and risk parameters for a vault. [Learn more: Morpho curation](https://docs.morpho.org/curate/concepts/liquidity/)

> 7. **Vault allocator:** The entity or automation moving assets among destinations permitted by the vault configuration. [Learn more: Morpho curation](https://docs.morpho.org/curate/concepts/liquidity/)

> 8. **Vault share price:** The quantity of underlying assets represented by one vault share. [Learn more: ERC-4626](https://eips.ethereum.org/EIPS/eip-4626)

> 9. **Supply APY:** The annualized rate earned by suppliers according to current market conditions. [Learn more: Morpho rates](https://docs.morpho.org/learn/concepts/rates/)

> 10. **Borrow APY:** The annualized rate charged to borrowers according to current market conditions. [Learn more: Morpho rates](https://docs.morpho.org/learn/concepts/rates/)

> 11. **Interest-rate model:** The formula used to calculate borrowing rates. [Learn more: Morpho IRM](https://docs.morpho.org/learn/concepts/irm/)

> 12. **Utilization:** The portion of supplied assets currently borrowed. `utilization = borrowed assets ÷ supplied assets` . [Learn more: Morpho rates](https://docs.morpho.org/learn/concepts/rates/)

> 13. **.Collateral:** Assets pledged to secure borrowed assets. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/ltv/)

> 14. **Loan asset:** The asset supplied by lenders and borrowed by borrowers in a lending market. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/market-mechanics/)

> 15. **Debt:** Borrowed principal plus accrued interest. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/market-mechanics/)

> 16. **LTV / loan-to-value:** Debt value divided by collateral value. `LTV = debt value ÷ collateral value` . [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/ltv/)

> 17. **LLTV / liquidation loan-to-value:** The market parameter specifying the LTV at which a position becomes eligible for liquidation. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/ltv/)

> 18. **Health factor:** A measurement of a position’s distance from liquidation. `health factor = collateral value × LLTV ÷ debt value` . A Morpho position becomes liquidatable when its health factor reaches 1 or below. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/concepts/ltv/)

> 19. **Liquidation:** A process where a third party repays unhealthy debt and receives collateral according to the market’s liquidation rules. **Based NUT:** A Morpho market involving a NUT-linked asset would require a defined collateral asset, loan asset, oracle, interest-rate model, and LLTV. [Learn more: Morpho](https://docs.morpho.org/learn/concepts/liquidation/)

> 20. **Liquidator:** A wallet, bot, or contract executing a liquidation. [Learn more: Morpho](https://docs.morpho.org/learn/concepts/liquidation/)

> 21. **Liquidation incentive:** The additional collateral value available to a liquidator under the market’s liquidation formula. [Learn more: Morpho](https://docs.morpho.org/learn/concepts/liquidation/)

> 22. **Liquidation price:** The collateral price at which a position reaches its liquidation threshold, assuming other inputs remain constant. [Learn more: Morpho](https://docs.morpho.org/developers/borrow/tutorials/get-data/)

> 23. **Bad debt:** Debt remaining after available collateral can no longer fully cover repayment. [Learn more: Morpho](https://docs.morpho.org/curate/tutorials-v2/bad-debt/)

> 24. **Withdrawal queue:** The configured order in which a vault retrieves assets from markets or adapters to satisfy withdrawals. [Learn more: Morpho liquidity](https://docs.morpho.org/curate/concepts/liquidity/)

> 25. **Supply cap:** The maximum exposure a vault or market permits for a supplied asset or destination. [Learn more: Morpho curation](https://docs.morpho.org/curate/concepts/liquidity/)

> 26. **Market isolation:** Separation of lending positions into independently configured markets. [Learn more: Morpho markets](https://docs.morpho.org/developers/borrow/concepts/market-mechanics/)

***

### NFTs, ERC-1155, and Sudoswap

> 1. **NFT collection:** A group of NFTs associated through a common contract, creator, metadata system, or project. **Based NUT:** NUT Army assets form project-defined collections. [Learn more: ERC-721](https://eips.ethereum.org/EIPS/eip-721)

> 2. **Collection floor:** The lowest current asking price for an NFT in a collection. [Learn more: OpenSea](https://support.opensea.io/en/articles/8867085-what-is-floor-price)

> 3. **NFT liquidity:** The availability of buyers, sellers, or pools for exchanging NFTs. [Learn more: Sudoswap](https://docs.sudoswap.xyz/)

> 4. **NFT inventory:** NFTs held by a pool, vault, market maker, or treasury. [Learn more: Sudoswap pair creation](https://docs.sudoswap.xyz/reference/pair-creation/)

> 5. **NFT AMM:** A smart contract that quotes NFT purchase or sale prices according to a defined pricing curve. [Learn more: Sudoswap](https://docs.sudoswap.xyz/)

> 6. **Sudoswap:** An NFT AMM supporting ERC-721 and ERC-1155 assets against ETH or ERC-20 tokens through configurable pools and bonding curves. **Based NUT:** Sudoswap can provide markets for Based NUT NFT collections. [Learn more: Sudoswap](https://docs.sudoswap.xyz/)

> 7. **Buy-only NFT pool:** A pool holding payment assets and quoting prices to acquire NFTs. [Learn more: Sudoswap](https://docs.sudoswap.xyz/user-guide/creating-a-pool/)

> 8. **Sell-only NFT pool:** A pool holding NFTs and quoting prices to sell them. [Learn more: Sudoswap](https://docs.sudoswap.xyz/user-guide/creating-a-pool/)

> 9. **Trade NFT pool:** A pool holding both NFTs and payment assets and quoting both buy and sell transactions. [Learn more: Sudoswap](https://docs.sudoswap.xyz/user-guide/creating-a-pool/)

> 10. **Linear NFT curve:** A Sudoswap curve where the quoted price changes by a fixed amount after each trade. [Learn more: Sudoswap pricing](https://docs.sudoswap.xyz/reference/pricing/)

> 11. **Exponential NFT curve:** A Sudoswap curve where the quoted price changes by a fixed percentage after each trade. [Learn more: Sudoswap pricing](https://docs.sudoswap.xyz/reference/pricing/)

> 12. **XYK NFT curve:** A Sudoswap curve using constant-product-style virtual reserves. [Learn more: Sudoswap pricing](https://docs.sudoswap.xyz/reference/pricing/)

> 13. **GDA / gradual Dutch auction curve:** A pricing curve whose quote changes according to time and transaction sequence. [Learn more: Sudoswap auctions](https://docs.sudoswap.xyz/user-guide/creating-an-auction/)

> 14. **NFT fractionalization:** Creation of fungible or semi-fungible claims representing economic exposure to an NFT or NFT collection held by a wrapper or vault. [Learn more: ERC-3386 proposal](https://eips.ethereum.org/EIPS/eip-3386)

> 15. **NFT wrapper vault:** A contract holding NFTs and issuing tokenized claims against them. [Learn more: ERC-3386 proposal](https://eips.ethereum.org/EIPS/eip-3386)

> 16. **Sudoswap fractionalization:** Sudoswap can trade ERC-1155 quantities or fractional tokens created by another system, but an ordinary Sudoswap ERC-721 pool does not divide an NFT into ownership fractions. **Based NUT:** A separate wrapper would perform any fractionalization of a unique NUT NFT. [Learn more: Sudoswap ERC-1155](https://docs.sudoswap.xyz/v2/erc1155/)

***

### AI Agents and Virtuals

> 1. **AI agent:** Software that receives objectives, observes state, selects actions, uses tools, and performs tasks with some degree of autonomy. **Based NUT:** Peanutoshi Nutkamoto is the ecosystem’s AI-agent identity. [Learn more: Virtuals](https://os.virtuals.io/)

> 2. **Onchain agent:** An agent connected to a blockchain wallet or smart account and capable of submitting transactions under defined permissions. [Learn more: Virtuals](https://os.virtuals.io/acp/concepts)

> 3. **Agent identity:** The persistent identifiers describing an agent, such as its wallet, profile, email, card, credentials, or optional token. [Learn more: Virtuals](https://os.virtuals.io/acp/concepts)

> 4. **Agent wallet:** A blockchain account used by agent software to hold assets, sign messages, and submit transactions. [Learn more: Virtuals EconomyOS](https://os.virtuals.io/)

> 5. **Agent policy:** Rules restricting the transactions, contracts, amounts, or actions available to an agent. [Learn more: ERC-4337](https://eips.ethereum.org/EIPS/eip-4337)

> 6. **Session key:** A temporary or restricted key authorized to perform a defined set of smart-account operations. [Learn more: ERC-4337](https://eips.ethereum.org/EIPS/eip-4337)

> 7. **Human-in-the-loop:** A system requiring human review or authorization for selected agent actions. [Learn more: NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework)

> 8. **Tool:** An external function an agent can invoke, such as reading pool data, querying an oracle, or submitting a transaction. [Learn more: Virtuals ACP SDK](https://os.virtuals.io/acp/sdk/getting-started)

> 9. **Worker:** A specialized agent component responsible for a subset of tasks or functions. [Learn more: Virtuals G.A.M.E.](https://whitepaper.virtuals.io/builders-hub/game-framework)

> 10. **Keeper:** Automation that submits transactions when predefined protocol-maintenance conditions occur. **Based NUT:** A keeper can execute approved pool or liquidity operations. [Learn more: Chainlink Automation](https://docs.chain.link/chainlink-automation)

> 11. **Sentinel:** Automation focused on monitoring conditions, producing alerts, and triggering authorized protective responses. **Based NUT:** Peanut sentinel is the proposed monitoring agent for pools, oracles, vaults, and ecosystem contracts. [Learn more: OpenZeppelin Monitor](https://docs.openzeppelin.com/defender/module/monitor)

> 12. **Virtuals AI agent:** An agent registered within Virtuals infrastructure with a persistent identity and optional wallet, services, commerce functions, compute, or token. [Learn more: EconomyOS](https://os.virtuals.io/)

> 13. **EconomyOS:** Virtuals infrastructure providing agent identity, capital, commerce, and compute components. [Learn more: EconomyOS](https://os.virtuals.io/)

> 14. **ACP / Agent Commerce Protocol:** A framework for onchain commercial interactions between agents, including jobs, roles, escrow, deliverables, and settlement. **Based NUT:** Peanutoshi can use ACP as an agent-commerce layer while maintaining separate NUT-related services or liquidity. [Learn more: ACP](https://os.virtuals.io/acp/overview)

> 15. **Agent offering:** A published service with defined pricing, requirements, and expected deliverables. [Learn more: ACP concepts](https://os.virtuals.io/acp/concepts)

> 16. **Agent resource:** A read-only endpoint exposed by an agent for other agents to query. **Based NUT:** A Peanut sentinel resource could publish NUT market or protocol-state data. [Learn more: ACP concepts](https://os.virtuals.io/acp/concepts)

> 17. **ACP job:** An onchain contract representing one commercial engagement between a client and provider. [Learn more: ACP concepts](https://os.virtuals.io/acp/concepts)

> 18. **Client agent:** The agent requesting or purchasing work in an ACP job. [Learn more: ACP concepts](https://os.virtuals.io/acp/concepts)

> 19. **Provider agent:** The agent delivering work in an ACP job. [Learn more: ACP concepts](https://os.virtuals.io/acp/concepts)

> 20. **Evaluator agent:** The agent authorized to approve or reject an ACP deliverable. [Learn more: ACP concepts](https://os.virtuals.io/acp/concepts)

> 21. **Agent escrow:** Funds held by a job contract until its completion, rejection, or expiry rules are satisfied. [Learn more: ACP concepts](https://os.virtuals.io/acp/concepts)

> 22. **Agent token:** A token associated with an agent’s identity, services, access, incentives, governance, or market. **Based NUT:** An agent token may connect to NUT through pools, service payments, or other explicit contracts. [Learn more: EconomyOS](https://os.virtuals.io/)

> 23. **G.A.M.E.:** A Virtuals agent framework organized around agents, goals, workers, and executable functions. [Learn more: Virtuals G.A.M.E.](https://whitepaper.virtuals.io/builders-hub/game-framework)

> 24. **x402:** A machine-payment pattern using HTTP `402 Payment Required` semantics to request and settle payments for digital services. **Based NUT:** Peanutoshi inference or API services can expose x402 payment flows independently of NUT-holder allowances. [Learn more: Coinbase x402](https://docs.cdp.coinbase.com/x402/docs/welcome)

> 25. **Agent-token bridge:** A Based NUT design term for liquidity connecting an agent token to VIRTUAL and separately to NUT. It describes a market route rather than a redemption guarantee. [Learn more: Virtuals](https://os.virtuals.io/)

***

### Game Theory, Incentives, and Flywheels

> 1. **Game theory:** The study of decisions where each participant’s outcome depends partly on the actions of other participants. [Learn more: Stanford Encyclopedia](https://plato.stanford.edu/entries/game-theory/)

> 2. **Game theory mechanics:** Protocol rules that influence participant choices, including rewards, penalties, fees, voting, lockups, bonds, and reputation. **Based NUT:** NUT pools, SNUT fees, bonding curves, NFTs, and agent services each introduce distinct strategic rules. [Learn more: Stanford Encyclopedia](https://plato.stanford.edu/entries/game-theory/)

> 3. **Mechanism design:** Construction of rules intended to produce specified outcomes from participants acting according to their own incentives. [Learn more: Nobel Prize](https://www.nobelprize.org/prizes/economic-sciences/2007/popular-information/)

> 4. **Incentive compatibility:** A condition where following the intended rules is consistent with a participant’s own incentives. [Learn more: Nobel Prize](https://www.nobelprize.org/prizes/economic-sciences/2007/popular-information/)

> 5. **Coordination game:** A situation where participants receive benefits from selecting compatible actions, standards, pools, or strategies. **Based NUT:** A canonical NUT pool functions as a coordination reference. [Learn more: Stanford Encyclopedia](https://plato.stanford.edu/entries/game-theory/)

> 6. **Credible commitment:** A commitment made enforceable through code, collateral, timelocks, multisigs, or restricted authority. [Learn more: OpenZeppelin TimelockController](https://docs.openzeppelin.com/contracts/5.x/access-control#delayed_operation)

> 7. **Economic security:** Use of bonds, collateral, penalties, or loss exposure to assign an economic cost to prohibited behavior. [Learn more: Ethereum proof of stake](https://ethereum.org/developers/docs/consensus-mechanisms/pos/)

> 8. **Bond:** Capital posted as assurance that an actor will satisfy specified obligations. [Learn more: Ethereum staking](https://ethereum.org/staking/)

> 9. **Slashing:** Confiscation of bonded capital according to predefined violation rules. [Learn more: Ethereum](https://ethereum.org/developers/docs/consensus-mechanisms/pos/rewards-and-penalties/)

> 10. **Reflexivity:** A feedback relationship where market beliefs affect prices and prices affect subsequent beliefs or actions. **Based NUT:** NUT-linked prices, NAV calculations, burns, and liquidity activity can interact reflexively. [Learn more: Reflexivity](https://www.investopedia.com/terms/r/reflexivity.asp)

> 11. **Sybil attack:** One actor using multiple identities or wallets to appear as several independent participants. [Learn more: Ethereum](https://ethereum.org/developers/docs/consensus-mechanisms/pos/attack-and-defense/)

> 12. **Sybil resistance:** Rules that make duplication of identities costly, ineffective, or detectable. [Learn more: Ethereum](https://ethereum.org/developers/docs/consensus-mechanisms/pos/attack-and-defense/)

> 13. **Principal-agent problem:** A situation where the incentives of an agent, manager, curator, or operator differ from those of the participants whose assets or interests it manages. [Learn more: Stanford Encyclopedia](https://plato.stanford.edu/entries/principal-agent/)

> 14. **Moral hazard:** A situation where an actor changes its behavior because another participant bears part of the resulting cost. [Learn more: Federal Reserve](https://www.federalreserve.gov/boarddocs/speeches/2002/20020412/default.htm)

> 15. **Free-rider problem:** A situation where participants receive benefits from a shared system without contributing proportionally to its operation. [Learn more: Britannica](https://www.britannica.com/topic/free-riding)

> 16. **Gauge:** A smart contract or allocation mechanism directing token emissions toward a selected pool. **Based NUT:** Aerodrome gauges can direct AERO emissions toward eligible NUT pools. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 17. **Gauge vote:** A governance vote assigning emission weight to a gauge. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 18. **Voting incentive / bribe:** A reward offered to participants who direct gauge votes toward a specified pool. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 19. **Flywheel:** A descriptive systems term for a feedback loop in which one activity creates conditions that support continued activity. [Learn more: Feedback systems](https://en.wikipedia.org/wiki/Feedback)

> 20. **Liquidity flywheel:** A descriptive mechanism where trading generates fees or incentives, liquidity responds, and subsequent trading occurs through the resulting liquidity. **Based NUT:** NUT markets connect trading, liquidity provision, and routing across several venues. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 21. **DeFi burn flywheel:** A descriptive mechanism where protocol activity funds token purchases or burns, altering token supply or accessible circulation; subsequent activity determines whether the process repeats. [Learn more: Ethereum issuance](https://ethereum.org/roadmap/merge/issuance/)

> 22. **Buyback flywheel:** A feedback structure in which protocol revenue funds token purchases and continued protocol activity supplies future revenue. [Learn more: Token Terminal](https://tokenterminal.com/resources/metrics)

> 23. **Burn flywheel:** A feedback structure expressed as:

> `activity → fee collection → buyback → burn or sink → changed supply conditions → subsequent activity`

> **Based NUT:** SNUT transaction fees include a buyback-and-sink allocation. No price outcome is implied by the definition. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 24. **Recursive burn flywheel:** A burn flywheel where activity in one token affects another token or position, which then becomes an input to later activity. **Based NUT:** SNUT, NUT rewards, NUT sinks, and NUT-linked liquidity form the project’s recursive burn model. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 25. **Revenue flywheel:** A feedback structure where service or protocol usage generates revenue that funds continued operations, services, liquidity, or distribution. **Based NUT:** Peanutoshi services can form a revenue layer separate from token transfers. [Learn more: Token Terminal](https://tokenterminal.com/resources/metrics)

> 26. **Regenerative flywheel:** A project-design term for repeatedly routing productive activity into the resources used to maintain the system. **Based NUT:** Regenerative tokenomics refers to routing fees or service activity into liquidity, reserves, agents, or infrastructure. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 27. **Flywheel input:** An activity or resource entering a feedback loop, such as users, trades, fees, or service revenue. [Learn more: Feedback systems](https://en.wikipedia.org/wiki/Feedback)

> 28. **Flywheel output:** The measurable result produced by a feedback loop, such as liquidity, token sinks, rewards, or treasury assets. [Learn more: Feedback systems](https://en.wikipedia.org/wiki/Feedback)

> 29. **Flywheel leakage:** A descriptive term for value leaving a feedback loop through gas, external fees, taxes, operating costs, arbitrage, or asset transfers. [Learn more: LVR paper](https://arxiv.org/abs/2208.06046)

> 30. **Negative flywheel / death spiral:** A feedback loop where one decline causes conditions that reinforce further decline. [Learn more: Feedback systems](https://en.wikipedia.org/wiki/Positive_feedback)

***

### Exchange Architectures

#### Uniswap v2

> 1. **Uniswap v2:** A two-token, full-range constant-product AMM. LP ownership is represented by fungible ERC-20 LP tokens. **Based NUT:** NUT and SNUT have Uniswap v2 markets. [Learn more: Uniswap v2 whitepaper](https://docs.uniswap.org/whitepaper.pdf)

> 2. **Uniswap v2 pair:** A contract holding two token reserves and executing constant-product swaps. [Learn more: Uniswap v2](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 3. **Uniswap v2 LP token:** A fungible ERC-20 representing proportional ownership of a v2 pair. [Learn more: Uniswap v2](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

> 4. **Cumulative price:** A running value maintained by a v2 pair and usable for time-weighted price calculations. [Learn more: Uniswap v2 oracles](https://docs.uniswap.org/contracts/v2/concepts/core-concepts/oracles)

#### Uniswap v3

> 1. **Uniswap v3:** A concentrated-liquidity AMM where LPs select active price ranges. **Based NUT:** NUT’s genesis pool uses Uniswap v3. [Learn more: Uniswap v3](https://developers.uniswap.org/docs/get-started/concepts/liquidity-providers/concentrated-liquidity)

> 2. **Tick:** A discrete price boundary used by concentrated-liquidity pools. [Learn more: Uniswap](https://docs.uniswap.org/concepts/protocol/concentrated-liquidity)

> 3. **Tick spacing:** The permitted interval between initialized ticks for a pool configuration. [Learn more: Uniswap factory](https://docs.uniswap.org/contracts/v3/reference/core/UniswapV3Factory#enablefeeamount)

> 4. **Liquidity range:** The lower and upper price boundaries selected for a concentrated position. [Learn more: Uniswap](https://docs.uniswap.org/concepts/protocol/concentrated-liquidity)

> 5. **In-range position:** A concentrated position whose interval contains the current price. [Learn more: Uniswap](https://support.uniswap.org/hc/en-us/articles/32514988932877-What-does-out-of-range-liquidity-mean)

> 6. **Range order:** Concentrated liquidity configured to exchange one asset for another as price crosses a selected interval. [Learn more: Uniswap range orders](https://docs.uniswap.org/concepts/protocol/range-orders)

#### Uniswap v4

> 1. **Uniswap v4:** A concentrated-liquidity architecture using a shared PoolManager, flash accounting, native ETH support, flexible fees, and hooks. **Based NUT:** New NUT pools can use v4 independently of existing v2 and v3 pools. [Learn more: Uniswap v4](https://docs.uniswap.org/contracts/v4/overview)

> 2. **Singleton:** An architecture where one principal contract manages many pools. [Learn more: Uniswap PoolManager](https://docs.uniswap.org/contracts/v4/concepts/PoolManager)

> 3. **PoolManager:** The principal Uniswap v4 contract coordinating pool state, accounting, and settlement. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v4/concepts/PoolManager)

> 4. **Hook:** External logic attached to a v4 pool and invoked around specified pool operations. [Learn more: Uniswap hooks](https://developers.uniswap.org/docs/get-started/concepts/hooks)

> 5. **Before-swap hook:** Hook logic executed before a swap. [Learn more: Uniswap hooks](https://developers.uniswap.org/docs/get-started/concepts/hooks)

> 6. **After-swap hook:** Hook logic executed after a swap. [Learn more: Uniswap hooks](https://developers.uniswap.org/docs/get-started/concepts/hooks)

> 7. **Dynamic-fee hook:** A hook that calculates or updates swap fees according to custom logic. [Learn more: Uniswap dynamic fees](https://docs.uniswap.org/contracts/v4/concepts/dynamic-fees)

> 8. **Custom accounting:** v4 hook logic that modifies token deltas or settlement behavior around pool operations. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v4/concepts/custom-accounting)

> 9. **Flash accounting:** Settlement based on net token deltas across operations rather than transferring tokens after every internal action. [Learn more: Uniswap](https://docs.uniswap.org/contracts/v4/concepts/flash-accounting)

> 10. **Hook association:** The hook selected when a v4 pool is created. A pool’s hook address is part of its pool identity. [Learn more: Uniswap hooks](https://developers.uniswap.org/docs/get-started/concepts/hooks)

#### Balancer v2

> 1. **Balancer v2:** A programmable AMM architecture centered on a shared Vault and supporting weighted, stable, managed, and composable pools. **Based NUT:** pNUT is a Balancer v2 weighted pool. [Learn more: Balancer v2](https://docs.balancer.fi/partner-onboarding/balancer-v2/v2-overview.html)

> 2. **Balancer v2 Vault:** The shared contract holding pool assets and coordinating swaps and liquidity operations. [Learn more: Balancer Vault](https://docs.balancer.fi/concepts/vault/)

> 3. **Batch swap:** A single transaction executing swaps through multiple Balancer pools. [Learn more: Balancer swaps](https://docs.balancer.fi/concepts/vault/swaps.html)

> 4. **Internal balance:** Balancer Vault accounting that records user balances internally and can reduce external token transfers. [Learn more: Balancer](https://docs.balancer.fi/concepts/vault/internal-user-balances.html)

#### Balancer v3

> 1. **Balancer v3:** A separate Balancer architecture with a redesigned Vault, custom pools, hooks, routers, and yield-bearing-token support. **Based NUT:** A Balancer v3 NUT pool would be a separate deployment from the existing v2 pNUT pool. [Learn more: Balancer v3](https://docs.balancer.fi/partner-onboarding/balancer-v3/v3-overview.html)

> 2. **Balancer v3 Vault:** The accounting and settlement layer shared by Balancer v3 pools. [Learn more: Balancer Vault](https://docs.balancer.fi/concepts/vault/)

> 3. **Balancer hook:** External logic invoked around configured swaps or liquidity operations. [Learn more: Balancer hooks](https://docs.balancer.fi/concepts/core-concepts/hooks.html)

> 4. **Rate provider:** A contract reporting the exchange rate between a tokenized position and its referenced underlying asset. [Learn more: Balancer rate providers](https://docs.balancer.fi/concepts/core-concepts/rate-providers.html)

> 5. **Custom pool:** A Balancer v3 pool implementing specialized pricing or accounting logic. [Learn more: Balancer custom pools](https://docs.balancer.fi/developer-reference/contracts/custom-pools.html)

#### reCLAMM

> 1. **reCLAMM:** A Balancer v3 pool design with a concentrated liquidity range that gradually readjusts according to configured parameters. LP ownership is represented by fungible BPTs. **Based NUT:** A reCLAMM pool can form a separate NUT liquidity venue. [Learn more: Balancer reCLAMM](https://medium.com/balancer-protocol/introducing-reclamms-self-readjusting-trustless-passive-lping-for-clamms-b5528429588e)

> 2. **Readjusting range:** A concentrated liquidity interval that shifts according to a reCLAMM pool’s parameters. [Learn more: Balancer reCLAMM](https://medium.com/balancer-protocol/unpacking-reclamm-attributes-trustless-1c23af247e3b)

> 3. **Centeredness margin:** A reCLAMM parameter specifying how far the pool price can move from its range center before adjustment begins. [Learn more: Balancer reCLAMM](https://medium.com/balancer-protocol/unpacking-reclamm-attributes-trustless-1c23af247e3b)

> 4. **Daily price shift exponent:** A reCLAMM parameter involved in determining the rate at which the range changes. [Learn more: Balancer reCLAMM](https://medium.com/balancer-protocol/unpacking-reclamm-attributes-trustless-1c23af247e3b)

#### Aerodrome

> 1. **Aerodrome:** A Base-native DEX combining constant-product and concentrated-liquidity markets with gauge-directed incentives. **Based NUT:** NUT, SNUT, SALT, and other ecosystem assets use Aerodrome markets. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 2. **AERO:** Aerodrome’s liquid ERC-20 incentive token. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 3. **veAERO:** An ERC-721 position representing locked AERO and associated voting power. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 4. **Epoch:** Aerodrome’s recurring seven-day voting, emissions, and accounting period. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 5. **Gauge staking:** Depositing eligible liquidity positions into a gauge to receive directed AERO emissions. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 6. **Voting reward:** Pool revenue and deposited voting incentives allocated to eligible veAERO voters. [Learn more: Aerodrome](https://aerodrome.finance/docs)

> 7. **Slipstream:** Aerodrome’s concentrated-liquidity AMM system. **Based NUT:** A NUT Slipstream pool is separate from NUT’s classic Aerodrome pools. [Learn more: Aerodrome](https://aerodrome.finance/docs)

***

### Protocol Controls, Security, and Bridges

> 1. **Owner:** The address holding primary ownership authority over a contract. [Learn more: OpenZeppelin Ownable](https://docs.openzeppelin.com/contracts/5.x/access-control#ownership-and-ownable)

> 2. **Role-based access control:** Assignment of contract permissions through named roles. [Learn more: OpenZeppelin AccessControl](https://docs.openzeppelin.com/contracts/5.x/access-control#role-based-access-control)

> 3. **Multisig:** A smart account requiring a configured number of authorized signatures to execute transactions. [Learn more: Safe](https://docs.safe.global/advanced/smart-account-concepts)

> 4. **Signing threshold:** The number of multisig approvals required for execution. [Learn more: Safe](https://docs.safe.global/advanced/smart-account-concepts)

> 5. **Timelock:** A contract-enforced delay between scheduling and executing an operation. [Learn more: OpenZeppelin](https://docs.openzeppelin.com/contracts/5.x/access-control#delayed_operation)

> 6. **Immutable contract:** A contract whose deployed bytecode cannot be replaced. External configuration and dependencies can still exist. [Learn more: Ethereum smart contracts](https://ethereum.org/developers/docs/smart-contracts/)

> 7. **Upgradeable contract:** A system designed so its active implementation can be replaced while retaining an address or state. [Learn more: OpenZeppelin upgrades](https://docs.openzeppelin.com/upgrades-plugins/proxies)

> 8. **Proxy contract:** A contract that delegates execution to another implementation contract. [Learn more: OpenZeppelin](https://docs.openzeppelin.com/upgrades-plugins/proxies)

> 9. **Implementation contract:** The contract containing logic used by a proxy. [Learn more: OpenZeppelin](https://docs.openzeppelin.com/upgrades-plugins/proxies)

> 10. **Pause function:** Contract logic that temporarily disables selected operations. [Learn more: OpenZeppelin Pausable](https://docs.openzeppelin.com/contracts/5.x/api/utils#Pausable)

> 11. **Ownership renouncement:** Removal or transfer of the primary owner role. It does not automatically remove other roles, proxy permissions, or external controls. [Learn more: OpenZeppelin Ownable](https://docs.openzeppelin.com/contracts/5.x/access-control#ownership-and-ownable)

> 12. **Approval:** Authorization allowing another address or contract to spend tokens. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 13. **Allowance:** The remaining quantity a spender is authorized to transfer from a token owner. [Learn more: ERC-20](https://eips.ethereum.org/EIPS/eip-20)

> 14. **Unlimited approval:** An allowance set to a value intended to avoid repeated approvals. [Learn more: MetaMask](https://support.metamask.io/stay-safe/protect-yourself/what-is-a-token-approval/)

> 15. **Permit:** Signature-based token approval without requiring a separate onchain approval transaction. [Learn more: ERC-2612](https://eips.ethereum.org/EIPS/eip-2612)

> 16. **Smart-contract risk:** The possibility that contract code, configuration, permissions, or interactions produce unintended results. [Learn more: Ethereum security](https://ethereum.org/developers/docs/smart-contracts/security/)

> 17. **Dependency risk:** Risk inherited from external tokens, pools, bridges, oracles, routers, vaults, or agents. **Based NUT:** Nested NUT positions inherit dependencies from each underlying contract. [Learn more: OWASP Smart Contract Security](https://scs.owasp.org/)

> 18. **Composability risk:** The possibility that a lower-level protocol change or failure affects higher-level positions built from it. **Based NUT:** pNUT and LP-token metapools are composable positions. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 19. **Rug pull:** Unauthorized or misleading extraction of liquidity or protocol assets by a privileged party. [Learn more: Chainalysis](https://www.chainalysis.com/blog/crypto-rug-pulls-2021/)

> 20. **Bridge:** Infrastructure for transferring messages or representing assets across blockchains. [Learn more: Ethereum bridges](https://ethereum.org/bridges/)

> 21. **Canonical bridge:** A bridge recognized as part of a chain’s standard protocol infrastructure. **Based NUT:** Base’s standard bridge connects Ethereum and Base. [Learn more: Base](https://docs.base.org/base-chain/specs/protocol/bridging/bridges)

> 22. **Lock-and-mint bridge:** A bridge model where assets are locked on one chain and representations are minted on another. [Learn more: Base bridges](https://docs.base.org/base-chain/specs/protocol/bridging/bridges)

> 23. **Burn-and-release bridge:** A bridge model where representations are burned on one chain and corresponding assets are released on another. [Learn more: Base bridges](https://docs.base.org/base-chain/specs/protocol/bridging/bridges)

> 24. **WETH:** An ERC-20 representation of ETH. **Based NUT:** WETH is the paired asset in NUT’s genesis Uniswap pool. [Learn more: Ethereum](https://ethereum.org/wrapped-eth/)

> 25. **cbBTC:** A Coinbase-issued tokenized representation of bitcoin on supported chains. **Based NUT:** cbBTC appears in NUT-related pools and the pNUT basket. [Learn more: Coinbase](https://www.coinbase.com/cbbtc)

> 26. **cbETH:** A Coinbase liquid-staking token representing a position associated with staked ETH. **Based NUT:** cbETH is a pNUT pool component. [Learn more: Coinbase](https://www.coinbase.com/cbeth)

> 27. **USDC:** A fiat-referenced ERC-20 stablecoin issued by Circle. **Based NUT:** SALT has an external SALT/USDC market. [Learn more: Circle](https://www.circle.com/usdc)

> 28. **Base:** An Ethereum Layer 2 rollup network. **Based NUT:** Based NUT contracts and principal markets are deployed on Base. [Learn more: Base](https://docs.base.org/base-chain/specs/protocol/overview)

***

### Based NUT Ecosystem Terms

> 1. **BASED NUT:** An experimental DeFi and memefi ecosystem on Base containing NUT, SNUT, pNUT, bonding-curve assets, NFT layers, liquidity markets, and AI-agent concepts. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 2. **NUT:** The ecosystem’s central ERC-20 token and principal economic reference asset. Its verified contract is `0xb8DE15Fb529d98C93C749De63c749D48D25A30DF`. [Learn more: BaseScan](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df)

> 3. **One-NUT supply:** NUT has a total supply of one whole displayed token. [Learn more: NUT contract](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df)

> 4. **NUT divisibility:** NUT uses 18 decimals, so the one whole-token supply consists of `10^18` transferable raw units. [Learn more: NUT contract](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df#code)

> 5. **NUT total supply:** The one whole NUT reported by `totalSupply()`. The verified ABI contains standard transfer and approval functions but no public burn method. [Learn more: NUT ABI](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df#code)

> 6. **NUT accessible supply:** The portion of the one NUT supply controlled by addresses capable of transferring it. `accessible NUT = total NUT − inaccessible NUT` . [Learn more: NUT holders](https://basescan.org/token/0xb8de15fb529d98c93c749de63c749d48d25a30df#balances)

> 7. **NUT FDV:** Because NUT has one whole token as its maximum supply, its FDV is numerically equal to the price of one whole NUT. Circulating market capitalization can differ if circulating supply is below one. [Learn more: NUT BaseScan](https://basescan.org/token/0xb8de15fb529d98c93c749de63c749d48d25a30df)

> 8. **NUT genesis pool:** The original NUT/WETH Uniswap v3 pool used to initialize the NUT market. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 9. **NUT genesis liquidity:** The initial one-sided NUT liquidity deposited into the genesis pool. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 10. **NUT economic burn:** Transfer of NUT to a conventional dead address, reducing accessible supply without changing the verified token contract’s `totalSupply`. [Learn more: NUT contract](https://basescan.org/address/0xb8de15fb529d98c93c749de63c749d48d25a30df#code)

> 11. **NUT canonical pool:** The pool designated as the primary NUT market and historical price reference. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 12. **NUT oracle network:** The collection of NUT markets and observations used to compare NUT prices across venues. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 13. **SNUT:** A Based NUT ERC-20 reward-position token with a stated maximum supply of 100,000 and nine decimals. Its contract address is `0xAC130701aa31c284c36609E2489f150F419AD7AD`. [Learn more: BaseScan](https://basescan.org/token/0xAC130701aa31c284c36609E2489f150F419AD7AD)

> 14. **SNUT transaction fee:** The Based NUT FAQ describes a 6% transfer fee divided into four 1.5% allocations for liquidity, management, buyback-and-sink activity, and rewards. Contract settings and exemptions determine execution. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 15. **SNUT reward position:** A qualifying SNUT balance associated with NUT reward distributions under SNUT’s distributor and exclusion rules. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 16. **SNUT auto-liquidity:** The SNUT fee allocation identified for liquidity operations. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 17. **SNUT buyback:** Contract activity using accumulated assets to purchase SNUT from a market. [Learn more: SNUT BaseScan](https://basescan.org/token/0xAC130701aa31c284c36609E2489f150F419AD7AD)

> 18. **SNUT buyback-and-sink:** Purchased SNUT transferred to the conventional dead address. This reduces accessible SNUT supply but does not necessarily reduce `totalSupply`. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 19. **SNUT circulating supply:** SNUT supply excluding balances treated as inaccessible under the selected calculation method. [Learn more: SNUT BaseScan](https://basescan.org/token/0xAC130701aa31c284c36609E2489f150F419AD7AD)

> 20. **pNUT:** The BPT representing ownership of Based NUT’s Balancer v2 weighted pool. [Learn more: Balancer pool](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000000019e)

> 21. **pNUT basket:** The pool containing cbETH, cbBTC, NUT, and SNUT with 25% normalized weights in its Balancer invariant. Current balances and current market-value proportions change with pool activity and asset prices. [Learn more: Balancer pool](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000000019e)

> 22. **pNUT NAV:** The estimated current value of the assets redeemable through the pool divided by outstanding pNUT BPT supply. `pNUT NAV = pool asset value ÷ pNUT supply` . [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 23. **pNUT issuance:** Creation of pNUT BPT shares when assets are added to the Balancer pool. [Learn more: Balancer liquidity](https://docs.balancer.fi/concepts/vault/add-remove-liquidity.html)

> 24. **pNUT redemption:** Destruction of pNUT BPT shares in exchange for underlying pool assets according to Balancer exit rules. [Learn more: Balancer liquidity](https://docs.balancer.fi/concepts/vault/add-remove-liquidity.html)

> 25. **pNUT price drift:** A difference between a separately quoted pNUT market price and calculated pNUT NAV. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 26. **pNUT underlying transfer-fee exposure:** The transfer behavior introduced by SNUT being one of the assets inside pNUT. [Learn more: Uniswap token fees](https://support.uniswap.org/hc/en-us/articles/18673568523789-What-is-a-token-fee)

> 27. **SALT:** A Based NUT child token issued through a Mint Club discrete bonding curve using NUT as its base asset. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 28. **NUTINO:** A Based NUT child token issued through a Mint Club discrete bonding curve using NUT as its base asset. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 29. **NUT-backed child token:** A token redeemable through its bonding curve for NUT according to the deployed curve steps and royalties. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 30. **Nested NFT:** A Based NUT NFT whose minting, reserve, redemption, or ecosystem relationship incorporates NUT. [Learn more: Mint Club NFT](https://docs.mint.club/create/nft)

> 31. **NUT-redeemable NFT:** An NFT burnable under its contract rules in exchange for NUT held by its curve or reserve mechanism. [Learn more: Mint Club](https://docs.mint.club/mintburn/burning)

> 32. **NUT Army NFTs:** Based NUT NFT collections representing roles or factions in the Great Nut War narrative. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 33. **Meta-DEX / NUTDEX:** A Based NUT framework connecting AMMs, bonding curves, LP-token pools, NFT markets, vaults, routing, and agent systems. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 34. **NUT-denominated economy:** An ecosystem where token prices, reserves, services, or accounting relationships are expressed relative to NUT. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 35. **NUT orbit:** The project-defined network of tokens, NFTs, pools, LP tokens, vault shares, and agents connected to NUT through reserves, liquidity, or services. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 36. **Palm Grove:** A Based NUT term for the SNUT-LP metapool and related LP-token market structure. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 37. **Palm Grove metapool:** A higher-level market holding tokens that represent lower-level SNUT liquidity positions. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 38. **LP-NAV:** The estimated value of an LP token’s redeemable underlying assets divided by outstanding LP-token supply. [Learn more: Balancer BPTs](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 39. **Economic recursion:** The placement of a tokenized position inside another pool, vault, collateral system, or agent economy. **Based NUT:** NUT can enter a curve; its child token or LP position can then enter another liquidity layer. [Learn more: Balancer composability](https://docs.balancer.fi/concepts/core-concepts/balancer-pool-tokens.html)

> 40. **Peanutoshi Nutkamoto:** The Based NUT AI-agent identity and ecosystem interface. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 41. **Peanut sentinel:** A proposed Based NUT agent for monitoring pools, oracles, liquidity, taxes, vaults, and protocol state. [Learn more: Virtuals ACP](https://os.virtuals.io/acp/overview)

> 42. **Sentinel alert:** A notification generated when a monitored condition crosses a configured threshold. [Learn more: OpenZeppelin Monitor](https://docs.openzeppelin.com/defender/module/monitor)

> 43. **Sentinel action:** A transaction or operation submitted by the sentinel under its assigned permissions. [Learn more: Chainlink Automation](https://docs.chain.link/chainlink-automation)

> 44. **Sentinel guardrail:** A permission, spending limit, allowlist, or policy constraining sentinel actions. [Learn more: ERC-4337](https://eips.ethereum.org/EIPS/eip-4337)

> 45. **NUT agent service:** An AI or automation service whose access, settlement, or accounting connects to NUT. [Learn more: Virtuals ACP](https://os.virtuals.io/acp/overview)

> 46. **Agent-token orbit:** An agent token connected to NUT through explicit liquidity, payments, fees, or reserves. [Learn more: Virtuals EconomyOS](https://os.virtuals.io/)

> 47. **VIRTUAL-to-NUT route:** A liquidity route connecting an agent token or VIRTUAL market to NUT through one or more pools. [Learn more: Uniswap routing](https://docs.uniswap.org/contracts/v3/concepts/advanced-topics/routing)

> 48. **NUT liquidity flywheel:** The project-defined feedback structure connecting NUT trading, pool fees, liquidity provision, and subsequent trading activity. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 49. **SNUT fee flywheel:** The project-defined flow from SNUT transfers to fee allocations for liquidity, operations, buybacks, and rewards. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 50. **SNUT sink flywheel:** The project-defined flow from SNUT transfer activity to buybacks and dead-address transfers. `SNUT activity → fee allocation → SNUT buyback → SNUT sink` . [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 51. **Nested-token flywheel:** A project-defined flow where NUT is deposited into child-token curves and child-token activity produces further NUT-denominated transactions. [Learn more: Mint Club](https://docs.mint.club/learn/bonding)

> 52. **Agent-service flywheel:** A project-defined flow where agent usage generates service revenue or activity that supports continued agent operation. [Learn more: Virtuals ACP](https://os.virtuals.io/acp/overview)

> 53. **pNUT basket flywheel:** A project-defined flow connecting basket deposits, pNUT share issuance, pNUT liquidity, redemptions, and arbitrage. [Learn more: Balancer pool](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000000019e)

> 54. **Regenerative tokenomics:** The Based NUT design objective of routing protocol or service activity into liquidity, reserves, agents, infrastructure, or ecosystem operations. [Learn more: Based NUT FAQ](https://liquidity-six.vercel.app/faq)

> 55. **Please nut responsibly:** The Based NUT warning that its tokens and products are experimental memefi and do not promise intrinsic value, financial returns, or safety. [Learn more: Based NUT](https://docs.basednut.com/)

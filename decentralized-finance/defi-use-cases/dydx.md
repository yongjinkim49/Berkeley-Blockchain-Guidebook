# dYdX

**Introduction:**&#x20;

dYdX is a decentralized exchange built on the Ethereum which delivers financial instruments perpetuals, margin and spot trading (which was on Layer 1 of Ethereum and is now winded down), as well as lending and borrowing. dYdX services traders with off-chain order books with on-chain settlement and enables them to short-sell tokens, increase exposure with leverage, or earn interest on token deposits. dYdX utilizes StarkWare’s Layer 2 for the elimination of trusting a centralized exchange which can simultaneously support the security/transparency of a decentralized exchange along with the speed/usability of a centralized exchange.&#x20;

dYdX started with the Layer 1 product (Solo) in July 2017 and provided decentralized services in lending, borrowing, and margin trading on Ethereum. In February 2021, dYdX launched a closed alpha for its new Layer 2 cross-margined Perpetuals product built on StarkWare’s StarkEx scalability engine. In April 2021, its Layer 2 product was launched to the public.&#x20;

In August 2021, dYdX announced the dYdX Foundation to pave way for building the infrastructure for truly open markets. The dYdX Foundation deploys governance smart contracts and issues DYDX governance token. As the foundation intends to develop the growth of its Layer 2 ecosystem and governance, dYdX Trading’s core development team aims to spend its future time focused on, amongst other things, decentralizing the order book and matching engine components of the dYdX Layer 2 Protocol.&#x20;

**What does it offer:**

The dYdX platform was traditionally divided into 2 layers offering DeFi products with differing characteristics: Margin and Perpetual. Spot trading and margin trading (i.e. leveraged trading) **were** originally on Layer 1 of Ethereum as a trading platform but now is to be deprecated since November 1st of 2021. It is notable that at the time of closure, dYdX’s trading volume from perpetual (to be explained below) accounted for around 99% of all trades on dYdX.&#x20;

Perpetual non-custodial trading is supported on a Layer 2 blockchain system. This is like a type of derivative trading similar to trading products like BTC futures. A crypto perpetual contract has no fixed date specified for the exchange. In other words, you can hold a perpetual contract ”perpetually”. The main advantage of trading perpetual over futures is you are not stuck with a loss if the trade goes against you. Margined leverage trading for perpetual contracts is also possible.

{% file src="../../.gitbook/assets/perpetual_futures_contract.PNG" %}

Trades are processed off-chain and submitted validity proofs to the Ethereum chain, this is called ZK Rollups ( Zero-Knowledge rollups) - Layer 2 solution of Ethereum powered by Starkware. Basically, ZK-rollups has the following features:

* Validating speed is higher since the state is updated after off-chain validation.&#x20;
* Secure and decentralized features remain since the data is stored on the Ethereum blockchain.&#x20;
* Lower gas fees and trading fees are preferred.&#x20;
* Starkware does not publish all transaction details on-chain; therefore, the privacy of traders is granted.&#x20;

Perpetual powered by Starkware offers a trading product having features, including leverage up to 25x / cross-margin and off-chain order-book / only accept USDC as collateral/front-running prevention.&#x20;

Portfolio management service is also provided for traders to monitor trade activity where one can also claim trading rewards and fee discounts based on respective trading volumes.

{% file src="../../.gitbook/assets/hedgies.PNG" %}

Note that dYdX also launched its Hedgies NFT series. This series is a collection of 4,200 unique collectible avatars represented as NFTs based on Ethereum. On February 1, 2022, a free mint took place in a tiered distribution for governance voters, traders, and the greater crypto community. During this time, 2,443 Hedgies were minted. The remaining Hedgies will be distributed to traders on the dYdX exchange over the following two years.&#x20;

**Updates**&#x20;

dYdX announced (June 22, 2022) that its V4 will be developed as a standalone blockchain based on the Cosmos SDK and Tendermint Proof-of-stake consensus protocol. dYdX states that V4 will feature a fully decentralized, off-chain, orderbook, and matching engine capable of scaling to orders of magnitude more throughput than any blockchain can support. It is to be developed as a standalone blockchain based on Tendermint consensus and built using Cosmos SDK.&#x20;

Cosmos is a technology that makes it relatively easy to create a standalone blockchain with robust cross-chain interoperability. Its chains are based on the Tendermint PoS and is characterized by high throughput, decentralization, and customization. Each Cosmos chain traditionally has its own validators and Layer 1 staking token.

Off-chain, decentralized, order book + matching: The fundamental problem with every L1 or L2 we could develop is that none can handle even close to the throughput needed to run a first class order book and matching engine. For reference, the existing dYdX product processes about 10 trades per second and 1,000 order places/cancellations per second, with the goal to scale up orders of magnitude higher.

dYdX considered pivoting to developing another trading model (e.g., AMM or RFQ system), but decided that an order book-based protocol was critical to the trading experience that could meet the demands and tastes of institutions and professional traders. They also state that they were not satisfied with existing off-chain order book systems that either did not include matching (huge problems with front-running and trade collisions) or were based on centralized matching (there can be no central systems in dYdX V4). This led dYdX to go with building a decentralized off-chain network to run the order book.&#x20;

This is where Cosmos came into the picture for dYdX. One benefit of developing a blockchain dedicated to dYdX V4 is that it offers full customizability over how the blockchain itself works, as well as the jobs that validators perform.&#x20;

In dYdX V4, each validator runs an in-memory order book that is never committed to consensus. Orders/cancellations will propagate through the network similar to how it happens for normal blockchain transactions. This ensures that orders/cancellations will always make way through the network. The order book that each validator stores is eventually consistent with one another. Orders will be matched together by the network in real-time. The resulting trades are then committed on-chain on each block.&#x20;

This allows dYdX V4 to have extremely high throughput for the order book while remaining decentralized. Also, dYdX proposes that that traders would not pay gas fees to trade, but rather pay fees based on trades executed similar to dYdX V3 and centralized exchanges. These fees accrue to validators and their stakes.&#x20;

dYdX V4 is stated to be a fully sovereign blockchain (i.e. the chain is not reliant on external blockchains). This may become a good platform for the dYdX community to continue to build in a vertically integrated way with the protocol token holders having full control of the system.

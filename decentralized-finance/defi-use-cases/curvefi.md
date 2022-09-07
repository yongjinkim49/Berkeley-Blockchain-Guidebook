# Curvefi

**Introduction**&#x20;

By 2020, stablecoins were becoming increasingly popular. However, they had obvious problems with price stability and liquidity, which was particularly problematic for arbitrage. This is why Michael Egorov published his white paper, StableSwap – an efficient mechanism for Stablecoin liquidity, setting the first milestone for what would become the Curve.fi protocol.&#x20;

On the supply side, Curve.fi offers liquidity pools through a DAPP based on the Ethereum blockchain. Stablecoins holders can use them as saving accounts and earn typically 25% APR. On the demand side, it offers a Uniswap-like automated exchange with very low price-slippage - typically 100 times smaller than the only current alternative, Uniswap.&#x20;

The protocol has been a huge success, with 100k active users, 64k token holders, and a total value locked in of $20 billion in April 2022, the largest at the time, despite several hacks, including one from January to June 2022. The stablecoin pools have also gained traction offering high liquidity and low fees (0.004%) because Curve uses its native token to reward liquidity providers instead of higher swap fees.

**How does it work**&#x20;

The concept of a market maker basically focuses on matching a buyer with a seller. In traditional markets, the asset price evolves according to supply/demand equilibrium. The centralized exchanges (Binance, Kraken) provide an order book, and the price is defined by a transaction between a seller and a buyer.&#x20;

Liquidity pools provide a solution to these problems of stability, liquidity, and the ability to sell without a counterparty (without necessarily having a seller or a buyer). Liquidity providers deposit several types of tokens in a liquidity pool, and receive passive income from traders using these tokens, and rewarding them for tying up their tokens. Liquidity pools are hence faster and more efficient than centralized exchanges.

{% file src="../../.gitbook/assets/curvefi_protocol.PNG" %}

At any time, liquidity providers can recover the share corresponding to the tokens they have tied up. However, they must beware of the risk of impermanent loss, which they can typically do by depositing two correlated tokens.&#x20;

In 2020, the only possibility to trade tokens for stablecoins was through Uniswap. They adjust prices using the following constraint: with x the quantity of token X, and y the quantity of token Y, x_y has to remain constant. Hence, whenever a trader will sell dx token X, he will get rewarded with dy tokens Y such as (x+dx)_(y-dy) = x\*y.&#x20;

However, while this method is very apt for assets like ETH and tokens, which display high price volatility, it is not very well working for something which is meant to be stable. The problem is that the price slippage is enormous, and one should provide enormous funds to keep good liquidity. Price slippage refers to the difference between the expected price of a trade and the price at which the trade is executed. Slippage can occur at any time but is most prevalent during periods of higher volatility when market orders are used. It can also occur when a large order is executed but there isn’t enough volume at the chosen price to maintain the current bid/ask spread.&#x20;

It is also possible to adjust prices in a way that keeps each pool price constant, assuming the underlying cryptocurrency price is constant. Hence, with x and y the quantities of tokens X and Y in the pool, the invariant becomes x + y. Yet, if this hypothesis of constant underlying price makes little sense when trading ETH or BTC, it is relevant when trading stablecoins. Thus, Curve.fi developers chose a mix of the two methods in building their own invariant.

{% file src="../../.gitbook/assets/Comparison of StableSwap invariant with Uniswap .PNG" %}

The price slippage is much smaller if compared to Uniswap constant-product invariant. Therefore, the Curve.fi invariant is a very useful feature for creating stablecoin-to-stablecoin liquidity.&#x20;

Finally, in 2021, the developers published a new white paper focusing on improving the Uniswap invariant, and not just focusing on stablecoins. This new method creates 5-10 times higher liquidity than the Uniswap invariant, as well as higher profits for liquidity providers. It relies on a mix of Uniswap and stableswap invariants.

{% file src="../../.gitbook/assets/Comparison_of_AMM_invariant.PNG" %}

The new invariant is chosen with regards to one currency in the pool that will be seen as the currency of reference, and with regards to an invariant D which is constant for the same curve in such a way that it is equal to the total deposits in the pool when it is in equilibrium. In order to quantify profits or losses, they chose the value of the constant-product invariant at the equilibrium point, which is obtained by solving equations in D. However, this new invariant is more sensitive to volatility than the uniswap one, and will thereby need more arbitragers.&#x20;

**Governance, token, and DAO**&#x20;

Curve.fi is associated with the CRV token. It is basically an ERC-20 token operating on the Curve DEX. CRV basically serves as the governance token on the exchange. In addition, the token is also used for offering rewards to liquidity providers.&#x20;

It arrives in August 2020. You will find below the breakdown as of 08/18/22 and the release schedule as of August 2022.

{% file src="../../.gitbook/assets/breakdown.PNG" %}

{% file src="../../.gitbook/assets/rekease_schedule.PNG" %}

In order to incentivize CRV token holders to keep their tokens, and thus reduce the selling pressure on the tokens, the developers have set up a locking system. Locking CRV tokens allows receiving vote-escrowed Curve (veCRV) tokens. The longer the token is locked, the more veCRV tokens the holder will receive in exchange. These veCRV tokens give access to four rewards.&#x20;

Firstly, they allow the platform to collect exchange fees, which are paid by the traders. When a trader makes a deal, he pays a fee, half of which goes to the liquidity providers, and a half to the veCRV token holders. They also give access to airdrops, such as the one Ellipsis is offering in 2021. They also increase the returns of the liquidity pool: a liquidity provider that holds veCRV tokens will receive a bonus. Finally, it gives the right to vote on the hiring of developers, as well as on the choice of blockchains and liquidity pools that will receive the next CRV tokens.&#x20;

We should add here that the second graph shows a significant proportion of tokens destined for the core team (roughly 30%). This was a surprise to the community, which is used to figures of around 10 to 15% in this type of project.

**Strategies**&#x20;

Let’s say there was a market for USDC and DAI. As we said previously, the price Uniswap shows for each token in any pooled market pair is based on the balance of each in the pool. So, if someone were to set up a USDC/DAI pool, they should deposit equal amounts of both. In a pool with only 2 USDC and 2 DAI it would offer a price of 1 USDC for 1 DAI. But then imagine that someone put in 1 DAI and took out 1 USDC. Then the pool would have 1 USDC and 3 DAI. An investor could make an easy $0.50 profit by putting in 1 USDC and receiving 1.5 DAI. That’s a 50% arbitrage profit, and that’s why liquidity matters. Hence, yield farmers are cryptocurrencies holders that put their assets to work.&#x20;

Curve.fi allows any user to create a market and earn trading fees from token swaps. Thanks to its high level of TVLs and the stability of the first version, which specialized in stablecoins, it has become a popular platform for liquidity providers, with returns of around 25% APR. The presence of stablecoins also protects investments in liquidity pools from declines in cryptocurrency prices. The downside of that is that if the prices of a crypto skyrocket, we won’t perform as well. Hence, this is a somewhat bearish strategy, hedging for big losses while decreasing the potential profits.&#x20;

Yet, as we mentioned previously, yield farming exposes to the risk of impermanent losses, which corresponds to the loss in asset values while they are stacked. To illustrate this phenomenon, let’s think of a Uniswap pool with ETH and DAI. To supply liquidity to a 50/50 pool, the LP has to provide an equal value of both tokens to the pool. For instance:

{% file src="../../.gitbook/assets/7.PNG" %}

However, if the investor had kept his 20 ETH, he would have earned 20\*$550 = $21,000. Thus, the impermanent loss here is $23.41, and will become a permanent loss if he chooses to withdraw his position after the arbitrage. To reduce the risk of impermanent loss, it is better to sell the farm in a pool containing correlated tokens, to focus only on the fees and reduce the risk of fluctuation in value.


# DAI: The Rise and Inevitable Fall:

### What is DAI?

The one-liner of DAI after creation is “Resistant to hyperinflation due to its low volatility, DAI offers economic freedom and opportunity to anyone, anywhere.”&#x20;

This reminds us of Terra. Right?&#x20;

Let’s dig first into what is DAI.&#x20;

When discussing DAI, two major concepts come into mind: MakerDAO and Maker Protocol.

MakerDAO is a decentralized autonomous organization founded in 2014 that runs as an open-source initiative on the Ethereum blockchain. People who own the project’s governance token, MKR, are in charge of running it from all over the world. Holders of MKR oversee the stability, openness, and effectiveness of Dai’s financial risks and the Maker Protocol through a system of scientific governance that includes Executive Voting and Governance Polling.

Maker Protocol is where users can make money, it is based on the Ethereum blockchain. The Dai stablecoin, Maker Collateral Vaults, Oracles, and Voting are the current components of the Maker Protocol. By using the voting power of MKR holders to determine important criteria (such as stability fees, collateral types/rates, etc.), MakerDAO controls the Maker Protocol.&#x20;

The MakerDAO project started operating in 2015 with developers from all across the world collaborating on the initial iterations of the code, architecture, and documentation. The initial MakerDAO formal white paper, which introduced the first DAI Stablecoin System, was released in December 2017. Today’s Maker Protocol, formerly known as the Dai Stablecoin System, now accepts any Ethereum-based asset as collateral that has been accepted by MKR holders, who also vote on appropriate Risk Parameters for each collateral item. Also, it is worthy to note that Multi-Collateral Dai (MCD) was released on November 18 of 2019, and along with its new features came a very important change in terminology: “Collateralized Debt Position (CDP)” was replaced with “Vault.”&#x20;

DAI is an algorithmic stablecoin issued by MakerDAO, an Ethereum-based protocol, that aims to maintain an exact ratio of one-to-one with the U.S. dollar. It is utilized as a means of lending and borrowing crypto assets without the need for an intermediary — creating a permissionless system with transparency and minimal restrictions.&#x20;

DAI maintains its stability, by locking other altcoins, mainly ETH, in smart contracts against US Dollar. The Maker protocol, the creators of DAI stablecoin, enables borrowers to lock ETH and other crypto assets, with the intention to collateralize them and mint new DAI in a loan format. A variety of cryptocurrencies, including ether (ETH), basic attention token (BAT), USD Coin (USDC), wrapped bitcoin (wBTC), compound (COMP), and many others, can be used as collateral by DAI. The Maker Protocol initially only accepted ether as collateral. However, the technology was modified in November 2019 to incorporate BAT and USDC, resulting in the multi-collateral DAI system that is in use today.



The motivation behind DAI is to act as:

1. A store of value
2. A medium of exchange
3. A unit of account
4. A standard of deferred payment

If DAI is to be acquired, some assets need to be collateralized. Collateral assets that are deposited into Maker Vaults on the Maker Protocol are used to generate, back, and maintain the stability of Dai. A digital item that MKR holders have chosen to accept into the Protocol is referred to as a collateral asset. The Maker Protocol takes any Ethereum-based asset that has been authorized by MKR holders as collateral to create Dai.&#x20;

Through the use of Maker Vaults, a type of smart contract, any acceptable collateral assets can be used to generate Dai. Users can utilize a variety of different user interfaces to access the Maker Protocol and create Vaults.

### Liquidation:



Any Maker Vault deemed too risky (according to criteria established by Maker Governance) is liquidated through automated Maker Protocol auctions, ensuring there is always enough collateral in the Maker Protocol to cover the value of all outstanding debt (the amount of Dai outstanding valued at the Target Price). The Liquidation Ratio is compared to the existing collateral-to-debt ratio of a Vault before the Protocol decides. Each type of vault has a unique liquidation ratio, which is decided by MKR voters based on the risk profile of the specific type of collateral asset.&#x20;

There are three main types of Auctions Mechanisms under MakerDAO:

1. Collateral Auction: The winning bidder pays Dai for collateral from a liquidated Vault. Dai received is used to cover the outstanding debt in the liquidated Vault.
2. Surplus Auction: The winning bidder pays MKR for surplus Dai from stability fees. The MKR received is burnt, thereby reducing the amount of MKR in circulation.
3. Debt Auction: The winning bidder pays Dai for MKR to cover the outstanding debt that Collateral Auctions haven’t been able to cover. MKR is minted by the system, thereby increasing the amount of MKR in circulation.&#x20;

It is important to note that the main mechanism is Collateral Auction.

### Risk Parameters:



The Key Risk Parameters for Maker Vaults are:

1. Debt Ceiling: The maximum amount of debt that can be issued using a particular type of collateral is known as a debt ceiling. Every type of collateral is given a Debt Ceiling by Maker Governance, which is used to guarantee that the Maker Protocol’s portfolio of collateral is sufficiently diversified. It is difficult to add to a collateral type’s debt after it reaches its debt ceiling unless some current users settle all or part of their vault debt.
2. Stability Fee: The Stability Fee is a percentage yield that is added annually to the amount of Dai that has been generated against the collateral of a Vault. Only Dai may be used to pay the charge, which is subsequently transmitted to the Maker Buffer.
3. Liquidation Ratio: The Liquidation Ratio is the minimum required collateralization level for each Vault type before it is considered undercollateralized and subject to liquidation. The Maker Protocol’s oracles provide the system with pricing data that is used to track Vaults for when their Liquidation Ratio is breached. Once breached, they are available for Liquidation. Each Vault type’s Liquidation Ratio is determined by a combination of the collateral’s risk profile and the Stability Fee. There may be multiple Vault types for each collateral, with varying Liquidation Ratios and Stability Fees. The Liquidation Ratio of a Vault is typically displayed on frontends that offer Vaults.

_LiquidationRatio = (CollateralAmount ∗ CollateralPrice) / GeneratedDai ∗ 100_

The maximum amount of DAI debt that a vault user can withdraw from their vault, given the value of their collateral stored in that vault, is limited by the Liquidation Ratio setting. In actuality, it specifies the minimal percentage of collateral required to sustain a specific DAI loan. A vault user’s vault may be liquidated if the proportion of their collateral to their debt falls below this level. Maker Governance can change the Liquidation Ratio for any individual vault type. Please take note that rather than applying to specific vaults, the Liquidation Ratio applies to all vaults built using a particular vault type as a whole.

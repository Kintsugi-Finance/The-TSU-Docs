# Vaults

## What is a Vault?

Vaults are investment instruments that employ a specific set of strategies for yield farming. They make use of automation to continually invest and reinvest deposited funds, which help to achieve high levels of compound interest. By using a Kintsugi vault to compound your gains, you save thousands of transactions with their associated gas costs, and precious personal time. Instead of manually harvesting and selling rewards, buying more tokens, and reinvesting that continuously, a vault does all that automatically at a high frequency.

Vaults are the core of the Kintsugi ecosystem. In a Kintsugi vault, you earn more of the asset you stake in it, regardless if this is an liquidity pool (LP) token or a single asset. For example, vaults where one can stake ETH-LINK LP will result in more ETH-LINK LP over time, effectively growing your share in the liquidity pool and thus allowing for more and more fees and rewards over time.

Despite the name 'Vault' suggests, user funds are never locked in any vault on Kintsugi. One could always withdraw from a vault at any moment in time. Kintsugi also does not own user funds staked in vaults. However, it is generally best to view vaults as investment tools to store funds for the medium to long term in order to have the effects of compounding really kick in.

When browsing the vaults on the platform, you will see the annual percentage yield (APY), which takes the frequent compounding into consideration compared to annual percentage rate (APR) which does not. You will also see daily interest percentages and the total amount invested in a vault by all users (TVL). Furthermore, one can see what underlying platform the vault is using as a source of revenue.

Each vault can either refer to a pair of tokens invested in liquidity pools, such as ETH-LINK LP tokens within the Arbitrum Chain ecosystem, or a single token invested in lending platforms or single stake reward pools. After depositing tokens to a vault, the user is supplied with vault specific wooTokens which represent their share in the vault. We will elaborate on wooTokens in the next section.

Anyone in the Cowmoonity can work together to build new strategies and submit them to the Kintsugi team for review. However, a new vault will not be accepted if the underlying platform does not adhere to the [beefy-safu-practices.md](../../safu-protocol/beefy-safu-practices.md "mention").

Summarizing, vaults can:

* Efficiently execute yield farming strategies.
* Compound rewards into the initially deposited token amount.
* Use any asset as liquidity.
* Provide one asset as collateral for another.
* Manage collateral at a safe level to mitigate liquidation.
* Put any asset to work to generate a yield.
* Reinvest earned profits.

Users can sit back and relax, and watch their investment grow!

## **What are wooTokens?**

A wooToken is an interest-bearing, tokenized proof of deposit that you will receive at the moment you deposit in a TSU vault. A wooToken is unique per vault, e.g. you get wooTSU tokens when depositing TSU into the TSU Native vault. One can view wooTokens as the receipt of your vault deposit.

{% hint style="info" %}
Kintsugi.Finance users should hold on tightly to their wooTokens and not sell or exchange it, since you would lose ownership of your staked vault assets if you did so!
{% endhint %}

## How do wooTokens earn interest?

Kintsugi's vaults automatically create more of your deposited asset in the form of compound interest. By holding wooTokens in your wallet, they are increasing in value against its corresponding vault asset. The number of wooTokens in your wallet will remain constant, but the quantity of the vault tokens they can be redeemed for increases. This is also the reason why wooTokens do not 1:1 match with the token amount initially deposited.

## How do I redeem wooTokens for the initially deposited tokens?

Whenever you want to withdraw the tokens that are staked for you in Kintsugi's vault, you simply initiate a withdrawal transaction to exchange them. The wooTokens are then taken from your wallet and burned, and your deposited assets plus yield will be given back to you.

## What are the advantages of the wooToken system?

Kintsugi's wooToken system has a few major advantages:

1. wooTokens allow any user to withdraw their fair share of deposited funds;
2. the system allows you to deposit the wooToken receipt to a cold or hardware wallet for ultimate safety;
3. your privacy is maintained, as you remain anonymous to Kintsugi. Your funds in the vault are not tied to the wallet address from which you made the deposit since the wooTokens are the only evidence of your share in the vault. Therefore, you could withdraw your share of funds from a different address if you moved your wooTokens to it;
4. wooTokens have tax benefits: since you're not selling off rewards, nor getting staking rewards direct to your address, you do not have taxable events when you have funds staked in a vault;
5. Lastly, wooTokens can be used as interest-bearing collateral.

## **How often do the vaults harvest their profits and reinvest?**

Vaults are normally harvested multiple times daily, and profits are automatically reinvested (compounded).&#x20;

## Why can't someone just do this themselves?

They could, but vaults help you save on personal time and transaction fees, maintain healthy collateral to debt ratios, self-optimize for the best possible yields, and automatically reinvest earnings. Attempting to do this manually would result in large inefficiencies. At Kintsugi we like to say: "Sit back and relax, the vault does all the work for you."

## **What is the vault fee structure?**

Most vaults have a performance fee structure, taking 4.5% of harvest rewards. This 3% fee on profits is split up: 1% is distributed back to $TSU stakers, 0.5% is allocated to the treasury, 0.5% is for the strategist that developed the vault and 0.5% for the one calling the harvest function. These fees are already built into the APY of each vault and daily rate. You do not need to calculate these yourself.

The performance fee on additional yield i.e. vault profits is largely distributed back to $TSU stakers and is the main source of Kintsugi.Finance's platform revenue. A part of it also funds the treasury which is used to further fund platform development and security and other initiatives. The performance fee was also implemented to promote community engagement and governance participation. A successful and engaged community is critical for our future growth, which in-turn rewards platform users even more.

Furthermore, some vaults have a withdrawal fee. The main purpose of this fee is to prevent possible exploits from bad-faith actors. Without the fee, somebody could deposit just before the harvest() function execution and withdraw straight after that event, taking a % of the gains generated by legitimate stakers. Withdrawal fees stay in the vault and are shared amongst vault funds.

## What is harvesting on deposit?

Many of Kintsugi's vaults "Harvest on Deposit". This means that when you deposit into the vault, you are also calling the harvest function of the vault's strategy. By calling the harvest function, you trigger the collection of pending farm rewards and compounding of those rewards back into the vault tokens for everyone.

Kintsugi does this so that it is impossible for malicious actors to steal yield, so a withdrawal fee is not required. This greatly benefits long-term investors.

Almost all of the vaults harvest on deposit. You can tell if a vault harvests on deposit if there is no withdrawal fee.

For depositing, and thus calling the harvest function, you will receive a reward in the form of WETH due to the harvest call fee.

## **Does the performance fee get taken out when I withdraw my funds?**

No, the performance fees are on profits and are taken every time someone calls the harvest() function.

## Does the vault page show the APY?

Yes. Our displayed APY values reflect the predicted rate earned on a vault in a year. This rate is determined by the underlying platform it uses, the strategy that it is interacting with at the time, the total amount of funds in the vault and also takes into account the effect of compounding. As a unique feature, we have also included all vault fees in the APY calculation. What you see is what you get!

## What risks do the vaults have?

Kintsugi vaults are audited, but this does not mean that a vault is entirely risk free. Below are some of the general vault risks:

* Assets deposited into the vault have no risk of decreasing in quantity but can decrease in monetary value.
* As with any smart contract, the ultimate risk is that an investor's funds can end up stolen or unable to be withdrawn. The team does take steps to quantify the security risks of smart contracts and will only interact with ones that meet a specific set of requirements after excessive testing to make sure the underlying platform does not contain so called 'rug-pull' functions. For a detailed breakdown of the steps Kintsugi takes before adding new vaults, please consult [kintsugi-safu-practices.md](../../safu-protocol/kintsugi-safu-practices.md "mention").

More detailed vault risks, or better yet, information on Kintsugi's vault safety expressed by the Kintsugi Safety Score can be found here: [Beefy Safety Score](../../safu-protocol/beefy-safety-score.md).

## **What are the different vaults?**

* **Money Market :** Utilizes lending platforms, such as Venus on BNB Chain or Scream on Fantom, to generate the highest possible yield for these coins (e.g. BUSD, BNB, LINK, DOT, DAI, USDT, ETH, or BTCB).
* **Native Token Farming :** Takes advantage of the high yield on popular farms by depositing another asset to earn, sell and compound profits of the native reward token.

## What will I get out when I make a vault withdrawal?

You will always withdraw the token type that you deposited, because at Kintsugi you earn what you stake. You will get the amount you deposited plus the yield generated (minus a potential vault withdrawal fee). In the case of LP token vaults, you may also chose to use Kintsugi's Zap feature to withdraw as one of the two tokens representing the LP.

## **How do LP vaults work?**

Liquidity pool (LP) vaults work by reinvesting the fees awarded to LP participants. In return for providing liquidity to the pool, many platforms reward investors with tokens. Our vaults regularly harvest these rewards, sell it, buy more of the LP’s underlying assets, and then reinvest to complete the cycle.

This compounds the rewards gained from a liquidity pool. Kintsugi.Finance creates strategies that automate this process, saving you time and gas fees in comparison to farming manually. This is all done for a tiny fee that is distributed back to those who stake in Kintsugi's governance pool or in the TSU Native Vault. A small percentage also goes to the Kintsugi Finance treasury.

## **How often are balances updated in the vaults?**

Pending rewards are not reflected in the balance until they are swapped for the initial deposited token. This can vary depending on the strategy running.

## **What’s your vault naming process?**

Each vault on the platform is named after the token that users can deposit in it. For example, the ETH-LINK LP vault uses ETH-LINK LP tokens for its investment strategy. A BTC vault uses the BTC token, etc.

Underneath the vault name, you can find the platform used for investing the token and farming its yields. For example, Uses: Venus means that that particular vault invests the token in Venus, a DeFi algorithmic money market and synthetic stablecoin protocol.


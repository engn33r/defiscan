---
chain: "Ethereum"
stage: 0
reasons: ["remove", "if none"]
risks: ["x", "x", "x", "x", "x"]
author: ["engn33r"]
submission_date: "2025-10-08"
publish_date: "2025-10-08"
update_date: "1970-01-01"
---

# Summary

Yearn Finance is a yield aggregator for DeFi, using automated vaults and strategies to allow depositors to maximize profits from yield farming while minimizing their exposure to underlying risks.

# Ratings

## Chain

Yearn is deployed to Ethereum and other EVM chains.

> Chain score: Low

## Upgradeability

In the upgradability section & risk we address bytecode upgrades and parameter changes that are permissioned.

We wrote a section explaining the Upgradeability Risk in our framework here: See http://defiscan.info/framework#upgradability

For some practical guidance follow this steps. It will help you in writing a nice report:

1. Run the [permission scanner](https://github.com/deficollective/permission-scanner)
2. Fill in all the permissioned functions in the table (`## Permissions`)
   - Remember: Each function with a permission needs to be considered when determining the risk on Upgradability
3. Get a mechanistic and precise understanding of each permissioned function
4. Assess impact for each function, look out for
   - loss/blocking of user funds
   - loss of unclaimed yield
   - change expected behavior significantly (blacklisting/kyc/fees/...)
5. Write the impact column based on your understanding
   - A good tip when writing the impact column below, think of least 2,3 sentences:
   1. First sentence: what it does technically, e.g "It assigns a new address to the owner variable"
   2. Second: what is the impact within the system, e.g "The owner is permissioned to raise fees"
   3. Third: Imagine faulty or malicious action, e.g "The malicious owner could raise fees to 100%, redirecting all future yield.
6. Summarise and abstract away technical details in this section here (`## Upgradeability`)

> Upgradeability score: Low/Medium/High

## Autonomy

See http://defiscan.info/framework#autonomy for more guidance.

> Autonomy score: Low/Medium/High

## Exit Window

See http://defiscan.info/framework#exit-window for more guidance.

> Exit Window score: Low/Medium/High

## Accessibility

See http://defiscan.info/framework#accessibility for more guidance.

> Accessibility score: Low/Medium/High

## Conclusion

Some text in form of:

The xyz protocol achieves High centralization risk scores for its Upgradeability, Autonomy and Exit Window dimensions. It thus ranks Stage 0.

The protocol could reach Stage 1 by ...

The project additionally could advance to Stage 2 if ...

# Reviewer's Notes

(Here, anything worth mentioning about what critical permissions you excluded from the scope or some elements that xyz protocol does in a unique way. If nothing seems relevant, just say that :)

⚠️ During our analysis, we identified ...

# Protocol Analysis

Here include the diagram. Please explain what the main contracts are doing within the diagram.

# Dependencies

Go into more detail of the oracle, bridge, or other dependency the defi protocol is using

# Governance

## Relevant Subsection

Here anything relevant to the governance, in this case it could be what you highlighted in "Upgrade Process"

## Security Council

New table with all the multisigs

| Name          | Account                                     | Type     | ≥ 7 signers | ≥ 51% threshold | ≥ 50% non-insider | Signers public |
| ------------- | ------------------------------------------- | -------- | ----------- | --------------- | ----------------- | -------------- |
| Team Multisig | [0x123](https://etherscan.io/address/0x123) | Multisig | ✅          | ❌              | ❌                | ✅             |

# Contracts & Permissions

## Contracts

| Contract Name | Address |
|--------------|--------------|
| YFI | 0x0bc529c00c6401aef6d220be8c6ea1667f6ad93e |
| veYFI | 0x90c1f9220d90d3966fbee24045edd73e1d588ad5 |
| TreasuryVault | 0x93A62dA5a14C80f265DAbC077fCEE437B1a0Efde |
| Protocol Address Provider | 0x775F09d6f3c8D2182DFA8bce8628acf51105653c |
| ReleaseRegistry | 0x0377b4daDDA86C89A0091772B79ba67d0E5F7198 |
| RoleManagerFactory | 0xca12459a931643BF28388c67639b3F352fe9e5Ce |
| Yearn V3.0.4 Vault | 0xd8063123BBA3B480569244AE66BFE72B6c84b00d |
| Yearn V3.0.4 Vault Factory | 0x770D0d1Fb036483Ed4AbB6d53c1C88fb277D812F |
| Yearn V3.0.4 TokenizedStrategy | 0xD377919FA87120584B21279a491F82D5265A139c |
| Yearn V3.0.3 Vault | 0xcA78AF7443f3F8FA0148b746Cb18FF67383CDF3f |
| Yearn V3.0.3 Vault Factory | 0x5577EdcB8A856582297CdBbB07055E6a6E38eb5f |
| Yearn V3.0.3 TokenizedStrategy | 0x254A93feff3BEeF9cA004E913bB5443754e8aB19 |
| Yearn V3.0.2 Vault | 0x1ab62413e0cf2eBEb73da7D40C70E7202ae14467 |
| Yearn V3.0.2 Vault Factory | 0x444045c5C13C246e117eD36437303cac8E250aB0 |
| Yearn V3.0.2 TokenizedStrategy | 0xBB51273D6c746910C7C06fe718f30c936170feD0 |
| Yearn V3.0.1 Vault | 0xDE992C652b266AE649FEC8048aFC35954Bee6145 |
| Yearn V3.0.1 Vault Factory | 0xE9E8C89c8Fc7E8b8F23425688eb68987231178e5 |
| Yearn V3.0.1 TokenizedStrategy | 0xDFC8cD9F2f2d306b7C0d109F005DF661E14f4ff2 |
| APROracle | 0x1981AD9F44F2EA9aDd2dC4AD7D075c102C70aF92 |
| CommonReportTrigger | 0xa045d4daea28ba7bfe234c96eaa03dafae85a147 |
| Yearn4626Router | 0x1112dbCF805682e828606f74AB717abf4b4FD8DE |
| RoleManager | 0xb3bd6B2E61753C311EFbCF0111f75D29706D9a41 |
| Registry v3 | 0xd40ecF29e001c76Dcc4cC0D9cd50520CE845B038 |
| Registry Legacy | 0xff31A1B020c868F6eA3f61Eb953344920EeCA3af |
| Accountant | 0x5A74Cb32D36f2f517DB6f7b0A0591e09b22cDE69 |
| RoboTreasury | 0x05f0357d5473de607f2220eC150E7a402041e38d |
| Dumper | 0x590Dd9399bB53f1085097399C3265C7137c1C4Cf |

## All Permission Owners

| Name | Account                                     | Type         |
| ---- | ------------------------------------------- | ------------ |
| Yearn Multisig | [0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52](https://etherscan.io/address/0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52) | Multisig 6/9 |
| Strategist Multisig | [0x16388463d60FFE0661Cf7F1f31a7D658aC790ff7](https://etherscan.io/address/0x16388463d60FFE0661Cf7F1f31a7D658aC790ff7) | Multisig 3/7 |
| Core Dev Multisig | [0x846e211e8ba920B353FB717631C015cf04061Cc9](https://etherscan.io/address/0x846e211e8ba920B353FB717631C015cf04061Cc9) | Multisig 2/8 |
| Role Manager | [0xb3bd6B2E61753C311EFbCF0111f75D29706D9a41](https://etherscan.io/address/0xb3bd6B2E61753C311EFbCF0111f75D29706D9a41) | Contract |
| TimelockGovernance | [0x026D4b8d693f6C446782c2C61ee357Ec561DFB61](https://etherscan.io/address/0x026D4b8d693f6C446782c2C61ee357Ec561DFB61) | Contract |

## Permissions

| Contract      | Function     | Impact                                                                                                                                                                                                                                                                                                                                     | Owner                   |
| ------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------- |
| YFI | mint | Callable by any minter address, this function mints new YFI tokens. Increasing the token supply can dilute existing token holders. A malicious minter address could mint a large number of YFI tokens, causing the token value to drop significantly and require the DAO to transition to a new token. | 0x0 |
| YFI | setGovernance | Callable by `governance`, this function performs a single step `governance` address change. The `governance` address is able to set minter addresses, which can mint an arbitrary number of new YFI tokens. A malicious `governance` address could adding their own minter address and then mint a large number of YFI tokens, causing the token value to drop significantly and require the DAO to transition to a new token. | TimelockGovernance |
| YFI | addMinter | Callable by `governance`, this function gives an address the ability to mint tokens. Setting a non-zero minter address will result in this address being able to mint an arbirary number of YFI tokens. A malicious minter address could mint a large number of YFI tokens, causing the token value to drop significantly and require the DAO to transition to a new token. | TimelockGovernance |
| YFI | removeMinter | Callable by `governance`, this function removes an address from the minters mapping, preventing this address from any further token minting. | TimelockGovernance |
| TreasuryVault | setOnesplit | Callable by `governance`, this function sets a new `onesplit` address, which is the RoboTreasury address. The `onesplit` address is used in `convert()` to withdraw non-core strategy tokens and deposit them into buckets. A malicious `onesplit` address could change the behavior of this function called in `onesplit` to something completely different. | Yearn Multisig |
| TreasuryVault | setRewards | Callable by `governance`, this function sets a new `rewards` address, which is the Curve Finance yDAI/yUSDC/yUSDT/yTUSD pool address. The `rewards` address is used in `convert()` to withdraw non-core strategy tokens and deposit them into buckets. A malicious `rewards` address could cause the `convert()` call to revert, causing a denial of service on that operation. | Yearn Multisig |
| TreasuryVault | setYGov | Callable by `governance`, this function sets a new `ygov` address, which is the contract 0xe2ba09069D25cE019814Ee5C7f195e60e34702fE. The `ygov` address would normally be used when calling `toVoters()`, but the current `ygov` address 0xe2ba09069D25cE019814Ee5C7f195e60e34702fE reverts when this function is called. Setting a new `ygov` address could result in calls to `toVoters()` not reverting as expected. | Yearn Multisig |
| TreasuryVault | setAuthorized | Callable by `governance`, this function sets an address to be authorized, which allows the address to call `convert()`. The `convert()` function moves tokens around the Yearn protocol. A malicious authorized address could move these tokens from an unexpected address or to an unexpected number of parts. | Yearn Multisig |
| TreasuryVault | revokeAuthorized | Callable by `governance`, this function removes an address from being authorized, which removes the ability for the address to call `convert()`. The `convert()` function moves tokens around the Yearn protocol. A malicious authorized address could move these tokens from an unexpected address or to an unexpected number of parts. | Yearn Multisig |
| TreasuryVault | setGovernance | Callable by `governance`, this function performs a single step `governance` address change. The `governance` address is able to withdraw tokens from the TreasuryVault. A malicious `governance` address could steal tokens from the treasury, although governance is already effectively the owner of these funds in TreasuryVault. | Yearn Multisig |
| TreasuryVault | toGovernance | Callable by `governance`, this function sends ERC20 tokens in the contract to the `governance` address. This removes tokens from the TreasuryVault contract and gives them to `governance`. A malicious `governance` address could steal tokens from the treasury, although governance is already effectively the owner of these funds in TreasuryVault. | Yearn Multisig |
| TreasuryVault | convert | Callable by any address authorized by `setAuthorized`, this function uses the RoboTreasury contract to withdraw non-core strategy tokens and deposit them into buckets. Currently only the Yearn Multisig is authorized. This function moves tokens around the Yearn protocol. A malicious authorized address could move these tokens from an unexpected address or to an unexpected number of parts. | Yearn Multisig |
| ReleaseRegistry | transferGovernance | Callable by `governance`, this function assigns a new address to the `pendingGovernance` variable, which is the first step to setting a new `governance` address. The `pendingGovernance` address is able to call `acceptGovernance()` to take over governance of the contract. | Yearn Multisig |
| ReleaseRegistry | acceptGovernance | Callable by `pendingGovernance`, this function set the `governance` variable to `pendingGovernance`, which is only callable after the governor called `transferGovernance()`. | Yearn Multisig |
| ReleaseRegistry | newRelease | Callable by `governance`, this function creates a new release by setting a new vaults factory and a new TokenizedStrategy, which the contract uses to maintain knowledge of the latest release. The vault factory and TokenizedStrategy are the core contract addresses used throughout the Yearn vaults system. A malicious `governance` address could create a malicious release with malicious contracts, which would make an user depositing into the newer vaults lose value. | Yearn Multisig |
| TokenizedStrategy v3.0.4 | report | Callable by keepers or `management`, this function harvests and records profits/losses for the strategy by calling the strategy's `harvestAndReport()` function. The function calculates profit/loss, handles performance fee collection, and manages the profit unlocking mechanism that controls how quickly profits are released to depositors. A malicious keeper could trigger reports at inappropriate times, potentially causing higher gas costs during expensive periods or missing optimal harvest opportunities, which could reduce overall strategy performance and depositor returns. | ['nonReentrant', 'onlyKeepers'] |
| TokenizedStrategy v3.0.4 | tend | Callable by keepers or `management`, this function allows maintenance operations on the strategy by calling the strategy's `tendThis()` function with the current loose balance. The tend function enables ongoing strategy management and rebalancing without changing the price per share, typically used for optimizing yield or managing positions. A malicious keeper could call `tend()` excessively, wasting gas and reducing net returns, or fail to call it when needed, missing optimization opportunities that could result in lower yields for depositors. | ['nonReentrant', 'onlyKeepers'] |
| TokenizedStrategy v3.0.4 | shutdownStrategy | Callable by `management` or `emergencyAdmin`, this function permanently disables new deposits into the strategy by setting the `shutdown` flag to true. Once shutdown, the strategy can only process withdrawals and emergency operations, making this a one-way irreversible action. A malicious `management` or `emergencyAdmin` could shut down a profitable strategy unnecessarily, preventing further deposits and potentially forcing premature liquidation, which could result in missed yield opportunities and potential losses for existing depositors during unfavorable market conditions. | Strategist Multisig |
| TokenizedStrategy v3.0.4 | emergencyWithdraw | Callable by `management` or `emergencyAdmin`, this function allows manual withdrawal of funds from the strategy's yield source by calling the strategy's `shutdownWithdraw()` function, but only after `shutdownStrategy()` is called to put the strategy in shutdown state. This provides a backup mechanism to recover funds during critical situations or protocol failures. A malicious `management` or `emergencyAdmin` could use this function to withdraw funds inappropriately after shutdown, potentially extracting value at suboptimal times or disrupting the normal withdrawal process, though the requirement for prior shutdown provides some protection against abuse. | Strategist Multisig |
| TokenizedStrategy v3.0.4 | setPendingManagement | Callable by `management`, this function performs the first step of a two-step `management` change, by setting the `pendingManagement` address which can then become the `management` by later calling `acceptManagement()`. The `management` address has full control over the strategy including fee settings, emergency powers, and governance parameters. A malicious `management` address could complete extract value through excessive fees, inappropriate emergency actions, or strategy mismanagement. | Strategist Multisig |
| TokenizedStrategy v3.0.4 | acceptManagement | Callable by `pendingManagement`, this function performs the second step of a two-step `management` change. The `management` address has full control over the strategy including fee settings, emergency powers, and governance parameters. A malicious `management` address could complete extract value through excessive fees, inappropriate emergency actions, or strategy mismanagement. | 0x0 |
| TokenizedStrategy v3.0.4 | setKeeper | Callable by `management`, this function sets a new `keeper` address. The `keeper` address can call `tend()` and `report()` functions on the strategy, which regularly update accounting, profits, and fees. A malicious `management` address could set a malicious or unreliable `keeper` address, which could then neglect critical strategy maintenance leading to missed yield opportunities, or conversely perform excessive operations that waste gas and reduce net returns for depositors. | Strategist Multisig |
| TokenizedStrategy v3.0.4 | setEmergencyAdmin | Callable by `management`, this function sets a new `emergencyAdmin` address. The `emergencyAdmin` address can call `shutdownStrategy()` and `emergencyWithdraw()` functions. The `emergencyAdmin` provides backup authority for critical emergency operations when management may not be available during crisis situations. A malicious management address could set a malicious `emergencyAdmin` that could then inappropriately shut down profitable strategies or extract funds during emergencies, potentially causing losses to depositors through premature liquidation or theft of strategy assets. | Strategist Multisig |
| TokenizedStrategy v3.0.4 | setPerformanceFee | Callable by `management`, this function updates the performance fee charged by the strategy, with a maximum fee of 50%. Performance fees are charged on profits generated by the strategy and represent a key revenue mechanism for strategy operators. A malicious management address could set the performance fee to the maximum 50% rate, significantly reducing depositor returns, or could repeatedly change fees to manipulate expected returns. | Strategist Multisig |
| TokenizedStrategy v3.0.4 | setPerformanceFeeRecipient | Callable by `management`, this function updates the address that receives performance fees collected by the strategy. Performance fees are automatically sent to this recipient address when profits are realized during strategy reporting. A malicious management address could redirect performance fees to a different address, effectively stealing fees that should go to the protocol or legitimate fee recipients, resulting in direct financial loss and undermining the intended fee distribution mechanism of the strategy. | Strategist Multisig |
| TokenizedStrategy v3.0.4 | setProfitMaxUnlockTime | Callable by `management`, this function updates the maximum time period over which strategy profits are unlocked and made available to depositors. This parameter controls the profit unlocking mechanism that prevents front-running and ensures fair distribution of gains over time. A malicious management address could set this to an extremely long time period, effectively locking profits for extended periods and preventing depositors from accessing their earned returns, or set it too short to enable MEV attacks and profit extraction by front-running depositors during strategy reports. | Strategist Multisig |
| AprOracle | transferGovernance | Callable by `governance`, this function performs a single step `governance` address change. The `governance` address is able to call `setOracle()` to change the APR oracle for a strategy. If the APR oracle is incorrectly set, the contract will report an inaccurate APR value. | Strategist Multisig |
| AprOracle | setOracle | Callable by `governance`, this function sets or changes the APR oracle address for a strategy. The `governance` address is able to call `setOracle()` to change the APR oracle for a strategy. If the APR oracle is incorrectly set, the contract will report an inaccurate APR value. | Strategist Multisig |
| CommonReportTrigger | transferGovernance | Callable by `governance`, this function performs a single step `governance` address change. The `governance` address is able to set base fees and base fee providers. A malicious governance address set higher than expected base fees to an incorrect fee provider, potentially disrupting strategy reporting for vaults. | Strategist Multisig |
| CommonReportTrigger | setCustomStrategyTrigger | Callable by strategy management, this function sets a custom trigger contract for a specific strategy's reporting logic. The custom trigger overrides the default CommonReportTrigger behavior for that strategy, but allows keepers to still read the trigger status from the CommonReportTrigger. A malicious strategy manager could set an inaccurate trigger that prevents the strategy from reporting when profitable or forces excessive reporting, leading to missing strategy actions. | Strategy Management |
| CommonReportTrigger | setCustomStrategyBaseFee | Callable by strategy management, this function sets a custom base fee threshold for when a specific strategy should report based on gas costs. This overrides the default acceptable base fee for that strategy. An inappropriately high base fee threshold could prevent strategy triggers, or setting too low of a base fee could cause excessive triggers during high gas periods, both reducing net yields for depositors. | Strategy Management |
| CommonReportTrigger | setCustomVaultTrigger | Callable by addresses with the REPORTING_MANAGER role on a vault, this function sets a custom trigger contract for a specific strategy within a vault. The custom trigger overrides default reporting logic at the vault-strategy level. A malicious reporting manager could configure inappropriate triggers that disrupt optimal reporting schedules, causing strategies to miss profitable harvest opportunities or waste gas on unprofitable reports, ultimately reducing vault performance. | REPORTING_MANAGER |
| CommonReportTrigger | setCustomVaultBaseFee | Callable by addresses with the REPORTING_MANAGER role on a vault, this function sets a custom base fee threshold for a specific strategy within a vault. This creates vault-specific gas cost thresholds for reporting decisions. A malicious reporting manager could set inappropriate base fee thresholds that either prevent necessary reporting during standard gas conditions or allow wasteful reporting during expensive gas periods, reducing the vault's overall profitability and depositor returns. | REPORTING_MANAGER |
| CommonReportTrigger | setBaseFeeProvider | Callable by `governance`, this function sets the address that provides current base fee information used for gas cost calculations in reporting decisions. The base fee provider is critical for determining when reporting is economically viable across all strategies and vaults. A malicious governance address could set a compromised provider that returns manipulated gas price data, leading to suboptimal reporting decisions system-wide and reduced overall protocol performance. | ['onlyGovernance'] |
| CommonReportTrigger | setAcceptableBaseFee | Callable by `governance`, this function sets the global default acceptable base fee threshold for determining when strategies should report. This threshold affects all strategies unless they have custom settings, balancing reporting frequency with gas costs. A malicious `governance` address could set the threshold inappropriately high, preventing most strategies from reporting during normal gas conditions, or too low, causing excessive reporting and high gas costs that significantly reduce depositor returns across the protocol. | ['onlyGovernance'] |
| RoleManager | transferGovernance | Callable by `governance`, this function performs the first step of a two-step `governance` change, by setting the `pendingGovernance` address which can then become the `governance` by later calling `acceptGovernance()`. The `governance` address is able to set position roles, position holders, default time for unlocking vault profits, create new vaults that are added to the Registry. Setting an incorrect or malicious governance address can result in incorrect values or inability to access these functions in this contract. | Yearn Multisig |
| RoleManager | acceptGovernance | Callable by `pendingGovernance`, this function performs the second step of a two-step `governance` change. The `governance` address is able to set position roles, position holders, default time for unlocking vault profits, create new vaults that are added to the Registry. Setting an incorrect or malicious governance address can result in incorrect values or inability to access these functions in this contract. | 0x0 |
| RoleManager | newVault | Callable by `DADDY`, this function deploys a new vault and endorses it in the Registry. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | Yearn Multisig |
| RoleManager | addNewVault | Callable by `DADDY`, this function adds a new vault to the RoleManager with the specified category and debt allocator. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | Yearn Multisig |
| RoleManager | updateDebtAllocator | Callable by `BRAIN`, this function updates a vault's debt allocator to a specified `_debtAllocator` address. The debt allocators manage debt and need to process reports. If the wrong address is set, the debt management and report processing may not happen reliably. | Strategist Multisig |
| RoleManager | updateKeeper | Callable by `BRAIN`, this function updates a vault's keeper to a specified `_keeper`. The keeper address is able to call `tend()` and `report()` on a strategy. If the wrong keeper address is set, `tend()` and `report()` may not be called reliably on the strategy. | Strategist Multisig |
| RoleManager | removeVault | Callable by `BRAIN`, this function removes a vault from the RoleManager without removing the endorsement in the Registry. | Strategist Multisig |
| RoleManager | removeRoles | Callable by `governance`, this function removes a specific role (or roles) for an address from a list of `_vaults`. The `governance` address is able to set position roles, position holders, default time for unlocking vault profits, create new vaults that are added to the Registry. Setting an incorrect or malicious governance address can result in incorrect values or inability to access these functions in this contract. | Yearn Multisig |
| RoleManager | setPositionRoles | Callable by `governance`, this function updates a position's roles. The `governance` address is able to set position roles, position holders, default time for unlocking vault profits, create new vaults that are added to the Registry. Setting an incorrect or malicious governance address can result in incorrect system configuration or inability to access these functions in this contract. | Yearn Multisig |
| RoleManager | setPositionHolder | Callable by `governance`, this function sets updates a position's holder. The `governance` address is able to set position roles, position holders, default time for unlocking vault profits, create new vaults that are added to the Registry. Setting an incorrect or malicious governance address can result in incorrect values or inability to access these functions in this contract. | Yearn Multisig |
| RoleManager | setDefaultProfitMaxUnlock | Callable by `governance`, this function sets the default time until profits are fully unlocked for new vaults. The `governance` address is able to set position roles, position holders, default time for unlocking vault profits, create new vaults that are added to the Registry. Setting an incorrect or malicious governance address can result in incorrect values or inability to access these functions in this contract. | Yearn Multisig |
| Registry v3 | transferGovernance | Callable by `governance`, this function performs a single step `governance` address change. The `governance` address is able to modify the endorser and tagger addresses. A malicious governance address could revoke permissions of existing endorser and tagger addresses and replace them with other malicious addresses. | Yearn Multisig |
| Registry v3 | newEndorsedVault | Callable by endorsers, this function deploys and adds a new vault to the `_endorsedVaults` array, calling Vault Factory in the process. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyEndorsers'] |
| Registry v3 | endorseMultiStrategyVault | Callable by endorsers, this function calls `endorseVault()` to endorse an already deployed multi strategy vault. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyEndorsers'] |
| Registry v3 | endorseSingleStrategyVault | Callable by endorsers, this function calls `endorseVault()` to endorse an already deployed multi strategy vault. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyEndorsers'] |
| Registry v3 | endorseVault | Callable by endorsers, this function adds an already deployed vault to the `_endorsedVaults` array. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyEndorsers'] |
| Registry v3 | tagVault | Callable by taggers, this function tags any vault or strategy with a specific string. This string is used to describe certain ratings or vault status. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyTaggers'] |
| Registry v3 | removeVault | Callable by endorsers, this function removes a vault from the `_endorsedVaults` array to make iterating over the array more efficient. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyEndorsers'] |
| Registry v3 | removeAsset | Callable by endorsers, this function removes an asset from the `assets` array to make iterating over the array more efficient. The Registry contract tracks vaults and assets endorsed by the Registry owner. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyEndorsers'] |
| Registry v3 | setEndorser | Callable by `governance`, this function adds or removes endorser privileges to an address. Endorsers can change the endorsed vaults stored in this Registry contract. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyGovernance'] |
| Registry v3 | setTagger | Callable by `governance`, this function adds or removes tagger privileges to an address. Taggers can change the string tags associated with vaults stored in this Registry contract. If inaccurate information is entered during this function call, the Registry will give inaccurate information about vaults and assets that are endorsed by the Registry owner. | ['onlyGovernance'] |
| Accountant | report | Callable by vaults added to this Accountant, this function handles profit/loss reporting from vaults to calculate and charge fees. The Accountant validates the report data and determines management fees, performance fees, and any refunds that should be provided back to the vault. A malicious vault could submit false profit reports to avoid fees or manipulate the fee calculation, potentially draining the protocol's fee revenue or causing incorrect fee assessments that harm depositors. | Vaults |
| Accountant | addVault | Callable by `vaultManager` or `feeManager`, this function adds a new vault to the Accountant's managed vault list. Once added, the vault will be subject to the Accountant's fee structure and reporting requirements. A malicious `feeManager` could add unauthorized or malicious vaults that could exploit the fee system, potentially abusing the funds calculations through false reporting. | ['onlyVaultOrFeeManager'] |
| Accountant | removeVault | Callable by `vaultManager` or `feeManager`, this function removes a vault from the Accountant's managed vault list. The vault will no longer be able to interact with this Accountant for fee-related operations. A malicious `feeManager` could remove legitimate vaults to prevent proper fee collection, or remove vaults to hide malicious activity and avoid oversight of vault operations. | ['onlyVaultOrFeeManager'] |
| Accountant | updateDefaultConfig | Callable by `feeManager`, this function updates the default fee configuration applied to all vaults that don't have a custom config set. These parameters directly affect how much fees are charged and when refunds are provided to all vaults using default settings. A malicious actor could set extremely high default fees to extract excessive value from vaults with the default configuration, or set inappropriate parameters that could lead to system instability or unfair fee distribution. | Strategist Multisig |
| Accountant | setCustomConfig | Callable by `feeManager`, this function sets vault-specific custom fee configuration that overrides default settings. Custom configurations can include specific management fees, performance fees, and other parameters unique to that vault. A malicious `feeManager` could set exploitative custom configurations with excessive fees for specific vaults, or create preferential treatment that unfairly benefits certain vaults at the expense of others. | Strategist Multisig |
| Accountant | removeCustomConfig | Callable by `feeManager`, this function removes vault-specific custom fee configuration, reverting the vault to default settings. This removes any special fee configurations or risk parameters that were configured for that vault, changing the fees to the default values. A malicious `feeManager` could remove beneficial custom configurations or remove protective custom parameters that were put in place for high-risk vaults. | Strategist Multisig |
| Accountant | turnOffHealthCheck | Callable by `feeManager`, this function skips a health check for a specific vault-and-strategy combination for one report. Health checks typically prevent operations when losses exceed thresholds or when vault states are abnormal. A malicious `feeManager` could disable health checks to allow bad debt to accrue or increase. | Strategist Multisig |
| Accountant | redeemUnderlying | Callable by `feeManager`, this function redeems underlying assets from a vault. It ensures proper accounting when fees are claimed in vault shares and received in underlying assets. A malicious `feeManager` may redeem a non-deal amount value, interfering with normal fee collection. | Strategist Multisig |
| Accountant | setMaxLoss | Callable by `feeManager`, this function sets the maximum acceptable loss threshold for vault operations. This parameter affects when health checks fail and when operations are prevented due to excessive losses. A malicious actor could set an inappropriately high max loss threshold to disable health checks on losses. | Strategist Multisig |
| Accountant | distribute | Callable by `feeManager` or `feeRecipient`, this function send accumulated fees to `feeRecipient`. | ['onlyFeeManagerOrRecipient'] |
| Accountant | setFutureFeeManager | Callable by `feeManager`, this function performs the first step of a two-step `feeManager` change, by setting the `futureFeeManager` address which can then become the `feeManager` by later calling `acceptFeeManager()`. The `feeManager` receives distributed rewards from strategies. If the `feeManager` is not set correctly, fees could get locked, redirected to an unintented address, or set to an inaccessible address (locking some functionality of this contract). | Strategist Multisig |
| Accountant | acceptFeeManager | Callable by `futureFeeManager`, this function performs the second step of a two-step `feeManager` change, by setting the `feeManager` address to the `futureFeeManager` value. The `feeManager` receives distributed rewards from strategies. If the `feeManager` is not set correctly, fees could get locked, redirected to an unintented address, or set to an inaccessible address (locking some functionality of this contract). | 0x0 |
| Accountant | setVaultManager | Callable by `feeManager`, this function performs a single step `vaultManager` address change. The `vaultManager` is able to add or remove vaults for the Accountant to charge fees for. If a vault is added or removed without authorization, fees can start or stop accruing in this Accountant unintentionally. | Strategist Multisig |
| Accountant | setFeeRecipient | Callable by `feeManager`, this function performs a single step `feeManager` address change. The `feeManager` receives distributed rewards from strategies. If the `feeManager` is not set correctly, fees could get locked, redirected to an unintented address, or set to an inaccessible address (locking some functionality of this contract). | Strategist Multisig |
| TimelockGovernance | setThisGovernance | Callable by `governance`, this function sets a new `governance` address and requires a time period to pass before the `governance` address update can be finalized. The `governance` address can set a new governor address for YFI, which in turn can set new YFI minter addresses. A malicious `governance` address can cause the minting of an arbitrary number of new YFI tokens. | Yearn Multisig |
| TimelockGovernance | setTargetGovernance | Callable by `governance`, this function sets a new `governance` address on the YFI contract by calling `setGovernance()` on the YFI contract. The `governance` address on the YFI contract can set new YFI minter addresses. A malicious `governance` address can cause the minting of an arbitrary number of new YFI tokens. | Yearn Multisig |
| Dumper | transferGovernance | Callable by `governance`, this function performs a single step `governance` address change. The `governance` address is able to configure contract parameters like `splitToken` and `auction`, but also sweep any leftover tokens in the contract. A malicious `governance` address could configure these addresses incorrectly and take any leftover tokens in the contract. | Strategist Multisig |
| Dumper | dumpToken | ... | ['onlyAllowed'] |
| Dumper | dumpTokens | ... | ['onlyAllowed'] |
| Dumper | claimToken | ... | ['onlyAllowed'] |
| Dumper | claimTokens | ... | ['onlyAllowed'] |
| Dumper | claimToken | ... | ['onlyAllowed'] |
| Dumper | sweep | Callable by `governance`, this function sends any leftover ERC20 tokens to the `governance` address. Although normally there are no tokens in this contract, this function is here to rescue any extra tokens. A malicious `governance` address could take any leftover tokens in the contract. | Strategist Multisig |
| Dumper | setSplitToken | Callable by `governance`, this function  | Strategist Multisig |
| Dumper | setAuction | Callable by `governance`, this function  | Strategist Multisig |
| Dumper | setAllowed | Callable by `governance`, this function  | Strategist Multisig |
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
| ProtocolAddress Provider | 0x775F09d6f3c8D2182DFA8bce8628acf51105653c |
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
| APR Oracle | 0x1981AD9F44F2EA9aDd2dC4AD7D075c102C70aF92 |
| Common Report Trigger | 0xa045d4daea28ba7bfe234c96eaa03dafae85a147 |
| Yearn 4626 Router | 0x1112dbCF805682e828606f74AB717abf4b4FD8DE |
| Registry | 0xd40ecF29e001c76Dcc4cC0D9cd50520CE845B038 |
| Registry | 0xff31A1B020c868F6eA3f61Eb953344920EeCA3af |
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
| TokenizedStrategy v3.0.4 | report | ... | ['nonReentrant', 'onlyKeepers'] |
| TokenizedStrategy v3.0.4 | tend | ... | ['nonReentrant', 'onlyKeepers'] |
| TokenizedStrategy v3.0.4 | shutdownStrategy | ... | ['onlyEmergencyAuthorized'] |
| TokenizedStrategy v3.0.4 | emergencyWithdraw | ... | ['nonReentrant', 'onlyEmergencyAuthorized'] |
| TokenizedStrategy v3.0.4 | setPendingManagement | ... | ['onlyManagement'] |
| TokenizedStrategy v3.0.4 | acceptManagement | ... | [] |
| TokenizedStrategy v3.0.4 | setKeeper | ... | Strategist Multisig and undocumented multisig 0x2bf2dDD9fD2Ad08DB9C2055a387EaD131cE93ECc |
| TokenizedStrategy v3.0.4 | setEmergencyAdmin | ... | ['onlyManagement'] |
| TokenizedStrategy v3.0.4 | setPerformanceFee | ... | ['onlyManagement'] |
| TokenizedStrategy v3.0.4 | setPerformanceFeeRecipient | ... | ['onlyManagement'] |
| TokenizedStrategy v3.0.4 | setProfitMaxUnlockTime | ... | ['onlyManagement'] |
| AprOracle | _checkGovernance | ... | [] |
| AprOracle | transferGovernance | ... | ['onlyGovernance'] |
| AprOracle | setOracle | ... | [] |
| CommonReportTrigger | _checkGovernance | ... | [] |
| CommonReportTrigger | transferGovernance | ... | ['onlyGovernance'] |
| CommonReportTrigger | setCustomStrategyTrigger | ... | [] |
| CommonReportTrigger | setCustomStrategyBaseFee | ... | [] |
| CommonReportTrigger | setCustomVaultTrigger | ... | [] |
| CommonReportTrigger | setCustomVaultBaseFee | ... | [] |
| CommonReportTrigger | setBaseFeeProvider | ... | ['onlyGovernance'] |
| CommonReportTrigger | setAcceptableBaseFee | ... | ['onlyGovernance'] |
| Yearn4626Router | withdrawDefault | ... | [] |
| Yearn4626Router | redeemDefault | ... | [] |
| Yearn4626Router | selfPermitIfNecessary | ... | [] |
| Yearn4626Router | selfPermitAllowedIfNecessary | ... | [] |
| Yearn4626Router | withdrawDefault | ... | [] |
| Yearn4626Router | redeemDefault | ... | [] |
| Yearn4626Router | selfPermitIfNecessary | ... | [] |
| Yearn4626Router | selfPermitAllowedIfNecessary | ... | [] |
| RoleManager | transferGovernance | ... | ['onlyGovernance'] |
| RoleManager | acceptGovernance | ... | [] |
| RoleManager | _checkGovernance | ... | [] |
| RoleManager | transferGovernance | ... | ['onlyGovernance'] |
| RoleManager | _isPositionHolder | ... | [] |
| RoleManager | newVault | ... | ['onlyPositionHolder'] |
| RoleManager | newVault | ... | ['onlyPositionHolder'] |
| RoleManager | newVault | ... | ['onlyPositionHolder'] |
| RoleManager | addNewVault | ... | ['onlyPositionHolder'] |
| RoleManager | addNewVault | ... | ['onlyPositionHolder'] |
| RoleManager | updateDebtAllocator | ... | ['onlyPositionHolder'] |
| RoleManager | updateDebtAllocator | ... | ['onlyPositionHolder'] |
| RoleManager | updateKeeper | ... | ['onlyPositionHolder'] |
| RoleManager | removeVault | ... | ['onlyPositionHolder'] |
| RoleManager | removeRoles | ... | ['onlyGovernance'] |
| RoleManager | setPositionRoles | ... | ['onlyGovernance'] |
| RoleManager | setPositionHolder | ... | ['onlyGovernance'] |
| RoleManager | setDefaultProfitMaxUnlock | ... | ['onlyGovernance'] |
| Registry | _checkGovernance | ... | [] |
| Registry | transferGovernance | ... | ['onlyGovernance'] |
| Registry | _isEndorser | ... | [] |
| Registry | _isTagger | ... | [] |
| Registry | newEndorsedVault | ... | ['onlyEndorsers'] |
| Registry | newEndorsedVault | ... | ['onlyEndorsers'] |
| Registry | endorseMultiStrategyVault | ... | ['onlyEndorsers'] |
| Registry | endorseSingleStrategyVault | ... | ['onlyEndorsers'] |
| Registry | endorseVault | ... | ['onlyEndorsers'] |
| Registry | tagVault | ... | ['onlyTaggers'] |
| Registry | removeVault | ... | ['onlyEndorsers'] |
| Registry | removeAsset | ... | ['onlyEndorsers'] |
| Registry | setEndorser | ... | ['onlyGovernance'] |
| Registry | setTagger | ... | ['onlyGovernance'] |
| Accountant | _checkFeeManager | ... | [] |
| Accountant | _checkVaultOrFeeManager | ... | [] |
| Accountant | _checkFeeManagerOrRecipient | ... | [] |
| Accountant | _checkVaultIsAdded | ... | [] |
| Accountant | report | ... | ['onlyAddedVaults'] |
| Accountant | addVault | ... | ['onlyVaultOrFeeManager'] |
| Accountant | removeVault | ... | ['onlyVaultOrFeeManager'] |
| Accountant | updateDefaultConfig | ... | Strategist Multisig |
| Accountant | setCustomConfig | ... | Strategist Multisig |
| Accountant | removeCustomConfig | ... | Strategist Multisig |
| Accountant | turnOffHealthCheck | ... | Strategist Multisig |
| Accountant | redeemUnderlying | ... | Strategist Multisig |
| Accountant | redeemUnderlying | ... | Strategist Multisig |
| Accountant | setMaxLoss | ... | Strategist Multisig |
| Accountant | distribute | Callable by `feeManager` or `feeRecipient`, this function send accumulated fees to `feeRecipient`. | ['onlyFeeManagerOrRecipient'] |
| Accountant | setFutureFeeManager | Callable by `feeManager`, this function performs the first step of a two-step `feeManager` change, by setting the `futureFeeManager` address which can then become the `feeManager` by later calling `acceptFeeManager()`. The `feeManager` receives distributed rewards from strategies. If the `feeManager` is not set correctly, fees could get locked, redirected to an unintented address, or set to an inaccessible address (locking some functionality of this contract). | Strategist Multisig |
| Accountant | acceptFeeManager | Callable by `futureFeeManager`, this function performs the second step of a two-step `feeManager` change, by setting the `feeManager` address to the `futureFeeManager` value. The `feeManager` receives distributed rewards from strategies. If the `feeManager` is not set correctly, fees could get locked, redirected to an unintented address, or set to an inaccessible address (locking some functionality of this contract). | 0x0 |
| Accountant | setVaultManager | Callable by `feeManager`, this function performs a single step `vaultManager` address change. The `vaultManager` is able to add or remove vaults for the Accountant to charge fees for. If a vault is added or removed without authorization, fees can start or stop accruing in this Accountant unintentionally. | Strategist Multisig |
| Accountant | setFeeRecipient | Callable by `feeManager`, this function performs a single step `feeManager` address change. The `feeManager` receives distributed rewards from strategies. If the `feeManager` is not set correctly, fees could get locked, redirected to an unintented address, or set to an inaccessible address (locking some functionality of this contract). | Strategist Multisig |
| TimelockGovernance | setThisGovernance | Callable by `governance`, this function sets a new `governance` address and requires a time period to pass before the `governance` address update can be finalized. The `governance` address can set a new governor address for YFI, which in turn can set new YFI minter addresses. A malicious `governance` address can cause the minting of an arbitrary number of new YFI tokens. | Yearn Multisig |
| TimelockGovernance | setTargetGovernance | Callable by `governance`, this function sets a new `governance` address on the YFI contract by calling `setGovernance()` on the YFI contract. The `governance` address on the YFI contract can set new YFI minter addresses. A malicious `governance` address can cause the minting of an arbitrary number of new YFI tokens. | Yearn Multisig |
| Dumper | dumpToken | ... | [onlyAllowed] |
| Dumper | dumpTokens | ... | [onlyAllowed] |
| Dumper | claimToken | ... | [onlyAllowed] |
| Dumper | claimTokens | ... | [onlyAllowed] |
| Dumper | setAllowed | ... | [onlyGovernance] |
| Dumper | sweep | ... | [onlyGovernance] |
| Dumper | setSplitToken | ... | [onlyGovernance] |
| Dumper | setAuction | ... | [onlyGovernance] |
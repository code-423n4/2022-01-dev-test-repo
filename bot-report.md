MrsHudson report

## Summary

| |Issue|Instances| Gas Savings
|-|:-|:-:|:-:|
| [[M-01](#m-01)] | Low Level Calls to Custom Addresses | 7| 0|
| [[M-02](#m-02)] | Possible Vulnerability to Fee-On-Transfer Accounting Issues | 21| 0|
| [[M-03](#m-03)] | Use `_safeMint()` instead of `_mint()` | 3| 0|
| [[M-04](#m-04)] | Potential Gas Griefing Due to Non-Handling of Return Data in External Calls | 3| 0|
| [[M-05](#m-05)] | Centralized Control Risk in Privileged Functions | 91| 0|
| [[M-06](#m-06)] | Potential DoS Risk with Loops Iterating Over Large State Arrays | 1| 0|
| [[M-07](#m-07)] | Potential Over/Underflow in `unchecked` Blocks | 3| 0|
| [[M-08](#m-08)] | Unchecked Return Values of the `approve()` Function | 15| 0|
| [[M-09](#m-09)] | Unchecked Return Values of `transfer()/transferFrom()` | 32| 0|
| [[M-10](#m-10)] | Unsafe use of `transfer()/transferFrom()` with IERC20 | 32| 0|
| [[M-11](#m-11)] | For ERC721 use `safeTransferFrom()` instead of `transferFrom()` | 5| 0|
| [[M-12](#m-12)] | Use `forceApprove/safeIncreaseAllowance` from SafeERC20 instead of `approve/safeApprove` | 12| 0|


 MrsHudson report ### Medium Risk Issues


### [M-01]<a name="m-01"></a> Low Level Calls to Custom Addresses
Contracts should avoid making low-level calls to custom addresses, especially if these calls are based on address parameters in the function. 
Such behavior can lead to unexpected execution of untrusted code. Instead, consider using Solidity's high-level function calls or contract interactions.

*There are 7 instance(s) of this issue:*

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

120: (success, result) = payable(_toft).call{value: msg.value}(_bytecode);


*GitHub* : [120](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/TapiocaWrapper.sol#L120)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

280: (bool sent, ) = to.call{value: amount}("");


*GitHub* : [280](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L280)

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFT.sol

380: (bool sent, ) = to.call{value: amount}("");


*GitHub* : [380](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L380)

```solidity
File: tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol

1045: (bool success, bytes memory returnData) = target.call(actionCalldata);


*GitHub* : [1045](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/MagnetarV2.sol#L1045)

```solidity
File: tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol

99: (bool success, bytes memory data) = token.call(


*GitHub* : [99](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Swapper/BaseSwapper.sol#L99)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

356: (bool successEmtptyApproval, ) = token.call(
369: (bool success, bytes memory data) = token.call(


*GitHub* : [356](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L356),[369](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L369)
### [M-02]<a name="m-02"></a> Possible Vulnerability to Fee-On-Transfer Accounting Issues
Contracts transfer funds using the `transferFrom()` function but do not verify that the actual number of tokens received matches the input amount to the transfer.
This could lead to accounting issues if the token involves a fee on transfer.
An attacker might exploit latent funds to get a free credit.
To prevent this, consider checking the balance before and after the transfer and use the difference as the actual amount received.

*There are 21 instance(s) of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol

160: yieldBox.transfer(from, address(swapper), assetId, supplyShare);


*GitHub* : [160](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol#L160)

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol

180: IERC20(address(this)).safeTransfer(
        to,
        lendParams.depositAmount
    );


*GitHub* : [180](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/modules/USDOMarketModule.sol#L180)

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol

191: IERC20(address(this)).safeTransfer(
        optionsData.from,
        optionsData.paymentTokenAmount
    );
240: IERC20(tapSendData.tapOftAddress).safeTransfer(from, tapAmount);


*GitHub* : [191](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L191),[240](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/modules/USDOOptionsModule.sol#L240)

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol

182: IERC20(address(this)).safeTransfer(leverageFor, amount);


*GitHub* : [182](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L182)

```solidity
File: tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol

148: IERC20(erc20).safeTransfer(msg.sender, _amount);


*GitHub* : [148](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L148)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol

165: IERC20(address(this)).safeTransfer(onBehalfOf, amount);


*GitHub* : [165](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L165)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol

172: IERC20(address(this)).safeTransfer(_from, borrowParams.amount);


*GitHub* : [172](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTMarketModule.sol#L172)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol

206: IERC20(address(this)).safeTransfer(
        optionsData.from,
        optionsData.paymentTokenAmount
    );
255: IERC20(tapSendData.tapOftAddress).safeTransfer(from, tapAmount);


*GitHub* : [206](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L206),[255](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTOptionsModule.sol#L255)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

197: IERC20(address(this)).safeTransfer(leverageFor, amount);


*GitHub* : [197](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L197)

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

42: tapToken.transferFrom(msg.sender, address(this), amount);
50: tapToken.transfer(msg.sender, amount);


*GitHub* : [42](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/LTap.sol#L42),[50](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/LTap.sol#L50)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

186: yieldBox.transfer(msg.sender, address(this), sglAssetID, sharesIn);
241: yieldBox.transfer(
address(this),
_to,
lockPosition.sglAssetID,
sharesOut
);


*GitHub* : [186](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L186),[241](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L241)

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

260: tapOFT.transferFrom(msg.sender, address(this), _amount);
448: rewardToken.safeTransferFrom(msg.sender, address(this), _amount);


*GitHub* : [260](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L260),[448](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L448)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

230: tOLP.transferFrom(msg.sender, address(this), _tOLPTokenID);
342: tOLP.transferFrom(address(this), otapOwner, oTAPPosition.tOLP);


*GitHub* : [230](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L230),[342](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L342)

```solidity
File: YieldBox/contracts/YieldBox.sol

144: IERC20(asset.contractAddress).safeTransferFrom(from, address(asset.strategy), amount);
209: wrappedNative.safeTransfer(address(asset.strategy), amount);


*GitHub* : [144](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/YieldBox/contracts/YieldBox.sol#L144),[209](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/YieldBox/contracts/YieldBox.sol#L209)
### [M-03]<a name="m-03"></a> Use `_safeMint()` instead of `_mint()`
`_mint()` is discouraged in favor of `_safeMint()` which ensures that the recipient is either an EOA or implements IERC721Receiver.
Both OpenZeppelin and solmate have versions of this function.

*There are 3 instance(s) of this issue:*

```solidity
File: YieldBox/contracts/YieldBox.sol

139: _mint(to, assetId, share);
178: _mint(to, assetId, 1);
204: _mint(to, assetId, share);


*GitHub* : [139](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/YieldBox/contracts/YieldBox.sol#L139),[178](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/YieldBox/contracts/YieldBox.sol#L178),[204](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/YieldBox/contracts/YieldBox.sol#L204)
### [M-04]<a name="m-04"></a> Potential Gas Griefing Due to Non-Handling of Return Data in External Calls
Due to the EVM architecture, return data (bool success,) has to be stored.
However, when 'out' and 'outsize' values are given (0,0), this storage disappears.
This can lead to potential gas griefing/theft issues, especially when dealing with external contracts.
```solidity
assembly {
success: = call(gas(), dest, amount, 0, 0)
}
require(success, "transfer failed");

```
Consider using a safe call pattern above to avoid these issues.
The following instances show the unsafe external call patterns found in the code.

*There are 3 instance(s) of this issue:*

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

280: (bool sent, ) = to.call{value: amount}("");


*GitHub* : [280](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L280)

```solidity
File: tapiocaz-audit/contracts/tOFT/BaseTOFT.sol

380: (bool sent, ) = to.call{value: amount}("");


*GitHub* : [380](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/BaseTOFT.sol#L380)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

356: (bool successEmtptyApproval, ) = token.call(


*GitHub* : [356](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L356)
### [M-05]<a name="m-05"></a> Centralized Control Risk in Privileged Functions
Functions that grant centralized privileges introduce a notable security risk.
Such functions can act as a single point of vulnerability, especially if they control critical operations or access to sensitive data.

If the account or entity with these privileges gets compromised, it could lead to the unauthorized alteration of the contract's state, asset misappropriation, or other malicious activities.
It's essential to implement robust access controls, frequent audits, and potentially decentralize critical functions to mitigate this risk.

*There are 91 instance(s) of this issue:*

```solidity
File: tapioca-bar-audit/contracts/usd0/BaseUSDO.sol

/// @audit `onlyOwner` modifier is used to restrict access
88: function setMaxFlashMintable(uint256 _val) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
96: function setFlashMintFee(uint256 _val) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
105: function setConservator(address _conservator) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
125: function setMinterStatus(address _for, bool _status) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
134: function setBurnerStatus(address _for, bool _status) external onlyOwner {


*GitHub* : [88](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L88),[96](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L96),[105](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L105),[125](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L125),[134](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/BaseUSDO.sol#L134)

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

/// @audit `onlyOwner` modifier is used to restrict access
256: function setBigBangEthMarketDebtRate(uint256 _rate) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
263: function setBigBangEthMarket(address _market) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
281: function setConservator(address _conservator) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
291: function setUsdoToken(address _usdoToken) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
317: function registerSingularityMasterContract(
address mcAddress,
IPenrose.ContractType contractType_
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
339: function registerBigBangMasterContract(
address mcAddress,
IPenrose.ContractType contractType_
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
362: function registerSingularity(
address mc,
bytes calldata data,
bool useCreate2
)
external
payable
onlyOwner
registeredSingularityMasterContract(mc)
returns (address _contract)
{
/// @audit `onlyOwner` modifier is used to restrict access
381: function addSingularity(
address mc,
address _contract
) external onlyOwner registeredSingularityMasterContract(mc) {
/// @audit `onlyOwner` modifier is used to restrict access
395: function registerBigBang(
address mc,
bytes calldata data,
bool useCreate2
)
external
payable
onlyOwner
registeredBigBangMasterContract(mc)
returns (address _contract)
{
/// @audit `onlyOwner` modifier is used to restrict access
414: function addBigBang(
address mc,
address _contract
) external onlyOwner registeredBigBangMasterContract(mc) {
/// @audit `onlyOwner` modifier is used to restrict access
424: function executeMarketFn(
address[] calldata mc,
bytes[] memory data,
bool forceSuccess
)
external
onlyOwner
notPaused
returns (bool[] memory success, bytes[] memory result)
{
/// @audit `onlyOwner` modifier is used to restrict access
455: function setFeeTo(address feeTo_) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
464: function setSwapper(ISwapper swapper, bool enable) external onlyOwner {


*GitHub* : [256](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L256),[263](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L263),[281](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L281),[291](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L291),[317](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L317),[339](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L339),[362](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L362),[381](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L381),[395](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L395),[414](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L414),[424](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L424),[455](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L455),[464](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L464)

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/Singularity.sol

/// @audit `onlyOnce` modifier is used to restrict access
62: function init(bytes calldata data) external onlyOnce {
/// @audit `onlyOwner` modifier is used to restrict access
477: function refreshPenroseFees(
address feeTo
) external onlyOwner notPaused returns (uint256 feeShares) {
/// @audit `onlyOwner` modifier is used to restrict access
489: function setSingularityConfig(
uint256 _lqCollateralizationRate,
uint256 _liquidationMultiplier,
uint256 _minimumTargetUtilization,
uint256 _maximumTargetUtilization,
uint64 _minimumInterestPerSecond,
uint64 _maximumInterestPerSecond,
uint256 _interestElasticity
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
576: function setLiquidationQueueConfig(
ILiquidationQueue _liquidationQueue,
address _bidExecutionSwapper,
address _usdoSwapper
) external onlyOwner {


*GitHub* : [62](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L62),[477](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L477),[489](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L489),[576](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/Singularity.sol#L576)

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

/// @audit `onlyOnce` modifier is used to restrict access
101: function init(bytes calldata data) external onlyOnce {
/// @audit `onlyOwner` modifier is used to restrict access
442: function refreshPenroseFees(
address
) external onlyOwner notPaused returns (uint256 feeShares) {
/// @audit `onlyOwner` modifier is used to restrict access
466: function setBigBangConfig(
uint256 _minDebtRate,
uint256 _maxDebtRate,
uint256 _debtRateAgainstEthMarket,
uint256 _liquidationMultiplier
) external onlyOwner {


*GitHub* : [101](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L101),[442](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L442),[466](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L466)

```solidity
File: tapioca-bar-audit/contracts/markets/Market.sol

/// @audit `onlyOwner` modifier is used to restrict access
142: function setBorrowOpeningFee(uint256 _val) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
151: function setBorrowCap(uint256 _cap) external notPaused onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
158: function setMarketConfig(
uint256 _borrowOpeningFee,
IOracle _oracle,
bytes calldata _oracleData,
address _conservator,
uint256 _callerFee,
uint256 _protocolFee,
uint256 _liquidationBonusAmount,
uint256 _minLiquidatorReward,
uint256 _maxLiquidatorReward,
uint256 _totalBorrowCap,
uint256 _collateralizationRate
) external onlyOwner {


*GitHub* : [142](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/Market.sol#L142),[151](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/Market.sol#L151),[158](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/Market.sol#L158)

```solidity
File: tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol

/// @audit `onlyHostChain` modifier is used to restrict access
69: function wrap(
address _fromAddress,
address _toAddress,
uint256 _amount
) external payable onlyHostChain {
/// @audit `onlyHostChain` modifier is used to restrict access
84: function unwrap(
address _toAddress,
uint256 _amount
) external onlyHostChain {


*GitHub* : [69](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L69),[84](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/TapiocaOFT.sol#L84)

```solidity
File: tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol

/// @audit `onlyHostChain` modifier is used to restrict access
88: function wrap(
address _fromAddress,
address _toAddress,
uint256 _amount
) external payable onlyHostChain {
/// @audit `onlyOwner` modifier is used to restrict access
116: function updateConnectedChain(
uint256 _chain,
bool _status
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
131: function updateBalancerState(
address _balancer,
bool _status
) external onlyOwner {


*GitHub* : [88](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L88),[116](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L116),[131](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/mTapiocaOFT.sol#L131)

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

/// @audit `onlyOwner` modifier is used to restrict access
115: function executeTOFT(
address _toft,
bytes calldata _bytecode,
bool _revertOnFailure
) external payable onlyOwner returns (bool success, bytes memory result) {
/// @audit `onlyOwner` modifier is used to restrict access
131: function executeCalls(
ExecutionCall[] calldata _call
)
external
payable
onlyOwner
returns (bool success, bytes[] memory results)
{
/// @audit `onlyOwner` modifier is used to restrict access
154: function createTOFT(
address _erc20,
bytes calldata _bytecode,
bytes32 _salt,
bool _linked
) external onlyOwner {


*GitHub* : [115](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/TapiocaWrapper.sol#L115),[131](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/TapiocaWrapper.sol#L131),[154](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/TapiocaWrapper.sol#L154)

```solidity
File: tapiocaz-audit/contracts/Balancer.sol

/// @audit `onlyOwner` modifier is used to restrict access
172: function rebalance(
address payable _srcOft,
uint16 _dstChainId,
uint256 _slippage,
uint256 _amount,
bytes memory _ercData
)
external
payable
onlyOwner
onlyValidDestination(_srcOft, _dstChainId)
onlyValidSlippage(_slippage)
{
/// @audit `onlyOwner` modifier is used to restrict access
219: function initConnectedOFT(
address _srcOft,
uint16 _dstChainId,
address _dstOft,
bytes memory _ercData
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
250: function addRebalanceAmount(
address _srcOft,
uint16 _dstChainId,
uint256 _amount
) external onlyValidDestination(_srcOft, _dstChainId) onlyOwner {


*GitHub* : [172](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/Balancer.sol#L172),[219](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/Balancer.sol#L219),[250](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/Balancer.sol#L250)

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

/// @audit `onlyOwner` modifier is used to restrict access
52: function setLockedUntil(uint256 _lockedUntil) external onlyOwner {


*GitHub* : [52](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/LTap.sol#L52)

```solidity
File: tap-token-audit/contracts/options/oTAP.sol

/// @audit `onlyBroker` modifier is used to restrict access
96: function mint(
address _to,
uint128 _expiry,
uint128 _discount,
uint256 _tOLP
) external onlyBroker returns (uint256 tokenId) {


*GitHub* : [96](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/oTAP.sol#L96)

```solidity
File: tap-token-audit/contracts/option-airdrop/aoTAP.sol

/// @audit `onlyBroker` modifier is used to restrict access
109: function mint(
address _to,
uint128 _expiry,
uint128 _discount,
uint256 _amount
) external onlyBroker returns (uint256 tokenId) {


*GitHub* : [109](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/aoTAP.sol#L109)

```solidity
File: tap-token-audit/contracts/Vesting.sol

/// @audit `onlyOwner` modifier is used to restrict access
130: function registerUser(address _user, uint256 _amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
151: function init(IERC20 _token, uint256 _seededAmount) external onlyOwner {


*GitHub* : [130](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/Vesting.sol#L130),[151](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/Vesting.sol#L151)

```solidity
File: tap-token-audit/contracts/tokens/TapOFT.sol

/// @audit `onlyOwner` modifier is used to restrict access
140: function setGovernanceChainIdentifier(
uint256 _identifier
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
152: function updatePause(bool val) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
160: function setMinter(address _minter) external onlyOwner {


*GitHub* : [140](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/TapOFT.sol#L140),[152](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/TapOFT.sol#L152),[160](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/TapOFT.sol#L160)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

/// @audit `onlyOwner` modifier is used to restrict access
259: function setSGLPoolWEight(
IERC20 singularity,
uint256 weight
) external onlyOwner updateTotalSGLPoolWeights {
/// @audit `onlyOwner` modifier is used to restrict access
276: function registerSingularity(
IERC20 singularity,
uint256 assetID,
uint256 weight
) external onlyOwner updateTotalSGLPoolWeights {
/// @audit `onlyOwner` modifier is used to restrict access
297: function unregisterSingularity(
IERC20 singularity
) external onlyOwner updateTotalSGLPoolWeights {


*GitHub* : [259](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L259),[276](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L276),[297](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L297)

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

/// @audit `onlyOwner` modifier is used to restrict access
308: function setTapOracle(
IOracle _tapOracle,
bytes calldata _tapOracleData
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
317: function setPhase2MerkleRoots(
bytes32[4] calldata _merkleRoots
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
323: function registerUserForPhase(
uint256 _phase,
address[] calldata _users,
uint256[] calldata _amounts
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
344: function setPaymentToken(
ERC20 _paymentToken,
IOracle _oracle,
bytes calldata _oracleData
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
357: function setPaymentTokenBeneficiary(
address _paymentTokenBeneficiary
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
365: function collectPaymentTokens(
address[] calldata _paymentTokens
) external onlyOwner {


*GitHub* : [308](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L308),[317](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L317),[323](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L323),[344](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L344),[357](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L357),[365](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L365)

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

/// @audit `onlyOwner` modifier is used to restrict access
454: function addRewardToken(IERC20 token) external onlyOwner returns (uint256) {


*GitHub* : [454](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L454)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

/// @audit `onlyOwner` modifier is used to restrict access
446: function setTapOracle(
IOracle _tapOracle,
bytes calldata _tapOracleData
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
458: function setPaymentToken(
ERC20 _paymentToken,
IOracle _oracle,
bytes calldata _oracleData
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
471: function setPaymentTokenBeneficiary(
address _paymentTokenBeneficiary
) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
479: function collectPaymentTokens(
address[] calldata _paymentTokens
) external onlyOwner {


*GitHub* : [446](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L446),[458](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L458),[471](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L471),[479](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L479)

```solidity
File: tap-token-audit/contracts/tokens/BaseTapOFT.sol

/// @audit `onlyOwner` modifier is used to restrict access
325: function setTwTap(address _twTap) external onlyOwner {


*GitHub* : [325](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/BaseTapOFT.sol#L325)

```solidity
File: tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol

/// @audit `onlyOwner` modifier is used to restrict access
61: function setPoolFee(uint24 _newFee) external onlyOwner {


*GitHub* : [61](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L61)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
90: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
101: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [90](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L90),[101](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/yearn/YearnStrategy.sol#L101)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
89: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
100: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [89](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L89),[100](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/compound/CompoundStrategy.sol#L100)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
93: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
104: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [93](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L93),[104](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/lido/LidoEthStrategy.sol#L104)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
125: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
132: function setMultiSwapper(address _swapper) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
141: function setTricryptoLPGetter(address _lpGetter) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
182: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [125](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L125),[132](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L132),[141](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L141),[182](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoNativeStrategy.sol#L182)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
134: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
141: function setMultiSwapper(address _swapper) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
150: function setTricryptoLPGetter(address _lpGetter) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
199: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [134](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L134),[141](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L141),[150](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L150),[199](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/curve/TricryptoLPStrategy.sol#L199)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
142: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
149: function setMultiSwapper(address _swapper) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
193: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [142](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L142),[149](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L149),[193](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/stargate/StargateStrategy.sol#L193)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
122: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
129: function setMultiSwapper(address _swapper) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
209: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [122](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L122),[129](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L129),[209](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/aave/AaveStrategy.sol#L209)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
109: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
120: function emergencyWithdraw() external onlyOwner returns (uint256 result) {


*GitHub* : [109](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L109),[120](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/balancer/BalancerStrategy.sol#L120)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
103: function harvestGmx(uint256 priceNum, uint256 priceDenom) public onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
112: function setFeeRecipient(address recipient) external onlyOwner {


*GitHub* : [103](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L103),[112](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/glp/GlpStrategy.sol#L112)

```solidity
File: tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol

/// @audit `onlyOwner` modifier is used to restrict access
148: function emergencyWithdraw() external onlyOwner returns (uint256 result) {
/// @audit `onlyOwner` modifier is used to restrict access
163: function setDepositThreshold(uint256 amount) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
170: function setMultiSwapper(address _swapper) external onlyOwner {
/// @audit `onlyOwner` modifier is used to restrict access
179: function setTricryptoLPGetter(address _lpGetter) external onlyOwner {


*GitHub* : [148](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L148),[163](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L163),[170](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L170),[179](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-yieldbox-strategies-audit/contracts/convex/ConvexTricryptoStrategy.sol#L179)
### [M-06]<a name="m-06"></a> Potential DoS Risk with Loops Iterating Over Large State Arrays
Looping through state arrays can lead to denial of service (DoS) vulnerabilities if the array grows too large. 
If the computations within the loop are extensive enough to expend the entire transaction's gas, the function may fail.
Consider implementing mechanisms to check or limit the size of state arrays or to reduce the computational work within loops.

*There are 1 instance(s) of this issue:*

```solidity
File: tapiocaz-audit/contracts/TapiocaWrapper.sol

/// @audit state `harvestableTapiocaOFTs[]` is `push()`ed and may grow too large to iterate over. | 175: harvestableTapiocaOFTs.push(iOFT);
98: for (uint256 i = 0; i < harvestableTapiocaOFTs.length; i++) {


*GitHub* : [98](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/TapiocaWrapper.sol#L98)
### [M-07]<a name="m-07"></a> Potential Over/Underflow in `unchecked` Blocks
In Solidity, the `unchecked` block is used to disable automatic overflow/underflow checks for the arithmetic operations inside the block.
This can be dangerous as it might allow `underflow` (or `overflow`) to occur silently, potentially leading to unexpected behaviors or vulnerabilities in the contract. 

It is recommended to manually implement appropriate checks inside `unchecked` blocks to prevent `underflow` and `overflow`, ensuring the contract's correctness and security.

*There are 3 instance(s) of this issue:*

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

/// @audit Unchecked block containing subtraction/addition/multiplication which may underflow.
306: uint256 sglLastIndex = sglLength - 1;



*GitHub* : [306](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L306)

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

/// @audit Unchecked block containing subtraction/addition/multiplication which may underflow.
176: votes = uint256(position.tapAmount) * uint256(position.multiplier);

/// @audit Unchecked block containing subtraction/addition/multiplication which may underflow.
403: if (goal - week > _limit) {



*GitHub* : [176](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L176),[403](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L403)
### [M-08]<a name="m-08"></a> Unchecked Return Values of the `approve()` Function
The unchecked return value of the `approve()` method can potentially cause transaction failures to go unnoticed in your contract. 

Some IERC20 token implementations utilize boolean return values to indicate transaction failures, instead of relying on the `revert()` function. If the return value of the `approve()` method isn't appropriately verified, transactions may seemingly proceed even when the necessary token approvals have not been appropriately executed.

As a safeguard, it is crucial to consistently verify the return values of these methods. This precaution helps to ensure the correct execution of token approvals, maintaining the integrity of transaction operations and reducing the risk of unnoticed transaction failures.

*There are 15 instance(s) of this issue:*

```solidity
File: tapioca-bar-audit/contracts/usd0/USDO.sol

101: _approve(address(receiver), address(this), _allowance - (amount + fee));


*GitHub* : [101](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/USDO.sol#L101)

```solidity
File: tapioca-bar-audit/contracts/markets/MarketERC20.sol

197: _approve(msg.sender, spender, amount);
280: _approve(owner, spender, value);


*GitHub* : [197](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L197),[280](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/MarketERC20.sol#L280)

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol

198: _approve(address(this), externalData.swapper, amount);
217: IERC20(swapData.tokenOut).approve(externalData.tOft, amountOut);


*GitHub* : [198](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L198),[217](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L217)

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

450: asset.approve(address(yieldBox), totalFees);
761: asset.approve(address(yieldBox), amount);


*GitHub* : [450](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L450),[761](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L761)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol

184: _erc20.approve(address(yieldBox), _amount);


*GitHub* : [184](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L184)

```solidity
File: tapiocaz-audit/contracts/Balancer.sol

321: erc20.approve(address(router), _amount);


*GitHub* : [321](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/Balancer.sol#L321)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

215: IERC20(erc20).approve(externalData.swapper, amount);


*GitHub* : [215](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L215)

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

157: IERC20(collateralAddress).approve(
    address(yieldBox),
    collateralAmount
);
234: IERC20(assetAddress).approve(address(yieldBox), depositAmount);
339: IERC20(bbCollateralAddress).approve(
        address(yieldBox),
        mintData.collateralDepositData.amount
    );
386: IERC20(sglAssetAddress).approve(
    address(yieldBox),
    depositData.amount
);
428: IERC20(address(singularity)).approve(address(yieldBox), fraction);


*GitHub* : [157](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L157),[234](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L234),[339](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L339),[386](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L386),[428](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L428)
### [M-09]<a name="m-09"></a> Unchecked Return Values of `transfer()/transferFrom()`
`transfer()` or `transferFrom()` methods without checking their return values.
Some IERC20 implementations use these boolean return values to signal transaction failures instead of using revert().
Not checking these values could allow transactions to proceed without the intended token transfers.
It is recommended to always check the return values of these methods.

*There are 32 instance(s) of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol

49: yieldBox.transfer(address(this), to, collateralId, share);
79: yieldBox.transfer(address(this), to, assetId, share);


*GitHub* : [49](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L49),[79](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L79)

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol

160: yieldBox.transfer(from, address(swapper), assetId, supplyShare);


*GitHub* : [160](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol#L160)

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

192: yieldBox.transfer(from, address(this), _assetId, share);
243: yieldBox.transfer(address(this), to, assetId, share);


*GitHub* : [192](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L192),[243](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L243)

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

166: yieldBox.transfer(
address(this),
address(liquidationQueue),
collateralId,
allCollateralShare
);
193: yieldBox.transfer(address(this), msg.sender, assetId, callerShare);
281: yieldBox.transfer(address(this), penrose.feeTo(), assetId, feeShare);
282: yieldBox.transfer(address(this), msg.sender, assetId, callerShare);
330: yieldBox.transfer(
address(this),
address(swapper),
collateralId,
collateralShare
);


*GitHub* : [166](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L166),[193](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L193),[281](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L281),[282](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L282),[330](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L330)

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

514: yieldBox.transfer(
    address(this),
    address(swapper),
    assetId,
    feeShares
);
536: yieldBox.transfer(address(this), feeTo, assetId, feeShares);


*GitHub* : [514](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L514),[536](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L536)

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

349: yieldBox.transfer(from, address(swapper), assetId, supplyShare);
596: yieldBox.transfer(
address(this),
address(swapper),
collateralId,
collateralShare
);
648: yieldBox.transfer(address(this), penrose.feeTo(), assetId, feeShare);
649: yieldBox.transfer(address(this), msg.sender, assetId, callerShare);
704: yieldBox.transfer(from, address(this), _tokenId, share);
717: yieldBox.transfer(address(this), to, collateralId, share);


*GitHub* : [349](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L349),[596](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L596),[648](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L648),[649](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L649),[704](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L704),[717](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L717)

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

42: tapToken.transferFrom(msg.sender, address(this), amount);
50: tapToken.transfer(msg.sender, amount);


*GitHub* : [42](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/LTap.sol#L42),[50](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/LTap.sol#L50)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

186: yieldBox.transfer(msg.sender, address(this), sglAssetID, sharesIn);
241: yieldBox.transfer(
address(this),
_to,
lockPosition.sglAssetID,
sharesOut
);


*GitHub* : [186](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L186),[241](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L241)

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

377: paymentToken.transfer(
        paymentTokenBeneficiary,
        paymentToken.balanceOf(address(this))
    );
509: _paymentToken.transferFrom(
msg.sender,
address(this),
discountedPaymentAmount
);
514: tapOFT.transfer(msg.sender, tapAmount);


*GitHub* : [377](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L377),[509](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L509),[514](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L514)

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

260: tapOFT.transferFrom(msg.sender, address(this), _amount);
565: tapOFT.transfer(_to, releasedAmount);


*GitHub* : [260](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L260),[565](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L565)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

230: tOLP.transferFrom(msg.sender, address(this), _tOLPTokenID);
342: tOLP.transferFrom(address(this), otapOwner, oTAPPosition.tOLP);
491: paymentToken.transfer(
        paymentTokenBeneficiary,
        paymentToken.balanceOf(address(this))
    );
530: _paymentToken.transferFrom(
msg.sender,
address(this),
discountedPaymentAmount
);


*GitHub* : [230](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L230),[342](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L342),[491](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L491),[530](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L530)

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

624: yieldBox.transfer(
        address(this),
        user,
        bigBang.assetId(),
        yieldBox.toShare(
            bigBang.assetId(),
            _removeAmount - repayed,
            false
        )
    );


*GitHub* : [624](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L624)
### [M-10]<a name="m-10"></a> Unsafe use of `transfer()/transferFrom()` with IERC20
Not all tokens adhere strictly to the ERC20 standard, even if they are largely accepted as compliant.
A prominent example is Tether (USDT) on L1, where the transfer() and transferFrom() functions do not return booleans, contrary to the standard's requirements.
Instead, these functions provide no return value at all.
This discrepancy can lead to issues when such tokens are cast to IERC20: their non-standard function signatures can cause calls to revert.
As a safer alternative, consider using OpenZeppelin's SafeERC20 library, which offers safeTransfer() and safeTransferFrom() functions to address these incompatibilities.

*There are 32 instance(s) of this issue:*

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol

49: yieldBox.transfer(address(this), to, collateralId, share);
79: yieldBox.transfer(address(this), to, assetId, share);


*GitHub* : [49](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L49),[79](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLendingCommon.sol#L79)

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol

160: yieldBox.transfer(from, address(swapper), assetId, supplyShare);


*GitHub* : [160](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLeverage.sol#L160)

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol

192: yieldBox.transfer(from, address(this), _assetId, share);
243: yieldBox.transfer(address(this), to, assetId, share);


*GitHub* : [192](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L192),[243](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLCommon.sol#L243)

```solidity
File: tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol

166: yieldBox.transfer(
address(this),
address(liquidationQueue),
collateralId,
allCollateralShare
);
193: yieldBox.transfer(address(this), msg.sender, assetId, callerShare);
281: yieldBox.transfer(address(this), penrose.feeTo(), assetId, feeShare);
282: yieldBox.transfer(address(this), msg.sender, assetId, callerShare);
330: yieldBox.transfer(
address(this),
address(swapper),
collateralId,
collateralShare
);


*GitHub* : [166](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L166),[193](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L193),[281](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L281),[282](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L282),[330](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/singularity/SGLLiquidation.sol#L330)

```solidity
File: tapioca-bar-audit/contracts/Penrose.sol

514: yieldBox.transfer(
    address(this),
    address(swapper),
    assetId,
    feeShares
);
536: yieldBox.transfer(address(this), feeTo, assetId, feeShares);


*GitHub* : [514](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L514),[536](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/Penrose.sol#L536)

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

349: yieldBox.transfer(from, address(swapper), assetId, supplyShare);
596: yieldBox.transfer(
address(this),
address(swapper),
collateralId,
collateralShare
);
648: yieldBox.transfer(address(this), penrose.feeTo(), assetId, feeShare);
649: yieldBox.transfer(address(this), msg.sender, assetId, callerShare);
704: yieldBox.transfer(from, address(this), _tokenId, share);
717: yieldBox.transfer(address(this), to, collateralId, share);


*GitHub* : [349](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L349),[596](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L596),[648](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L648),[649](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L649),[704](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L704),[717](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L717)

```solidity
File: tap-token-audit/contracts/tokens/LTap.sol

42: tapToken.transferFrom(msg.sender, address(this), amount);
50: tapToken.transfer(msg.sender, amount);


*GitHub* : [42](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/LTap.sol#L42),[50](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/tokens/LTap.sol#L50)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol

186: yieldBox.transfer(msg.sender, address(this), sglAssetID, sharesIn);
241: yieldBox.transfer(
address(this),
_to,
lockPosition.sglAssetID,
sharesOut
);


*GitHub* : [186](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L186),[241](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionLiquidityProvision.sol#L241)

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

377: paymentToken.transfer(
        paymentTokenBeneficiary,
        paymentToken.balanceOf(address(this))
    );
509: _paymentToken.transferFrom(
msg.sender,
address(this),
discountedPaymentAmount
);
514: tapOFT.transfer(msg.sender, tapAmount);


*GitHub* : [377](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L377),[509](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L509),[514](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L514)

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

260: tapOFT.transferFrom(msg.sender, address(this), _amount);
565: tapOFT.transfer(_to, releasedAmount);


*GitHub* : [260](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L260),[565](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L565)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

230: tOLP.transferFrom(msg.sender, address(this), _tOLPTokenID);
342: tOLP.transferFrom(address(this), otapOwner, oTAPPosition.tOLP);
491: paymentToken.transfer(
        paymentTokenBeneficiary,
        paymentToken.balanceOf(address(this))
    );
530: _paymentToken.transferFrom(
msg.sender,
address(this),
discountedPaymentAmount
);


*GitHub* : [230](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L230),[342](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L342),[491](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L491),[530](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L530)

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

624: yieldBox.transfer(
        address(this),
        user,
        bigBang.assetId(),
        yieldBox.toShare(
            bigBang.assetId(),
            _removeAmount - repayed,
            false
        )
    );


*GitHub* : [624](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L624)
### [M-11]<a name="m-11"></a> For ERC721 use `safeTransferFrom()` instead of `transferFrom()`
Use of `transferFrom()` method for ERC721 transfer is discouraged and recommended to use `safeTransferFrom()`.
Because `transferFrom()` cannot check whether the receiving address knows how to handle ERC721 tokens.

*There are 5 instance(s) of this issue:*

```solidity
File: tap-token-audit/contracts/option-airdrop/AirdropBroker.sol

509: _paymentToken.transferFrom(


*GitHub* : [509](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/option-airdrop/AirdropBroker.sol#L509)

```solidity
File: tap-token-audit/contracts/governance/twTAP.sol

260: tapOFT.transferFrom(msg.sender, address(this), _amount);


*GitHub* : [260](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/governance/twTAP.sol#L260)

```solidity
File: tap-token-audit/contracts/options/TapiocaOptionBroker.sol

230: tOLP.transferFrom(msg.sender, address(this), _tOLPTokenID);
342: tOLP.transferFrom(address(this), otapOwner, oTAPPosition.tOLP);
530: _paymentToken.transferFrom(


*GitHub* : [230](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L230),[342](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L342),[530](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tap-token-audit/contracts/options/TapiocaOptionBroker.sol#L530)
### [M-12]<a name="m-12"></a> Use `forceApprove/safeIncreaseAllowance` from SafeERC20 instead of `approve/safeApprove`
Certain tokens, exemplified by USDT, have quirks where adjusting an allowance directly from a non-zero value can be problematic. For such tokens, it's a common requirement to first reset the allowance to zero before setting a new value. Failing to do so can result in transaction reverts, disrupting protocol functionality.

To gracefully handle this, consider using the `forceApprove` method from OpenZeppelin's SafeERC20 library. This method ensures the contract's allowance towards a `spender` is set to the specified `value`. If the token doesn't return a value, the non-reverting calls are assumed successful, offering a seamless solution for tokens like USDT.

Since `safeIncreaseAllowance` calls `forceApprove` internally, it's also a viable alternative.

[Reference the SafeERC20 Library for more details](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/9e3f4d60c581010c4a3979480e07cc7752f124cc/contracts/token/ERC20/utils/SafeERC20.sol#L71C8-L83).

*There are 12 instance(s) of this issue:*

```solidity
File: tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol

217: IERC20(swapData.tokenOut).approve(externalData.tOft, amountOut);


*GitHub* : [217](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/usd0/modules/USDOLeverageModule.sol#L217)

```solidity
File: tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol

450: asset.approve(address(yieldBox), totalFees);
761: asset.approve(address(yieldBox), amount);


*GitHub* : [450](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L450),[761](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-bar-audit/contracts/markets/bigBang/BigBang.sol#L761)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol

184: _erc20.approve(address(yieldBox), _amount);


*GitHub* : [184](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTStrategyModule.sol#L184)

```solidity
File: tapiocaz-audit/contracts/Balancer.sol

321: erc20.approve(address(router), _amount);


*GitHub* : [321](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/Balancer.sol#L321)

```solidity
File: tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol

215: IERC20(erc20).approve(externalData.swapper, amount);


*GitHub* : [215](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapiocaz-audit/contracts/tOFT/modules/BaseTOFTLeverageModule.sol#L215)

```solidity
File: tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol

172: TransferHelper.safeApprove(tokenIn, address(swapRouter), amountIn);


*GitHub* : [172](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Swapper/UniswapV3Swapper.sol#L172)

```solidity
File: tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol

157: IERC20(collateralAddress).approve(
    address(yieldBox),
    collateralAmount
);
234: IERC20(assetAddress).approve(address(yieldBox), depositAmount);
339: IERC20(bbCollateralAddress).approve(
        address(yieldBox),
        mintData.collateralDepositData.amount
    );
386: IERC20(sglAssetAddress).approve(
    address(yieldBox),
    depositData.amount
);
428: IERC20(address(singularity)).approve(address(yieldBox), fraction);


*GitHub* : [157](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L157),[234](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L234),[339](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L339),[386](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L386),[428](https://github.com/code-423n4/test/2023-07-tapioca/blob/main/tapioca-periph-audit/contracts/Magnetar/modules/MagnetarMarketModule.sol#L428) Thanks for reading!
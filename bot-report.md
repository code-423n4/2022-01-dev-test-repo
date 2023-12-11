## Summary

| |Issue|Instances| Gas Savings
|-|:-|:-:|:-:|
| [[medium-01](#medium-01)] | Contracts vulnerable to accounting-related issues with fee-on-transfer | 1| 0|
| [[medium-02](#medium-02)] | Potential token reversion when zero-value transfers occur | 2| 0|
| [[low-01](#low-01)] | Unsafe ERC20 operation(s) | 2| 0|
| [[low-02](#low-02)] | Unchecked return values of `transfer()`/`transferFrom()` | 2| 0|
| [[low-03](#low-03)] | Draft imports may break in new minor versions | 1| 0|
| [[low-04](#low-04)] | Centralization risk | 1| 0|
| [[low-05](#low-05)] | Functions calling contracts/addresses with transfer hooks are missing reentrancy guards | 2| 0|
| [[low-06](#low-06)] | State variables not capped at reasonable values | 1| 0|
| [[nc-01](#nc-01)] | Non-external/public variable names should start with an underscore | 1| 0|
| [[nc-02](#nc-02)] | Non-library/interface files should use fixed compiler versions, not floating ones | 2| 0|
| [[nc-03](#nc-03)] | Missing event for a critical parameter change | 1| 0|
| [[nc-04](#nc-04)] | Consider activating `via-ir` for deploying | 2| 0|
| [[nc-05](#nc-05)] | Inconsistent spacing in comments | 7| 0|
| [[nc-06](#nc-06)] | Consider adding a block/deny-list | 1| 0|
| [[nc-07](#nc-07)] | Missing checks for `address(0)` in constructor/initializers | 1| 0|
| [[nc-08](#nc-08)] | Large or complicated code bases should implement invariant tests | 2| 0|
| [[nc-09](#nc-09)] | NatSpec: Function declarations should have descriptions | 3| 0|
| [[nc-10](#nc-10)] | Style guide: Lines are too long | 9| 0|
| [[nc-11](#nc-11)] | NatSpec: State variable declarations should have descriptions | 3| 0|
| [[nc-12](#nc-12)] | Contract declarations should have NatSpec `@author` annotations | 2| 0|
| [[nc-13](#nc-13)] | Named imports of parent contracts are missing | 3| 0|
| [[nc-14](#nc-14)] | Contract should expose an `interface` | 5| 0|
| [[nc-15](#nc-15)] | `public` functions not called by the contract should be declared `external` instead | 2| 0|
| [[nc-16](#nc-16)] | Contract declarations should have NatSpec `@dev` annotations | 2| 0|
| [[nc-17](#nc-17)] | Set explicit visibility instead of defaulting to `internal` | 1| 0|
| [[nc-18](#nc-18)] | Use specific identifiers in import declarations | 3| 0|
| [[nc-19](#nc-19)] | NatSpec: Function `@param` tag is missing | 4| 0|
| [[nc-20](#nc-20)] | Consider disabling renounceOwnership() by overwriting It | 1| 0|
| [[nc-21](#nc-21)] | Top-level declarations should be separated by at least two lines | 3| 0|
| [[nc-22](#nc-22)] | Consider adding formal verification proofs | 2| 0|
| [[nc-23](#nc-23)] | Contract names should use CamelCase | 2| 0|
| [[nc-24](#nc-24)] | State variables should include comments | 3| 0|
| [[nc-25](#nc-25)] | NatSpec: Function declarations should have `@dev` tags | 2| 0|
| [[nc-26](#nc-26)] | Contracts should have full test coverage | 2| 0|
| [[gas-01](#gas-01)] | Use >=/<= instead of >/< | 1| 0|
| [[gas-02](#gas-02)] | The `payable` modifier can be used in constructors | 1| 0|
| [[gas-03](#gas-03)] | State variables only set in the constructor should be declared `immutable` | 2| 0|
| [[gas-04](#gas-04)] | Optimize names to save gas | 2| 0|
| [[gas-05](#gas-05)] | Avoid unnecessary storage updates | 1| 0|
| [[gas-06](#gas-06)] | Reduce gas usage by upgrading to Solidity 0.8.19 or later | 2| 0|
| [[gas-07](#gas-07)] | Restricted functions can be marked as `payable` | 1| 0|
| [[gas-08](#gas-08)] | Utilize Custom Errors for Cost-Effective Deployment and Runtime | 2| 0|


  ### medium Risk Issues


### [medium-01]<a name="medium-01"></a> Contracts vulnerable to accounting-related issues with fee-on-transfer
The below functions, which use `transferFrom()`, may result in an incorrect number of tokens being received compared to the input amount. This discrepancy can occur with fee-on-transfer tokens, causing accounting problems due to a smaller balance after the transfer. Even if later checks are in place for secondary transfers, an attacker could potentially exploit latent funds mistakenly sent by another user to obtain free credit. To mitigate this issue, one solution is to measure the balance before and after the transfer and utilize the difference as the transaction amount instead of relying solely on the provided amount.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

42 | tapToken.transferFrom(msg.sender, address(this), amount);
```


*GitHub* : [42](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L42)
### [medium-02]<a name="medium-02"></a> Potential token reversion when zero-value transfers occur
Although EIP-20 mandates acceptance of zero-valued transfers, certain tokens like LEND may revert if such transfers are made. This can lead to complete transaction reversions, even for operations involving other tokens like batch operations. To save gas and prevent this issue, it is advisable to skip the transfer if the transfer amount is zero.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

42 | tapToken.transferFrom(msg.sender, address(this), amount);

50 | tapToken.transfer(msg.sender, amount);
```


*GitHub* : [42](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L42),[50](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L50)### low Risk Issues


### [low-01]<a name="low-01"></a> Unsafe ERC20 operation(s)
Some tokens don't fully adhere to the ERC20 standard but are still widely accepted by ERC20 token-compatible code. For instance, on L1, Tether (USDT) does not return booleans as required by the specification in its `transfer()` and `transferFrom()` functions. Instead, these functions have no return value. Consequently, when these tokens are cast to `IERC20`, their function signatures do not match, causing the calls to revert. To mitigate this issue, it is recommended to utilize OpenZeppelin's `SafeERC20` library and employ the `safeTransfer()` or `safeTransferFrom()` functions. Please refer to the [function signatures article](https://medium.com/coinmonks/missing-return-value-bug-at-least-130-tokens-affected-d67bf08521ca) for additional details.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

42 | tapToken.transferFrom(msg.sender, address(this), amount);

50 | tapToken.transfer(msg.sender, amount);
```


*GitHub* : [42](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L42),[50](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L50)
### [low-02]<a name="low-02"></a> Unchecked return values of `transfer()`/`transferFrom()`
It has been observed that not all implementations of `IERC20` properly handle failures in the `transfer()` or `transferFrom()` functions. These functions have a `boolean` return value to indicate errors, instead of reverting. If the return value is not checked, operations that should have failed can potentially succeed without making the intended payment.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

42 | tapToken.transferFrom(msg.sender, address(this), amount);

50 | tapToken.transfer(msg.sender, amount);
```


*GitHub* : [50](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L50),[42](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L42)
### [low-03]<a name="low-03"></a> Draft imports may break in new minor versions
While OpenZeppelin draft contracts are safe to use and have been audited, their 'draft' status means that the EIPs they're based on are not finalized, and thus there may be breaking changes in even [minor releases](https://docs.openzeppelin.com/contracts/3.x/api/drafts). If a bug is found in this version of OpenZeppelin, and the version that you're forced to upgrade to has breaking changes in the new version, you'll encounter unnecessary delays in porting and testing replacement contracts. Ensure that you have extensive test coverage of this area so that differences can be automatically detected, and have a plan in place for how you would fully test a new version of these contracts if they do indeed change unexpectedly. Consider creating a forked version of the file rather than importing it from the package, and manually patch your fork as changes are made.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

5 | import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";
```


*GitHub* : [5](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L5)
### [low-04]<a name="low-04"></a> Centralization risk
Relying solely on a single externally owned account (EOA) as the owner of contracts introduces significant risks of centralization and single points of failure. In case of a hack or the inability to access the key, there is a high chance of losing control over the entire system. To mitigate this risk, it is advisable to transition to a multi-signature setup or implement a role-based authorization model, ensuring multiple parties are involved in decision-making and key management.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

53 | function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
```


*GitHub* : [53](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L53)
### [low-05]<a name="low-05"></a> Functions calling contracts/addresses with transfer hooks are missing reentrancy guards
While adherence to the check-effects-interaction pattern is commendable, the absence of a reentrancy guard in functions, especially where transfer hooks might be present, can expose the protocol users to risks of read-only reentrancies. Such reentrancy vulnerabilities can be exploited to execute malicious actions even without altering the contract state. Without a reentrancy guard, the only potential mitigation would be to blocklist the entire protocol - an extreme and disruptive measure. Therefore, incorporating a reentrancy guard into these functions is vital to bolster security, as it helps protect against both traditional reentrancy attacks and read-only reentrancies, ensuring robust and safe protocol operations.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

42 | tapToken.transferFrom(msg.sender, address(this), amount);

50 | tapToken.transfer(msg.sender, amount);
```


*GitHub* : [42](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L42),[50](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L50)
### [low-06]<a name="low-06"></a> State variables not capped at reasonable values
Consider adding minimum/maximum value checks to ensure that the state variables below can never be used to excessively harm users, including via griefing

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

38 | maxLockedUntil = _maxLockedUntil;
```


*GitHub* : [38](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L38)### nc Risk Issues


### [nc-01]<a name="nc-01"></a> Non-external/public variable names should start with an underscore
As per the Solidity Style Guide, it is recommended to prefix non-external/public variable names with an underscore (_). This naming convention helps distinguish them from external or public entities within the smart contract.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

24 | IERC20 tapToken;
```


*GitHub* : [24](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L24)
### [nc-02]<a name="nc-02"></a> Non-library/interface files should use fixed compiler versions, not floating ones
Non-library/interface files should be written with fixed compiler versions specified, as opposed to using floating compiler versions. This ensures consistent compilation and avoids potential issues that may arise with different compiler versions.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

// @audit: Found contract: LTap
2 | pragma solidity ^0.8.18;
```


*GitHub* : [2](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L2)

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

// @audit: Found contract: SGLCollateral
2 | pragma solidity ^0.8.18;
```


*GitHub* : [2](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L2)
### [nc-03]<a name="nc-03"></a> Missing event for a critical parameter change
In cases where critical state changes are not safeguarded by event emission.
This is particularly important for functions starting with 'set' or 'update' and having the 'onlyOwner' modifier.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

53 | function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
54 |         require(_lockedUntil <= maxLockedUntil, "Too late");
55 |         lockedUntil = _lockedUntil;
56 |     }
```


*GitHub* : [53](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L53)
### [nc-04]<a name="nc-04"></a> Consider activating `via-ir` for deploying
The IR-based code generator was developed to make code generation more performant by enabling optimization passes that can be applied across functions.

It is possible to activate the IR-based code generator through the command line by using the flag `--via-ir` or by including the option `{"viaIR": true}`.

Keep in mind that compiling with this option may take longer. However, you can simply test it before deploying your code. If you find that it provides better performance, you can add the `--via-ir` flag to your deploy command.

*There are 2 instance(s) of this issue:*

Project

*GitHub* : [1](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/),[2](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/)
### [nc-05]<a name="nc-05"></a> Inconsistent spacing in comments
There are instances in the code where `// x`, `//x`, `/// x`, or `///x` are used with inconsistent spacing. The following examples highlight the occurrences that deviate from the majority within each file.

*There are 7 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

1 | // SPDX-License-Identifier: UNLICENSED

21 | /// @title Locked TAP

22 | /// @notice Allow users to redeem LTAP for TAP after a certain period of time, in a 1:1 ratio.

28 | /// @notice Creates a new LTAP token

29 | /// @dev LTAP tokens are minted by depositing TAP

30 | /// @param _tapToken Address of the TAP token

31 | /// @param _maxLockedUntil Latest possible end of locking period
```


*GitHub* : [28](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L28),[1](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L1),[21](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L21),[22](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L22),[29](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L29),[30](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L30),[31](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L31)
### [nc-06]<a name="nc-06"></a> Consider adding a block/deny-list
Doing so will significantly increase centralization, but will help to prevent hackers from using stolen tokens

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

23 | contract LTap is BoringOwnable, ERC20Permit {
```


*GitHub* : [23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23)
### [nc-07]<a name="nc-07"></a> Missing checks for `address(0)` in constructor/initializers
Check for zero-address to avoid the risk of setting `address(0)` for state variables when deploying.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

36 | tapToken = _tapToken;
```


*GitHub* : [36](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L36)
### [nc-08]<a name="nc-08"></a> Large or complicated code bases should implement invariant tests
When dealing with large code bases or code containing intricate inline-assembly, complex mathematical calculations, or intricate interactions among multiple contracts, it is crucial to incorporate invariant fuzzing tests. Invariant fuzzers like Echidna operate by requiring the test writer to establish invariants that must never be violated under any circumstances. These fuzzers examine various inputs and function calls to ensure that the defined invariants always hold true. Merely achieving 100% code coverage does not guarantee bug-free code, as the order in which users perform operations can lead to unforeseen issues. By leveraging properly and extensively formulated invariants, invariant fuzzers can effectively address this testing gap.

*There are 2 instance(s) of this issue:*

Project

*GitHub* : [2](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/),[1](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/)
### [nc-09]<a name="nc-09"></a> NatSpec: Function declarations should have descriptions
e.g. `@dev` or `@notice`

*There are 3 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

41 | function deposit(uint256 amount) external {

46 | function redeem() external {

53 | function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
```


*GitHub* : [46](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L46),[41](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L41),[53](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L53)
### [nc-10]<a name="nc-10"></a> Style guide: Lines are too long
Usually lines in source code are limited to 80 characters. Today's screens are much larger so it's reasonable to stretch this in some cases. The Solidity style guide recommends a maximum line length of 120 characters, so the lines below should be split when they reach that length.

*There are 9 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

9 | __/\\\\\\\\\\\\\\\_____/\\\\\\\\\_____/\\\\\\\\\\\\\____/\\\\\\\\\\\_______/\\\\\_____________/\\\\\\\\\_____/\\\\\\\\\____

10 | _\///////\\\/////____/\\\\\\\\\\\\\__\/\\\/////////\\\_\/////\\\///______/\\\///\\\________/\\\////////____/\\\\\\\\\\\\\__

11 | _______\/\\\________/\\\/////////\\\_\/\\\_______\/\\\_____\/\\\_______/\\\/__\///\\\____/\\\/____________/\\\/////////\\\_

12 | _______\/\\\_______\/\\\_______\/\\\_\/\\\\\\\\\\\\\/______\/\\\______/\\\______\//\\\__/\\\_____________\/\\\_______\/\\\_

13 | _______\/\\\_______\/\\\\\\\\\\\\\\\_\/\\\/////////________\/\\\_____\/\\\_______\/\\\_\/\\\_____________\/\\\\\\\\\\\\\\\_

14 | _______\/\\\_______\/\\\/////////\\\_\/\\\_________________\/\\\_____\//\\\______/\\\__\//\\\____________\/\\\/////////\\\_

15 | _______\/\\\_______\/\\\_______\/\\\_\/\\\_________________\/\\\______\///\\\__/\\\_____\///\\\__________\/\\\_______\/\\\_

16 | _______\/\\\_______\/\\\_______\/\\\_\/\\\______________/\\\\\\\\\\\____\///\\\\\/________\////\\\\\\\\\_\/\\\_______\/\\\_

17 | _______\///________\///________\///__\///______________\///////////_______\/////_____________\/////////__\///________\///__
```


*GitHub* : [14](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L14),[15](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L15),[16](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L16),[17](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L17),[9](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L9),[10](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L10),[11](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L11),[12](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L12),[13](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L13)
### [nc-11]<a name="nc-11"></a> NatSpec: State variable declarations should have descriptions
e.g. `@notice` for public state variables, and `@dev` for non-public ones

*There are 3 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

24 | IERC20 tapToken;

25 | uint256 public lockedUntil;

26 | uint256 public maxLockedUntil;
```


*GitHub* : [24](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L24),[26](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L26),[25](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L25)
### [nc-12]<a name="nc-12"></a> Contract declarations should have NatSpec `@author` annotations
Add natspec annotation for clarity

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

23 | contract LTap is BoringOwnable, ERC20Permit {
```


*GitHub* : [23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23)

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

8 | contract SGLCollateral is SGLLendingCommon {
```


*GitHub* : [8](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L8)
### [nc-13]<a name="nc-13"></a> Named imports of parent contracts are missing
Parent contracts should use [named imports](https://docs.soliditylang.org/en/latest/layout-of-source-files.html#syntax-and-semantics) to improve the code readability.

*There are 3 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

8 | contract SGLCollateral is SGLLendingCommon {
```


*GitHub* : [8](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L8)

```solidity
File: contracts/tokens/LTap.sol

23 | contract LTap is BoringOwnable, ERC20Permit {

23 | contract LTap is BoringOwnable, ERC20Permit {
```


*GitHub* : [23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23),[23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23)
### [nc-14]<a name="nc-14"></a> Contract should expose an `interface`
The `contracts` should expose an `interface` so that other projects can more easily integrate with it, without having to develop their own non-standard variants.

*There are 5 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

41 | function deposit(uint256 amount) external {
42 |         tapToken.transferFrom(msg.sender, address(this), amount);
43 |         _mint(msg.sender, amount);
44 |     }

46 | function redeem() external {
47 |         require(block.timestamp > lockedUntil, "Still locked");
48 |         uint256 amount = balanceOf(msg.sender);
49 |         _burn(msg.sender, amount);
50 |         tapToken.transfer(msg.sender, amount);
51 |     }

53 | function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
54 |         require(_lockedUntil <= maxLockedUntil, "Too late");
55 |         lockedUntil = _lockedUntil;
56 |     }
```


*GitHub* : [41](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L41),[53](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L53),[46](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L46)

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

21 | function addCollateral(
22 |         address from,
23 |         address to,
24 |         bool skim,
25 |         uint256 amount,
26 |         uint256 share
27 |     ) public notPaused allowedBorrow(from, share) {
28 |         _addCollateral(from, to, skim, amount, share);
29 |     }

35 | function removeCollateral(
36 |         address from,
37 |         address to,
38 |         uint256 share
39 |     ) public notPaused solvent(from) allowedBorrow(from, share) {
40 |         _removeCollateral(from, to, share);
41 |     }
```


*GitHub* : [21](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L21),[35](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L35)
### [nc-15]<a name="nc-15"></a> `public` functions not called by the contract should be declared `external` instead
Contracts [are allowed](https://docs.soliditylang.org/en/latest/contracts.html#function-overriding) to override their parents' functions and change the visibility from `external` to `public`.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

21 | function addCollateral(

35 | function removeCollateral(
```


*GitHub* : [35](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L35),[21](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L21)
### [nc-16]<a name="nc-16"></a> Contract declarations should have NatSpec `@dev` annotations
Add natspec annotation for clarity

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

8 | contract SGLCollateral is SGLLendingCommon {
```


*GitHub* : [8](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L8)

```solidity
File: contracts/tokens/LTap.sol

23 | contract LTap is BoringOwnable, ERC20Permit {
```


*GitHub* : [23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23)
### [nc-17]<a name="nc-17"></a> Set explicit visibility instead of defaulting to `internal`
Visibility should be set explicitly rather than defaulting to `internal`.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

24 | IERC20 tapToken;
```


*GitHub* : [24](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L24)
### [nc-18]<a name="nc-18"></a> Use specific identifiers in import declarations

*There are 3 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

4 | import "@boringcrypto/boring-solidity/contracts/BoringOwnable.sol";

5 | import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";
```


*GitHub* : [5](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L5),[4](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L4)

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

4 | import "./SGLLendingCommon.sol";
```


*GitHub* : [4](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L4)
### [nc-19]<a name="nc-19"></a> NatSpec: Function `@param` tag is missing
NatSpec documentation, including `@param`, allows developers to provide clear explanations for function parameters, improving code readability and maintainability.

*There are 4 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

// @audit: Missing: @param amount
21 | function addCollateral(
22 |         address from,
23 |         address to,
24 |         bool skim,
25 |         uint256 amount,
26 |         uint256 share
27 |     ) public notPaused allowedBorrow(from, share) 
```


*GitHub* : [21](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L21)

```solidity
File: contracts/tokens/LTap.sol

// @audit: Missing: @param amount
41 | function deposit(uint256 amount) external {

// @audit: Missing: 
46 | function redeem() external {

// @audit: Missing: @param _lockedUntil
53 | function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
```


*GitHub* : [41](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L41),[46](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L46),[53](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L53)
### [nc-20]<a name="nc-20"></a> Consider disabling renounceOwnership() by overwriting It
If there is no provision in your project's roadmap to remove ownership, you may want to override the renounceOwnership() function in OpenZeppelin's Ownable contract to prevent its functionality.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

23 | contract LTap is BoringOwnable, ERC20Permit {
```


*GitHub* : [23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23)
### [nc-21]<a name="nc-21"></a> Top-level declarations should be separated by at least two lines
Follow the solidity style guide.

*There are 3 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

39 |     }
40 | 
41 |     function deposit(uint256 amount) external {

44 |     }
45 | 
46 |     function redeem() external {

51 |     }
52 | 
53 |     function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
```


*GitHub* : [51](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L51),[39](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L39),[44](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L44)
### [nc-22]<a name="nc-22"></a> Consider adding formal verification proofs
Consider using formal verification to mathematically prove that your code does what is intended, and does not have any edge cases with unexpected behavior. The solidity compiler itself has this functionality [built in](https://docs.soliditylang.org/en/latest/smtchecker.html#smtchecker-and-formal-verification)

*There are 2 instance(s) of this issue:*

Project

*GitHub* : [1](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/),[2](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/)
### [nc-23]<a name="nc-23"></a> Contract names should use CamelCase
According to the Solidity [style guide](https://docs.soliditylang.org/en/latest/style-guide.html#contract-and-library-names) contract names should be in CamelCase and should match their file names.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

8 | contract SGLCollateral is SGLLendingCommon {
```


*GitHub* : [8](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L8)

```solidity
File: contracts/tokens/LTap.sol

23 | contract LTap is BoringOwnable, ERC20Permit {
```


*GitHub* : [23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23)
### [nc-24]<a name="nc-24"></a> State variables should include comments
Consider adding some comments on critical state variables to explain what they are supposed to do: this will help for future code reviews.

*There are 3 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

24 | IERC20 tapToken;

25 | uint256 public lockedUntil;

26 | uint256 public maxLockedUntil;
```


*GitHub* : [24](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L24),[25](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L25),[26](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L26)
### [nc-25]<a name="nc-25"></a> NatSpec: Function declarations should have `@dev` tags
`@dev`` is used to explain to end users what the function does, and the compiler interprets /// or /** comments as this tag if one wasn't explicitly provided

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

21 | function addCollateral(
22 |         address from,
23 |         address to,
24 |         bool skim,
25 |         uint256 amount,
26 |         uint256 share
27 |     ) public notPaused allowedBorrow(from, share) 

35 | function removeCollateral(
36 |         address from,
37 |         address to,
38 |         uint256 share
39 |     ) public notPaused solvent(from) allowedBorrow(from, share) 
```


*GitHub* : [21](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L21),[35](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L35)
### [nc-26]<a name="nc-26"></a> Contracts should have full test coverage
While 100% code coverage does not guarantee that there are no bugs, it often helps identify easy-to-find bugs and reduces the likelihood of regressions when modifying the code. Additionally, achieving full coverage often requires code authors to re-organize their code in a modular manner, allowing separate testing of each component. This approach reduces interdependencies between modules and layers, resulting in code that is easier to understand, reason about, and audit.

*There are 2 instance(s) of this issue:*

Project

*GitHub* : [1](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/),[2](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/)### gas Risk Issues


### [gas-01]<a name="gas-01"></a> Use >=/<= instead of >/<
The compiler uses opcodes GT and ISZERO for code that uses >, but only requires LT for >=. A similar behaviour applies for >, which uses opcodes LT and ISZERO, but only requires GT for <=.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

47 | require(block.timestamp > lockedUntil, "Still locked");
```


*GitHub* : [47](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L47)
### [gas-02]<a name="gas-02"></a> The `payable` modifier can be used in constructors
By marking a constructor as `payable`, it becomes possible for the deployer of the smart contract to send funds along with its deployment. Since the deployer is the only one able to provide funds during contract creation, there is no risk of unintended transfers. Furthermore, the use of `payable` in constructors can result in lower gas costs, as additional safety checks are not required.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

32 | constructor(
33 |         IERC20 _tapToken,
34 |         uint256 _maxLockedUntil
35 |     ) ERC20("LTAP", "LTAP") ERC20Permit("LTAP") 
```


*GitHub* : [32](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L32)
### [gas-03]<a name="gas-03"></a> State variables only set in the constructor should be declared `immutable`
Avoids a Gsset (**20000 gas**) in the constructor, and replaces the first access in each transaction (Gcoldsload - **2100 gas**) and each access thereafter (Gwarmacces - **100 gas**) with a `PUSH32` (**3 gas**).

While `string`s are not value types, and therefore cannot be `immutable`/`constant` if not hard-coded outside of the constructor, the same behavior can be achieved by making the current contract `abstract` with `virtual` functions for the `string` accessors, and having a child contract override the functions with the hard-coded implementation-specific values.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

36 | tapToken = _tapToken;

38 | maxLockedUntil = _maxLockedUntil;
```


*GitHub* : [36](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L36),[38](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L38)
### [gas-04]<a name="gas-04"></a> Optimize names to save gas
`public`/`external` function names and `public` member variable names can be optimized to save gas. The interfaces/abstract contracts below can be optimized so that the most frequently-called functions use the least amount of gas possible during method lookup. Method IDs with two leading zero bytes can save **128 gas** each during deployment, and renaming functions with lower method IDs will save **22 gas** per call, [per sorted position shifted](https://medium.com/joyso/solidity-how-does-function-name-affect-gas-consumption-in-smart-contract-47d270d8ac92).

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

// @audit: addCollateral(), removeCollateral()
8 | contract SGLCollateral is SGLLendingCommon {
```


*GitHub* : [8](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L8)

```solidity
File: contracts/tokens/LTap.sol

// @audit: deposit(), redeem(), setLockedUntil()
23 | contract LTap is BoringOwnable, ERC20Permit {
```


*GitHub* : [23](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L23)
### [gas-05]<a name="gas-05"></a> Avoid unnecessary storage updates
Updating storage only when the value has changed can help avoid a Gsreset (2900 gas) at the cost of a Gcoldsload (2100 gas) or a Gwarmaccess (100 gas). Therefore, it is recommended to verify if the old value is equal to the new value before updating the storage.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

55 | lockedUntil = _lockedUntil;
```


*GitHub* : [55](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L55)
### [gas-06]<a name="gas-06"></a> Reduce gas usage by upgrading to Solidity 0.8.19 or later
Click [here](https://blog.soliditylang.org/2023/02/22/solidity-0.8.19-release-announcement/#preventing-dead-code-in-runtime-bytecode) for complete details.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/markets/singularity/SGLCollateral.sol

2 | pragma solidity ^0.8.18;
```


*GitHub* : [2](https://github.com/Tapioca-DAO/tapioca-bar-audit/blob/master/contracts/markets/singularity/SGLCollateral.sol#L2)

```solidity
File: contracts/tokens/LTap.sol

2 | pragma solidity ^0.8.18;
```


*GitHub* : [2](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L2)
### [gas-07]<a name="gas-07"></a> Restricted functions can be marked as `payable`

If a function modifier such as `onlyOwner` is applied, the function will revert if a regular user attempts to pay. By marking the function as `payable`, gas cost for legitimate callers will be reduced as the compiler omits checks for payment existence.

*There are 1 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

53 | function setLockedUntil(uint256 _lockedUntil) external onlyOwner {
```


*GitHub* : [53](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L53)
### [gas-08]<a name="gas-08"></a> Utilize Custom Errors for Cost-Effective Deployment and Runtime
[Source](https://blog.soliditylang.org/2021/04/21/custom-errors/) By employing Custom Errors instead of error strings, you can effectively minimize both deployment and runtime expenses.

*There are 2 instance(s) of this issue:*

```solidity
File: contracts/tokens/LTap.sol

47 | require(block.timestamp > lockedUntil, "Still locked");

54 | require(_lockedUntil <= maxLockedUntil, "Too late");
```


*GitHub* : [47](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L47),[54](https://github.com/Tapioca-DAO/tap-token-audit/blob/main/contracts/tokens/LTap.sol#L54) 
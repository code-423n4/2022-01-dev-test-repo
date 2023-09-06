# Report Generated for: Code4rena Test large data file
## Generated on: N/A 

## Testing

## Total findings: 107

### Total GAS findings: 30

### Total NC findings: 48

### Total LOW findings: 19

### Total MEDIUM findings: 10

### Total HIGH findings: 0
# Summary for MEDIUM findings

| Number | Details | Instances |
|----------|----------|----------|
| [MEDIUM-1] | SafeTransfer should be used in place of transfer | 2 |
| [MEDIUM-2] | Privileged functions can create points of failure | 6 |
| [MEDIUM-3] | Contracts are vulnerable to fee-on-transfer accounting-related issues | 2 |
| [MEDIUM-4] | Gas grief possible on unsafe external calls  | 1 |
| [MEDIUM-5] | Return values of transfer()/transferFrom() not checked | 4 |
| [MEDIUM-6] | Some tokens may revert when zero value transfers are made | 1 |
| [MEDIUM-7] | Remaining eth may not be refunded to users | 1 |
| [MEDIUM-8] | Function which returns data from a call has no validation | 1 |
| [MEDIUM-9] | Polygon chain reorgs affect Chainlink randomness  | 1 |
| [MEDIUM-10] | Divide before multiply | 7 |
# Summary for LOW findings

| Number | Details | Instances |
|----------|----------|----------|
| [LOW-1] | Int casting block.timestamp can reduce the lifespan of a contract | 1 |
| [LOW-2] | Potential division by zero should have zero checks in place | 2 |
| [LOW-4] | The call abi.encodeWithSelector is not type safe | 2 |
| [LOW-6] | Double type casts create complexity within the code | 1 |
| [LOW-7] | Use SafeCast to safely downcast variables | 9 |
| [LOW-8] | Functions which set address state variables should have zero address checks | 3 |
| [LOW-9] | Function calls within for loops | 1 |
| [LOW-10] | For loops in public or external functions should be avoided due to high gas costs and possible DOS | 1 |
| [LOW-11] | Unbounded state variable arrays exist within the project which are iterated upon  | 1 |
| [LOW-12] | Contracts do not use their OZ upgradable counterparts | 1 |
| [LOW-13] | Loss of precision | 2 |
| [LOW-14] | Missing zero address check in constructor | 9 |
| [LOW-15] | Use of onlyOwner functions can be lost | 2 |
| [LOW-16] | Using zero as a parameter | 1 |
| [LOW-17] | Solidity version 0.8.20 won't work on all chains due to PUSH0 | 13 |
| [LOW-18] | Arrays can grow in size without a way to shrink them | 1 |
| [LOW-19] | Functions calling contracts/addresses with transfer hooks are missing reentrancy guards | 2 |
| [LOW-20] | Revert on Transfer to the Zero Address | 1 |
| [LOW-21] | Constructors contains no validation | 4 |
# Summary for NC findings

| Number | Details | Instances |
|----------|----------|----------|
| [NC-1] | Floating pragma should be avoided | 13 |
| [NC-2] | Empty function blocks | 1 |
| [NC-3] | Events regarding state variable changes should emit the previous state variable value | 2 |
| [NC-4] | In functions which accept an address as a parameter, there should be a zero address check to prevent bugs | 19 |
| [NC-5] | Enum values should be used in place of constant array indexes | 2 |
| [NC-6] | Zero address checks should be present in constructors which take address(es) as parameters | 5 |
| [NC-7] | Ownable2Step should be used in place of Ownable | 2 |
| [NC-8] | Functions which are either private or internal should have a preceding _ in their name | 8 |
| [NC-9] | Public state variables shouldn't have a preceding _ in their name | 6 |
| [NC-10] | Contract lines should not be longer than 110 characters for readability | 14 |
| [NC-11] | Specific imports should be used where possible so only used code is imported | 3 |
| [NC-12] | Use newer solidity versions | 4 |
| [NC-13] | Not all event definitions are utilizing indexed variables. | 9 |
| [NC-14] | Explicitly define visibility of state variables to prevent misconceptions on what can access the variable | 6 |
| [NC-15] | Function names should differ to make the code more readable | 10 |
| [NC-16] | It is standard for all external and public functions to be override from an interface | 57 |
| [NC-17] | uint variables should have the bit size defined explicitly | 4 |
| [NC-18] | Functions within contracts are not ordered according to the solidity style guide | 1 |
| [NC-19] | Emits without msg.sender parameter | 4 |
| [NC-20] | Functions with array parameters should have length checks in place | 3 |
| [NC-21] | Interface imports should be declared first | 34 |
| [NC-22] | A function which defines named returns in it's declaration doesn't need to use return  | 1 |
| [NC-23] | Unused state variables present | 1 |
| [NC-24] | Constants should be on the left side of the  | 14 |
| [NC-25] | Both immutable and constant state variables should be CONSTANT_CASE | 14 |
| [NC-26] | Consider using named mappings | 2 |
| [NC-27] | Default address(0) can be returned | 4 |
| [NC-28] | Critical functions should be a two step procedure | 5 |
| [NC-29] | Address values should be used through variables rather than used as literals | 11 |
| [NC-30] | Mixed usage of int/uint with int256/uint256 | 5 |
| [NC-31] | Consider adding emergency-stop functionality | 11 |
| [NC-32] | Remove forge-std import | 1 |
| [NC-33] | Some if-statement can be converted to a ternary | 2 |
| [NC-34] | File is missing NatSpec | 1 |
| [NC-35] | Addresses shouldn't be hard-coded | 7 |
| [NC-36] | Empty bytes check is missing | 2 |
| [NC-37] | It's not standard to end and begin a code object on the same line | 36 |
| [NC-38] | Function missing natspec comments | 5 |
| [NC-39] | NatSpec @param is missing | 11 |
| [NC-40] | NatSpec @return argument is missing | 5 |
| [NC-41] | Natspec @title is missing from contract/interface/library | 1 |
| [NC-42] | Natspec @author is missing from contract/interface/library | 1 |
| [NC-43] | Assembly code blocks should be thoroughly commented | 1 |
| [NC-44] | Return bool not explicit | 1 |
| [NC-45] | Do not use underscore at the end of variable name | 5 |
| [NC-46] | Consider using SMTChecker | 17 |
| [NC-47] | Contracts should have full test coverage | 1 |
| [NC-48] | Consider using SafeTransferLib.safeTransferETH() or Address.sendValue() for clearer semantic meaning | 2 |
# Summary for GAS findings

| Number | Details | Instances | Gas |
|----------|----------|----------|----------|
| [GAS-1] | It is more efficient to use block.timestamp directly rather than calling a function to return it | 1 |  -  |
| [GAS-2] | The use of a logical AND in place of double if is slightly less gas efficient in instances where there isn't a corresponding else statement for the given if statement | 4 | 60 |
| [GAS-3] | x + y is more efficient than using += for state variables (likewise for -=) | 3 | 15 |
| [GAS-4] | Calling .length in a for loop wastes gas | 1 | 97 |
| [GAS-5] | ++X costs slightly less gas than X++ (same with --) | 2 | 10 |
| [GAS-6] | Internal functions only used once can be inlined so save gas | 11 | 330 |
| [GAS-7] | Solidity version 0.8.19 is more gas efficient | 2 | 2000 |
| [GAS-8] | Constructors can be marked as payable to save deployment gas | 9 |  -  |
| [GAS-9] | Usage of smaller uint/int types causes overhead | 42 | 2310 |
| [GAS-10] | Avoid updating storage when the value hasn't changed | 3 | 2400 |
| [GAS-11] | Use != 0 instead of > 0 | 6 | 18 |
| [GAS-12] | Integer increments by one can be unchecked to save on gas fees | 2 | 240 |
| [GAS-13] | Default int values are manually reset | 5 |  -  |
| [GAS-14] | <= or >= is more efficient than < or >  | 1 | 3 |
| [GAS-15] | State variables used within a function more than once should be cached to save gas | 15 | 1500 |
| [GAS-16] | Mappings used within a function more than once should be cached to save gas | 6 | 600 |
| [GAS-17] | Use assembly to check for the zero address | 5 |  -  |
| [GAS-18] | Use storage instead of memory for structs/arrays | 3 | 12600 |
| [GAS-19] | Can transfer 0 | 1 |  -  |
| [GAS-20] | Redundant state variable getters | 2 |  -  |
| [GAS-21] | State variables which are not modified within functions should be set as constants or immutable for values set at deployment | 1 |  -  |
| [GAS-22] | Redundant else statement | 1 |  -  |
| [GAS-23] | Don't use _msgSender() if not supporting EIP-2771 | 1 | 16 |
| [GAS-24] | Unbounded Gas Consumption Risk Due to External Call Recipients | 1 |  -  |
| [GAS-25] | Consider activating via-ir for deploying | 17 | 4250 |
| [GAS-26] | The result of a function call should be cached rather than re-calling the function | 19 | 1900 |
| [GAS-28] | Add unchecked {} for subtractions where the operands cannot underflow | 3 | 255 |
| [GAS-29] | Use bitmap to save gas | 1 | 70 |
| [GAS-30] | Use assembly to emit events | 17 | 646 |
| [GAS-31] | Shorten the array rather than copying to a new one | 2 |  -  |

# [MEDIUM-1] SafeTransfer should be used in place of transfer
## Number of instances found
 2 

## Resolution
 SafeTransfer should be used in place of Transfer for Solidity contracts to ensure robust security and error handling. Unlike the basic Transfer function, SafeTransfer incorporates safeguards against potential smart contract vulnerabilities, such as unexpected token loss. By automatically validating the recipient's ability to receive tokens and reverting transactions in case of failures,  

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L193-L193
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner {
189:     uint256 availableBoost = _accrue(_token);
190:     uint256 availableBalance = _token.balanceOf(address(this));
191:     uint256 remainingBalance = availableBalance - _amount;
192:     _boosts[IERC20(_token)].available = (availableBoost > remainingBalance ? remainingBalance : availableBoost).toUint144();
193:     _token.transfer(msg.sender, _amount); // <= FOUND
194: 
195:     emit Withdrawn(_token, msg.sender, _amount);
196:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L182-L182
```javascript
170:   function startRngRequest(address _rewardRecipient) external {
171:     if (!_canStartNextSequence()) revert CannotStartNextSequence();
172: 
173:     RNGInterface rng = _nextRng;
174: 
175:     uint64 _auctionElapsedTimeSeconds = _auctionElapsedTime();
176:     if (_auctionElapsedTimeSeconds > auctionDuration) revert AuctionExpired();
177: 
178:     (address _feeToken, uint256 _requestFee) = rng.getRequestFee();
179:     if (_feeToken != address(0) && _requestFee > 0) {
180:       if (IERC20(_feeToken).balanceOf(address(this)) < _requestFee) {
181:         
182:         IERC20(_feeToken).transferFrom(msg.sender, address(this), _requestFee); // <= FOUND
183:       }
184:       
185:       IERC20(_feeToken).safeIncreaseAllowance(address(rng), _requestFee);
186:     }
187: 
188:     (uint32 rngRequestId,) = rng.requestRandomNumber();
189:     uint32 sequenceId = _openSequenceId();
190:     UD2x18 rewardFraction = _currentFractionalReward();
191: 
192:     _lastAuction = RngAuctionResult({
193:       recipient: _rewardRecipient,
194:       rewardFraction: rewardFraction,
195:       sequenceId: sequenceId,
196:       rng: rng,
197:       rngRequestId: rngRequestId
198:     });
199: 
200:     emit RngAuctionCompleted(
201:       _rewardRecipient,
202:       sequenceId,
203:       rng,
204:       rngRequestId,
205:       _auctionElapsedTimeSeconds,
206:       rewardFraction

```


</details>


# [MEDIUM-2] Privileged functions can create points of failure
## Number of instances found
 6 

## Resolution
 Ensure such accounts are protected and consider implementing multi sig to prevent a single point of failure 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L347-L347
```javascript
347:   function setNextRngService(RNGInterface _rngService) external onlyOwner  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L188-L188
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner  // <= FOUND

```


</details>


# [MEDIUM-3] Contracts are vulnerable to fee-on-transfer accounting-related issues
## Number of instances found
 2 

## Resolution
 The below-listed functions use `transferFrom()` to move funds from the sender to the recipient but fail to verify if the received token amount matches the transferred amount. This could pose an issue with fee-on-transfer tokens, where the post-transfer balance might be less than anticipated, leading to balance inconsistencies. There might be subsequent checks for a second transfer, but an attacker might exploit leftover funds (such as those accidentally sent by another user) to gain unjustified credit. A practical solution is to gauge the balance prior and post-transfer, and consider the differential as the transferred amount, instead of the predefined amount. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>




https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L173-L173
```javascript
171:   function deposit(IERC20 _token, uint256 _amount) external {
172:     _accrue(_token);
173:     _token.safeTransferFrom(msg.sender, address(this), _amount); // <= FOUND
174: 
175:     emit Deposited(_token, msg.sender, _amount);
176:   }

```


</details>


# [MEDIUM-4] Gas grief possible on unsafe external calls 
## Number of instances found
 1 

## Resolution
 In Solidity, the use of low-level `call` methods can expose contracts to gas griefing attacks. The potential problem arises when the callee contract returns a large amount of data. This data is allocated in the memory of the calling contract, which pays for the gas costs. If the callee contract intentionally returns an enormous amount of data, the gas costs can skyrocket, causing the transaction to fail due to an Out of Gas error. Therefore, it's advisable to limit the use of `call` when interacting with untrusted contracts, or ensure that the callee's returned data size is capped or known in advance to prevent unexpected high gas costs. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L39-L39
```javascript
34:     function relay(
35:         IRngAuctionRelayListener _rngAuctionRelayListener,
36:         address _relayRewardRecipient
37:     ) external returns (bytes memory) {
38:         bytes memory data = encodeCalldata(_relayRewardRecipient);
39:         (bool success, bytes memory returnData) = address(_rngAuctionRelayListener).call(data); // <= FOUND
40:         if (!success) {
41:             revert DirectRelayFailed(returnData);
42:         }
43:         emit DirectRelaySuccess(_relayRewardRecipient, returnData);
44:         return returnData;
45:     }

```


</details>


# [MEDIUM-5] Return values of transfer()/transferFrom() not checked
## Number of instances found
 4 

## Resolution
 In Solidity, it's crucial to check the return value of `.transfer` and `.transferFrom` methods because not all ERC20 token implementations revert on failure. Notably, If these methods fail silently and the contract doesn't verify their return value, the contract might continue execution as if the tokens were transferred successfully, leading to incorrect balances, loss of funds, or other unexpected behaviors. Therefore, the return values of these methods should always be checked, ensuring a failed token transfer operation correctly halts the execution of the contract. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L170-L182
```javascript
170:   function startRngRequest(address _rewardRecipient) external { // <= FOUND
171:     if (!_canStartNextSequence()) revert CannotStartNextSequence();
172: 
173:     RNGInterface rng = _nextRng;
174: 
175:     uint64 _auctionElapsedTimeSeconds = _auctionElapsedTime();
176:     if (_auctionElapsedTimeSeconds > auctionDuration) revert AuctionExpired();
177: 
178:     (address _feeToken, uint256 _requestFee) = rng.getRequestFee();
179:     if (_feeToken != address(0) && _requestFee > 0) {
180:       if (IERC20(_feeToken).balanceOf(address(this)) < _requestFee) {
181:         
182:         IERC20(_feeToken).transferFrom(msg.sender, address(this), _requestFee); // <= FOUND
183:       }
184:       
185:       IERC20(_feeToken).safeIncreaseAllowance(address(rng), _requestFee);
186:     }
187: 
188:     (uint32 rngRequestId,) = rng.requestRandomNumber();
189:     uint32 sequenceId = _openSequenceId();
190:     UD2x18 rewardFraction = _currentFractionalReward();
191: 
192:     _lastAuction = RngAuctionResult({
193:       recipient: _rewardRecipient,
194:       rewardFraction: rewardFraction,
195:       sequenceId: sequenceId,
196:       rng: rng,
197:       rngRequestId: rngRequestId
198:     });
199: 
200:     emit RngAuctionCompleted(
201:       _rewardRecipient,
202:       sequenceId,
203:       rng,
204:       rngRequestId,
205:       _auctionElapsedTimeSeconds,
206:       rewardFraction

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L188-L193
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner { // <= FOUND
189:     uint256 availableBoost = _accrue(_token);
190:     uint256 availableBalance = _token.balanceOf(address(this));
191:     uint256 remainingBalance = availableBalance - _amount;
192:     _boosts[IERC20(_token)].available = (availableBoost > remainingBalance ? remainingBalance : availableBoost).toUint144();
193:     _token.transfer(msg.sender, _amount); // <= FOUND
194: 
195:     emit Withdrawn(_token, msg.sender, _amount);
196:   }

```


</details>


# [MEDIUM-6] Some tokens may revert when zero value transfers are made
## Number of instances found
 1 

## Resolution
 Reason: In Solidity, ERC20 token transfers of value 0 can sometimes lead to unexpected issues. This is particularly relevant when dealing with fractional token amounts that round to 0 when less than 1 of the smallest unit is transferred, leading to an effective transfer of nothing while still consuming gas. Furthermore, some ERC20 token implementations may revert on attempts to transfer a value of 0. However, note that this issue doesn't generally apply to wrapper native tokens like WETH.

Resolution: It's advisable to include a condition before any transfer operation to bypass the transaction if the transfer amount is 0. This saves unnecessary gas expenditure and prevents potential function reverts. For handling fractions, ensure token decimals are appropriately assigned and contemplate setting a minimum transfer threshold to avoid rounding down to 0. When dealing with wrapped tokens like WETH, special consideration should be given to their unique characteristics. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L188-L193
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner {
189:     uint256 availableBoost = _accrue(_token);
190:     uint256 availableBalance = _token.balanceOf(address(this));
191:     uint256 remainingBalance = availableBalance - _amount;
192:     _boosts[IERC20(_token)].available = (availableBoost > remainingBalance ? remainingBalance : availableBoost).toUint144();
193:     _token.transfer(msg.sender, _amount); // <= FOUND
194: 
195:     emit Withdrawn(_token, msg.sender, _amount);
196:   }

```


</details>


# [MEDIUM-7] Remaining eth may not be refunded to users
## Number of instances found
 1 

## Resolution
 When a contract function accepts Ethereum and executes a `.call()` or similar function that also forwards Ethereum value, it's important to check for and refund any remaining balance. This is because some of the supplied value may not be used during the call execution due to gas constraints, a revert in the called contract, or simply because not all the value was needed.

If you do not account for this remaining balance, it can become "locked" in the contract. It's crucial to either return the remaining balance to the sender or handle it in a way that ensures it is not permanently stuck. Neglecting to do so can lead to loss of funds and degradation of the contract's reliability. Furthermore, it's good practice to ensure fairness and trust with your users by returning unused funds. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L63-L67
```javascript
63:   function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) {
64:     
65:     
66:     _checkSender();
67:     (bool success, bytes memory returnData) = target.call{ value: value }(data); // <= FOUND
68:     
69:     
70:     
71:     if (!success) revert CallFailed(returnData);
72:     assembly {
73:       return (add(returnData, 0x20), mload(returnData))
74:     }
75:   }

```


</details>


# [MEDIUM-8] Function which returns data from a call has no validation
## Number of instances found
 1 

## Resolution
 In Solidity, when `call` or `delegatecall` is used to interact with another contract, it's possible that the called contract function doesn't return any data. This could be due to various reasons, such as the function is not implemented, or the function encountered an error. If the calling contract then tries to directly access elements in the returned data without first checking the length of the returned data, it could lead to a runtime error, or in some cases, incorrect logic execution.

Therefore, it's advisable to have a length check and revert the transaction if `results.length` is 0. This ensures the function doesn't proceed with potentially unsafe or invalid data. It also provides a clear error message to the caller, indicating that the called function did not return any data, which assists in troubleshooting. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L44-L44
```javascript
34:     function relay(
35:         IRngAuctionRelayListener _rngAuctionRelayListener,
36:         address _relayRewardRecipient
37:     ) external returns (bytes memory) {
38:         bytes memory data = encodeCalldata(_relayRewardRecipient);
39:         (bool success, bytes memory returnData) = address(_rngAuctionRelayListener).call(data);
40:         if (!success) {
41:             revert DirectRelayFailed(returnData);
42:         }
43:         emit DirectRelaySuccess(_relayRewardRecipient, returnData);
44:         return returnData; // <= FOUND
45:     }

```


</details>


# [MEDIUM-9] Polygon chain reorgs affect Chainlink randomness 
## Number of instances found
 1 

## Resolution
 The requestConfirmations value in VRFv2Consumer is currently set to a low number. This value is critical as it communicates to the Chainlink VRF service the minimum number of blocks to wait before providing randomness. Its purpose is to mitigate the impact of chain reorganizations, events where block and transaction orders are rearranged, thus changing their output. This issue is particularly relevant for applications slated for deployment on Polygon, as referenced in the README.md, given the frequency and depth of reorganizations on this network, often exceeding 3 blocks. Even more alarmingly, a recent event revealed a chain reorganization on Polygon with a depth of 156 blocks. This scenario could lead to the possibility of changing the winner of a lootbox game. If a transaction requesting randomness from VRF is displaced to a different block due to a reorganization, the resultant randomness would also change. Hence, it may be prudent to revisit and adjust the REQUEST_CONFIRMATION constant to a higher value to ensure consistent and accurate outcomes. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L188-L188
```javascript
188:     (uint32 rngRequestId,) = rng.requestRandomNumber(); // <= FOUND

```


</details>


# [MEDIUM-10] Divide before multiply
## Number of instances found
 7 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L33-L41
```javascript
23:   function purchasePrice(
24:     SD59x18 _amount,
25:     SD59x18 _emissionRate,
26:     SD59x18 _k,
27:     SD59x18 _decayConstant,
28:     SD59x18 _timeSinceLastAuctionStart
29:   ) internal pure returns (SD59x18) {
30:     if (_amount.unwrap() == 0) {
31:       return SD59x18.wrap(0);
32:     }
33:     SD59x18 topE = _decayConstant.mul(_amount).div(_emissionRate); 
34:     topE = topE.exp().sub(ONE);
35:     SD59x18 bottomE = _decayConstant.mul(_timeSinceLastAuctionStart);
36:     bottomE = bottomE.exp();
37:     SD59x18 result;
38:     if (_emissionRate.unwrap() > 1e18) {
39:       result = _k.div(_emissionRate).mul(topE).div(bottomE); 
40:     } else {
41:       result = _k.mul(topE.div(_emissionRate.mul(bottomE))); // <= FOUND
42:     }
43:     return result;
44:   }

```


</details>


# [LOW-1] Int casting block.timestamp can reduce the lifespan of a contract
## Number of instances found
 1 

## Resolution
 Consider removing casting to ensure future functionality. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L273-L273
```javascript
262:   function _computeAvailable(IERC20 _tokenOut) internal view returns (uint256) {
263:     Boost memory boost = _boosts[_tokenOut];
264:     uint256 deltaTime = block.timestamp - boost.lastAccruedAt;
265:     uint256 deltaAmount;
266:     if (deltaTime == 0) {
267:       return boost.available;
268:     }
269:     if (boost.tokensPerSecond > 0) {
270:       deltaAmount = boost.tokensPerSecond * deltaTime;
271:     }
272:     if (boost.multiplierOfTotalSupplyPerSecond.unwrap() > 0) {
273:       uint256 totalSupply = twabController.getTotalSupplyTwabBetween(address(vault), uint32(boost.lastAccruedAt), uint32(block.timestamp)); // <= FOUND
274:       deltaAmount += convert(boost.multiplierOfTotalSupplyPerSecond.intoUD60x18().mul(convert(deltaTime)).mul(convert(totalSupply)));
275:     }
276:     uint256 availableBalance = _tokenOut.balanceOf(address(this));
277:     deltaAmount = availableBalance > deltaAmount ? deltaAmount : availableBalance;
278:     return boost.available + deltaAmount;
279:   }

```


</details>


# [LOW-2] Potential division by zero should have zero checks in place
## Number of instances found
 2 

## Resolution
 Implement a zero address check for found instances 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L382-L382
```javascript
377:   function _computePeriod() internal view returns (uint256) {
378:     uint256 _timestamp = block.timestamp;
379:     if (_timestamp < periodOffset) {
380:       return 0;
381:     }
382:     return (_timestamp - periodOffset) / periodLength; // <= FOUND
383:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L374-L374
```javascript
365:   function _openSequenceId() internal view returns (uint32) {
366:     
367: 
368: 
369: 
370:     uint64 currentTime = _currentTime();
371:     if (currentTime < sequenceOffset) {
372:       return 0;
373:     }
374:     return uint32((currentTime - sequenceOffset) / sequencePeriod); // <= FOUND
375:   }

```


</details>



# [LOW-4] The call abi.encodeWithSelector is not type safe
## Number of instances found
 2 

## Resolution
 The call abi.encodeCall shout be used instead. Note abi.encodeCall is only safe from typographical errors in solidity versions 0.8.13 and above 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L37-L37
```javascript
31:     function encodeCalldata(address rewardRecipient) internal returns (bytes memory) {
32:         if (!rngAuction.isRngComplete()) revert RngNotCompleted();
33:         (uint256 randomNumber, uint64 rngCompletedAt) = rngAuction.getRngResults();
34:         AuctionResult memory results = rngAuction.getLastAuctionResult();
35:         uint32 sequenceId = rngAuction.openSequenceId();
36:         results.recipient = remappingOf(results.recipient);
37:         return abi.encodeWithSelector(IRngAuctionRelayListener.rngComplete.selector, randomNumber, rngCompletedAt, rewardRecipient, sequenceId, results); // <= FOUND
38:     }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L8-L8
```javascript
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
8:         return abi.encodeWithSelector( // <= FOUND
9:             RemoteOwner.execute.selector,
10:             target,
11:             value,
12:             data
13:         );
14:         
15:         
16:         
17:     }

```


</details>




# [LOW-6] Double type casts create complexity within the code
## Number of instances found
 1 

## Resolution
 Double type casting should be avoided in Solidity contracts to prevent unintended consequences and ensure accurate data representation. Performing multiple type casts in succession can lead to unexpected truncation, rounding errors, or loss of precision, potentially compromising the contract's functionality and reliability. Furthermore, double type casting can make the code less readable and harder to maintain, increasing the likelihood of errors and misunderstandings during development and debugging. To ensure precise and consistent data handling, developers should use appropriate data types and avoid unnecessary or excessive type casting, promoting a more robust and dependable contract execution. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L223-L223
```javascript
223:     _lastAuctionTime += uint48(uint256(convert(convert(int256(_amountOut)).div(_emissionRate)))); // <= FOUND

```


</details>


# [LOW-7] Use SafeCast to safely downcast variables
## Number of instances found
 9 

## Resolution
 Downcasting int/uints in Solidity can be unsafe due to the potential for data loss and unintended behavior. When downcasting a larger integer type to a smaller one (e.g., uint256 to uint128), the value may exceed the range of the target type, leading to truncation and loss of significant digits. This data loss can result in unexpected state changes, incorrect calculations, or other contract vulnerabilities, ultimately compromising the contracts functionality and reliability. To prevent these risks, developers should carefully consider the range of values their variables may hold and ensure that proper checks are in place to prevent out-of-range values before performing downcasting. Also consider using OZ SafeCast functionality. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L339-L340
```javascript
331:   function _updateAuction(uint256 __period) internal {
332:     if (_amountInForPeriod > 0 && _amountOutForPeriod > 0) {
333:       
334:       _lastNonZeroAmountIn = _amountInForPeriod;
335:       _lastNonZeroAmountOut = _amountOutForPeriod;
336:     }
337:     _amountInForPeriod = 0;
338:     _amountOutForPeriod = 0;
339:     _lastAuctionTime = uint48(periodOffset + periodLength * __period); // <= FOUND
340:     _period = uint16(__period); // <= FOUND
341:     SD59x18 emissionRate_ = _computeEmissionRate();
342:     _emissionRate = emissionRate_;
343:     if (_emissionRate.unwrap() != 0) {
344:       
345:       SD59x18 timeSinceLastAuctionStart = convert(int(uint(targetFirstSaleTime)));
346:       SD59x18 purchaseAmount = timeSinceLastAuctionStart.mul(emissionRate_);
347:       SD59x18 exchangeRateAmountInToAmountOut = convert(int(uint(_lastNonZeroAmountIn))).div(convert(int(uint(_lastNonZeroAmountOut))));
348:       SD59x18 price = exchangeRateAmountInToAmountOut.mul(purchaseAmount);
349:       _initialPrice = ContinuousGDA.computeK(
350:         emissionRate_,
351:         decayConstant,
352:         timeSinceLastAuctionStart,
353:         purchaseAmount,
354:         price
355:       );
356:     } else {
357:       _initialPrice = wrap(0);
358:     }
359:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L282-L282
```javascript
274:   function _computeEmissionRate() internal returns (SD59x18) {
275:     uint256 amount = source.liquidatableBalanceOf(tokenOut);
276:     
277:     if (amount < minimumAuctionAmount) {
278:       
279:       amount = 0;
280:       
281:     }
282:     return convert(int256(amount)).div(convert(int32(int(periodLength)))); // <= FOUND
283:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L374-L374
```javascript
365:   function _openSequenceId() internal view returns (uint32) {
366:     
367: 
368: 
369: 
370:     uint64 currentTime = _currentTime();
371:     if (currentTime < sequenceOffset) {
372:       return 0;
373:     }
374:     return uint32((currentTime - sequenceOffset) / sequencePeriod); // <= FOUND
375:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L221-L223
```javascript
211:   function swapExactAmountOut(
212:     address _account,
213:     uint256 _amountOut,
214:     uint256 _amountInMax
215:   ) external returns (uint256) {
216:     _checkUpdateAuction();
217:     uint swapAmountIn = _computeExactAmountIn(_amountOut);
218:     if (swapAmountIn > _amountInMax) {
219:       revert SwapExceedsMax(_amountInMax, swapAmountIn);
220:     }
221:     _amountInForPeriod += uint96(swapAmountIn); // <= FOUND
222:     _amountOutForPeriod += uint96(_amountOut); // <= FOUND
223:     _lastAuctionTime += uint48(uint256(convert(convert(int256(_amountOut)).div(_emissionRate)))); // <= FOUND
224:     source.liquidate(_account, tokenIn, swapAmountIn, tokenOut, _amountOut);
225:     return swapAmountIn;
226:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L45-L45
```javascript
25:   function fractionalReward(
26:     uint64 _elapsedTime,
27:     uint64 _auctionDuration,
28:     UD2x18 _targetTimeFraction,
29:     UD2x18 _targetRewardFraction
30:   ) internal pure returns (UD2x18) {
31:     UD60x18 x = convert(_elapsedTime).div(convert(_auctionDuration));
32:     UD60x18 t = UD60x18.wrap(_targetTimeFraction.unwrap());
33:     UD60x18 r = UD60x18.wrap(_targetRewardFraction.unwrap());
34:     UD60x18 rewardFraction;
35:     if (x.gt(t)) {
36:       UD60x18 tDelta = x.sub(t);
37:       UD60x18 oneMinusT = convert(1).sub(t);
38:       rewardFraction = r.add(
39:         convert(1).sub(r).mul(tDelta).mul(tDelta).div(oneMinusT).div(oneMinusT)
40:       );
41:     } else {
42:       UD60x18 tDelta = t.sub(x);
43:       rewardFraction = r.sub(r.mul(tDelta).mul(tDelta).div(t).div(t));
44:     }
45:     return UD2x18.wrap(uint64(rewardFraction.unwrap())); // <= FOUND
46:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L192-L192
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner {
189:     uint256 availableBoost = _accrue(_token);
190:     uint256 availableBalance = _token.balanceOf(address(this));
191:     uint256 remainingBalance = availableBalance - _amount;
192:     _boosts[IERC20(_token)].available = (availableBoost > remainingBalance ? remainingBalance : availableBoost).toUint144(); // <= FOUND
193:     _token.transfer(msg.sender, _amount);
194: 
195:     emit Withdrawn(_token, msg.sender, _amount);
196:   }

```


</details>


# [LOW-8] Functions which set address state variables should have zero address checks
## Number of instances found
 3 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L103-L103
```javascript
103:   function _setOriginChainOwner(address _newOriginChainOwner) internal {
104:     if (_newOriginChainOwner == address(0)) revert OriginChainOwnerZeroAddress();
105: 
106:     _originChainOwner = _newOriginChainOwner;
107: 
108:     emit OriginChainOwnerSet(_newOriginChainOwner);
109:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner {
143:     if (_initialAvailable > 0) {
144:       uint256 balance = _token.balanceOf(address(this));
145:       if (balance < _initialAvailable) {
146:         revert InitialAvailableExceedsBalance(_initialAvailable, balance);
147:       }
148:     }
149:     _boosts[_token] = Boost({
150:       liquidationPair: _liquidationPair,
151:       multiplierOfTotalSupplyPerSecond: _multiplierOfTotalSupplyPerSecond,
152:       tokensPerSecond: _tokensPerSecond,
153:       available: _initialAvailable,
154:       lastAccruedAt: uint48(block.timestamp)
155:     });
156: 
157:     emit SetBoost(
158:       _token,
159:       _liquidationPair,
160:       _multiplierOfTotalSupplyPerSecond,
161:       _tokensPerSecond,
162:       _initialAvailable,
163:       uint48(block.timestamp)
164:     );
165:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L96-L96
```javascript
96:   function setOriginChainOwner(address _newOriginChainOwner) external {
97:     _checkSender();
98:     _setOriginChainOwner(_newOriginChainOwner);
99:   }

```


</details>


# [LOW-9] Function calls within for loops
## Number of instances found
 1 

## Resolution
 Making function calls or external calls within loops in Solidity can lead to inefficient gas usage, potential bottlenecks, and increased vulnerability to attacks. Each function call or external call consumes gas, and when executed within a loop, the gas cost multiplies, potentially causing the transaction to run out of gas or exceed block gas limits. This can result in transaction failure or unpredictable behavior. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L66-L66
```javascript
65:    for (uint256 i; i < _auctionResultsLength; i++) {
66:       _rewards[i] = reward(_auctionResults[i], remainingReserve); // <= FOUND
67:       remainingReserve = remainingReserve - _rewards[i];
68:     }

```


</details>


# [LOW-10] For loops in public or external functions should be avoided due to high gas costs and possible DOS
## Number of instances found
 1 

## Resolution
 In Solidity, for loops can potentially cause Denial of Service (DoS) attacks if not handled carefully. DoS attacks can occur when an attacker intentionally exploits the gas cost of a function, causing it to run out of gas or making it too expensive for other users to call. Below are some scenarios where for loops can lead to DoS attacks: Nested for loops can become exceptionally gas expensive and should be used sparingly 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L167-L167
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) {
138:     if (_sequenceHasCompleted(_sequenceId)) revert SequenceAlreadyCompleted();
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt);
140:     if (_auctionElapsedSeconds > (_auctionDurationSeconds-1)) revert AuctionExpired();
141:     
142:     UD2x18 rewardFraction = _fractionalReward(_auctionElapsedSeconds);
143:     _auctionResults.rewardFraction = rewardFraction;
144:     _auctionResults.recipient = _rewardRecipient;
145:     _lastSequenceId = _sequenceId;
146: 
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2);
148:     auctionResults[0] = _rngAuctionResult;
149:     auctionResults[1] = AuctionResult({
150:       rewardFraction: rewardFraction,
151:       recipient: _rewardRecipient
152:     });
153: 
154:     uint32 drawId = prizePool.closeDraw(_randomNumber);
155: 
156:     uint256 futureReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
157:     uint256[] memory _rewards = RewardLib.rewards(auctionResults, futureReserve);
158: 
159:     emit RngSequenceCompleted(
160:       _sequenceId,
161:       drawId,
162:       _rewardRecipient,
163:       _auctionElapsedSeconds,
164:       rewardFraction
165:     );
166: 
167:     for (uint8 i = 0; i < _rewards.length; i++) { // <= FOUND
168:       uint104 _reward = uint104(_rewards[i]);
169:       if (_reward > 0) {
170:         prizePool.withdrawReserve(auctionResults[i].recipient, _reward);
171:         emit AuctionRewardDistributed(_sequenceId, auctionResults[i].recipient, i, _reward);
172:       }
173:     }
174: 
175:     return bytes32(uint(drawId));
176:   }

```


</details>


# [LOW-11] Unbounded state variable arrays exist within the project which are iterated upon 
## Number of instances found
 1 

## Resolution
 Unbounded arrays in Solidity can cause gas-related issues due to their potential for excessive growth, leading to increased computational complexity and resource consumption. Since Ethereum's gas fees are determined by the amount of computational effort required to execute a transaction, operations involving large, unbounded arrays can result in prohibitively high costs for users. Additionally, if a function iterates over an unbounded array, it may exceed the gas limit set by the network, causing the transaction to fail. To avoid these issues, developers should use bounded arrays or alternative data structures like mappings, ensuring efficient resource management and a better user experience. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L90-L90
```javascript
65:   function createPair(
66:     ILiquidationSource _source,
67:     address _tokenIn,
68:     address _tokenOut,
69:     uint32 _periodLength,
70:     uint32 _periodOffset,
71:     uint32 _targetFirstSaleTime,
72:     SD59x18 _decayConstant,
73:     uint112 _initialAmountIn,
74:     uint112 _initialAmountOut,
75:     uint256 _minimumAuctionAmount
76:   ) external returns (LiquidationPair) {
77:     LiquidationPair _liquidationPair = new LiquidationPair(
78:       _source,
79:       _tokenIn,
80:       _tokenOut,
81:       _periodLength,
82:       _periodOffset,
83:       _targetFirstSaleTime,
84:       _decayConstant,
85:       _initialAmountIn,
86:       _initialAmountOut,
87:       _minimumAuctionAmount
88:     );
89: 
90:     allPairs.push(_liquidationPair); // <= FOUND
91:     deployedPairs[_liquidationPair] = true;
92: 
93:     emit PairCreated(
94:       _liquidationPair,
95:       _source,
96:       _tokenIn,
97:       _tokenOut,
98:       _periodLength,
99:       _periodOffset,
100:       _targetFirstSaleTime,
101:       _decayConstant,
102:       _initialAmountIn,
103:       _initialAmountOut,
104:       _minimumAuctionAmount
105:     );
106: 
107:     return _liquidationPair;
108:   }

```


</details>


# [LOW-12] Contracts do not use their OZ upgradable counterparts
## Number of instances found
 1 

## Resolution
 Using the upgradeable counterpart of the OpenZeppelin (OZ) library in Solidity is beneficial for creating contracts that can be updated in the future. OpenZeppelin's upgradeable contracts library is designed with proxy patterns in mind, which allow the logic of contracts to be upgraded while preserving the contract's state and address. This can be crucial for long-lived contracts where future requirements or improvements may not be fully known at the time of deployment. The upgradeable OZ contracts also include protection against a class of vulnerabilities related to initialization of storage variables in upgradeable contracts. Hence, it's a good idea to use them when developing contracts that may need to be upgraded in the future, as they provide a solid foundation for secure and upgradeable smart contracts. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L40-L40
```javascript
40: contract VaultBooster is Ownable, ILiquidationSource  // <= FOUND

```


</details>


# [LOW-13] Loss of precision
## Number of instances found
 2 

## Resolution
 Dividing by large numbers in Solidity can cause a loss of precision due to the language's inherent integer division behavior. Solidity does not support floating-point arithmetic, and as a result, division between integers yields an integer result, truncating any fractional part. When dividing by a large number, the resulting value may become significantly smaller, leading to a loss of precision, as the fractional part is discarded. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L382-L382
```javascript
377:   function _computePeriod() internal view returns (uint256) {
378:     uint256 _timestamp = block.timestamp;
379:     if (_timestamp < periodOffset) {
380:       return 0;
381:     }
382:     return (_timestamp - periodOffset) / periodLength; // <= FOUND
383:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L374-L374
```javascript
365:   function _openSequenceId() internal view returns (uint32) {
366:     
367: 
368: 
369: 
370:     uint64 currentTime = _currentTime();
371:     if (currentTime < sequenceOffset) {
372:       return 0;
373:     }
374:     return uint32((currentTime - sequenceOffset) / sequencePeriod); // <= FOUND
375:   }

```


</details>


# [LOW-14] Missing zero address check in constructor
## Number of instances found
 9 

## Resolution
 In Solidity, constructors often take address parameters to initialize important components of a contract, such as owner or linked contracts. However, without a check, there's a risk that an address parameter could be mistakenly set to the zero address (0x0). This could occur due to a mistake or oversight during contract deployment. A zero address in a crucial role can cause serious issues, as it cannot perform actions like a normal address, and any funds sent to it are irretrievable. Therefore, it's crucial to include a zero address check in constructors to prevent such potential problems. If a zero address is detected, the constructor should revert the transaction. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L95-L96
```javascript
93:   constructor(
94:     ILiquidationSource _source,
95:     address _tokenIn, // <= FOUND
96:     address _tokenOut, // <= FOUND
97:     uint32 _periodLength,
98:     uint32 _periodOffset,
99:     uint32 _targetFirstSaleTime,
100:     SD59x18 _decayConstant,
101:     uint112 _initialAmountIn,
102:     uint112 _initialAmountOut,
103:     uint256 _minimumAuctionAmount
104:   ) {
105:     source = _source;
106:     tokenIn = _tokenIn;
107:     tokenOut = _tokenOut;
108:     decayConstant = _decayConstant;
109:     periodLength = _periodLength;
110:     periodOffset = _periodOffset;
111:     targetFirstSaleTime = _targetFirstSaleTime;
112: 
113:     SD59x18 period59 = convert(int256(uint256(_periodLength)));
114:     if (_decayConstant.mul(period59).unwrap() > uEXP_MAX_INPUT) {
115:       revert DecayConstantTooLarge(wrap(uEXP_MAX_INPUT).div(period59), _decayConstant);
116:     }
117: 
118:     if (targetFirstSaleTime >= periodLength) {
119:       revert TargetFirstSaleTimeLtPeriodLength(targetFirstSaleTime, periodLength);
120:     }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L142-L142
```javascript
140:   constructor(
141:     RNGInterface rng_,
142:     address owner_, // <= FOUND
143:     uint64 sequencePeriod_,
144:     uint64 sequenceOffset_,
145:     uint64 auctionDurationSeconds_,
146:     uint64 auctionTargetTime_
147:   ) Ownable(owner_) {
148:     if (sequencePeriod_ == 0) revert SequencePeriodZero();
149:     if (auctionTargetTime_ > auctionDurationSeconds_) revert AuctionTargetTimeExceedsDuration(uint64(auctionTargetTime_), uint64(auctionDurationSeconds_));
150:     sequencePeriod = sequencePeriod_;
151:     sequenceOffset = sequenceOffset_;
152:     auctionDuration = auctionDurationSeconds_;
153:     auctionTargetTime = auctionTargetTime_;
154:     _auctionTargetTimeFraction = intoUD2x18(convert(uint(auctionTargetTime_)).div(convert(uint(auctionDurationSeconds_))));
155:     _setNextRngService(rng_);
156:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L119-L123
```javascript
118:   constructor(
119:     PrizePool _prizePool, // <= FOUND
120:     address _vault, // <= FOUND
121:     address _owner // <= FOUND
122:   ) Ownable(_owner) {
123:     prizePool = _prizePool; // <= FOUND
124:     twabController = prizePool.twabController();
125:     vault = _vault;
126:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L53-L54
```javascript
51:   constructor(
52:     uint256 originChainId_,
53:     address executor_, // <= FOUND
54:     address __originChainOwner // <= FOUND
55:   ) ExecutorAware(executor_) {
56:     if (originChainId_ == 0) revert OriginChainIdZero();
57:     _originChainId = originChainId_;
58:     _setOriginChainOwner(__originChainOwner);
59:   }

```


</details>


# [LOW-15] Use of onlyOwner functions can be lost
## Number of instances found
 2 

## Resolution
 In Solidity, renouncing ownership of a contract essentially transfers ownership to the zero address. This is an irreversible operation and has considerable security implications. If the renounceOwnership function is used, the contract will lose the ability to perform any operations that are limited to the owner. This can be problematic if there are any bugs, flaws, or unexpected events that require owner intervention to resolve. Therefore, in some instances, it is better to disable or omit the renounceOwnership function, and instead implement a secure transferOwnership function. This way, if necessary, ownership can be transferred to a new, trusted party without losing the potential for administrative intervention. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L72-L72
```javascript
72: contract RngAuction is IAuction, Ownable  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L40-L40
```javascript
40: contract VaultBooster is Ownable, ILiquidationSource  // <= FOUND

```


</details>


# [LOW-16] Using zero as a parameter
## Number of instances found
 1 

## Resolution
 Taking 0 as a valid argument in Solidity without checks can lead to severe security issues. A historical example is the infamous 0x0 address bug where numerous tokens were lost. This happens because '0' can be interpreted as an uninitialized address, leading to transfers to the '0x0' address, effectively burning tokens. Moreover, 0 as a denominator in division operations would cause a runtime exception. It's also often indicative of a logical error in the caller's code. It's important to always validate input and handle edge cases like 0 appropriately. Use `require()` statements to enforce conditions and provide clear error messages to facilitate debugging and safer code. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L65-L65
```javascript
57:     function relay(
58:         IRngAuctionRelayListener _remoteRngAuctionRelayListener,
59:         address rewardRecipient
60:     ) external returns (bytes32) {
61:         bytes memory listenerCalldata = encodeCalldata(rewardRecipient);
62:         bytes32 messageId = messageDispatcher.dispatchMessage(
63:             toChainId,
64:             address(account),
65:             RemoteOwnerCallEncoder.encodeCalldata(address(_remoteRngAuctionRelayListener), 0, listenerCalldata) // <= FOUND
66:         );
67:         emit RelayedToDispatcher(rewardRecipient, messageId);
68:         return messageId;
69:     }

```


</details>


# [LOW-17] Solidity version 0.8.20 won't work on all chains due to PUSH0
## Number of instances found
 13 

## Resolution
 Solidity version 0.8.20 uses the new Shanghai EVM which introduces the PUSH0 opcode, this may not be implemented on all chains and L2 thus reducing the portability and compatability of the code. Consider using a earlier solidity version. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L2-L2
```javascript
2: pragma solidity ^0.8.19; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L2-L2
```javascript
2: pragma solidity ^0.8.0; // <= FOUND

```


</details>


# [LOW-18] Arrays can grow in size without a way to shrink them
## Number of instances found
 1 

## Resolution
 It's a good practice to maintain control over the size of array state variables in Solidity, especially if they are dynamically updated. If a contract includes a mechanism to push items into an array, it should ideally also provide a mechanism to remove items. This is because Solidity arrays don't automatically shrink when items are deleted - their length needs to be manually adjusted.

Ignoring this can lead to bloated and inefficient contracts. For instance, iterating over a large array can cause your contract to hit the block gas limit. Additionally, if entries are only marked for deletion but never actually removed, you may end up dealing with stale or irrelevant data, which can cause logical errors.

Therefore, implementing a method to 'pop' items from arrays helps manage contract's state, improve efficiency and prevent potential issues related to gas limits or stale data. Always ensure to handle potential underflow conditions when popping elements from the array. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L43-L43
```javascript
43: LiquidationPair[] public allPairs; // <= FOUND

```


</details>


# [LOW-19] Functions calling contracts/addresses with transfer hooks are missing reentrancy guards
## Number of instances found
 2 

## Resolution
 While adherence to the check-effects-interaction pattern is commendable, the absence of a reentrancy guard in functions, especially where transfer hooks might be present, can expose the protocol users to risks of read-only reentrancies. Such reentrancy vulnerabilities can be exploited to execute malicious actions even without altering the contract state. Without a reentrancy guard, the only potential mitigation would be to blocklist the entire protocol - an extreme and disruptive measure. Therefore, incorporating a reentrancy guard into these functions is vital to bolster security, as it helps protect against both traditional reentrancy attacks and read-only reentrancies, ensuring robust and safe protocol operations. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L193-L193
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner {
189:     uint256 availableBoost = _accrue(_token);
190:     uint256 availableBalance = _token.balanceOf(address(this));
191:     uint256 remainingBalance = availableBalance - _amount;
192:     _boosts[IERC20(_token)].available = (availableBoost > remainingBalance ? remainingBalance : availableBoost).toUint144();
193:     _token.transfer(msg.sender, _amount); // <= FOUND
194: 
195:     emit Withdrawn(_token, msg.sender, _amount);
196:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L226-L226
```javascript
211:   function liquidate(
212:     address _account,
213:     address _tokenIn,
214:     uint256 _amountIn,
215:     address _tokenOut,
216:     uint256 _amountOut
217:   ) external override onlyPrizeToken(_tokenIn) onlyLiquidationPair(_tokenOut) returns (bool) {
218:     uint256 amountAvailable = _computeAvailable(IERC20(_tokenOut));
219:     if (_amountOut > amountAvailable) {
220:       revert InsufficientAvailableBalance(_amountOut, amountAvailable);
221:     }
222:     amountAvailable = (amountAvailable - _amountOut);
223:     _boosts[IERC20(_tokenOut)].available = amountAvailable.toUint144();
224:     _boosts[IERC20(_tokenOut)].lastAccruedAt = uint48(block.timestamp);
225:     prizePool.contributePrizeTokens(vault, _amountIn);
226:     IERC20(_tokenOut).safeTransfer(_account, _amountOut); // <= FOUND
227: 
228:     emit Liquidated(
229:       IERC20(_tokenOut),
230:       _account,
231:       _amountIn,
232:       _amountOut,
233:       amountAvailable
234:     );
235: 
236:     return true;
237:   }

```


</details>


# [LOW-20] Revert on Transfer to the Zero Address
## Number of instances found
 1 

## Resolution
 Many ERC-20 and ERC-721 token contracts implement a safeguard that reverts transactions which attempt to transfer tokens to the zero address. This is because such transfers are often the result of programming errors. The OpenZeppelin library, a popular choice for implementing these standards, includes this safeguard. For token contract developers who want to avoid unintentional transfers to the zero address, it's good practice to include a condition that reverts the transaction if the recipient's address is the zero address.  

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L63-L69
```javascript
63:   function swapExactAmountOut(
64:     LiquidationPair _liquidationPair,
65:     address _receiver,
66:     uint256 _amountOut,
67:     uint256 _amountInMax
68:   ) external onlyTrustedLiquidationPair(_liquidationPair) returns (uint256) {
69:     IERC20(_liquidationPair.tokenIn()).safeTransferFrom( // <= FOUND
70:       msg.sender,
71:       _liquidationPair.target(),
72:       _liquidationPair.computeExactAmountIn(_amountOut)
73:     );
74: 
75:     uint256 amountIn = _liquidationPair.swapExactAmountOut(_receiver, _amountOut, _amountInMax);
76: 
77:     emit SwappedExactAmountOut(_liquidationPair, _receiver, _amountOut, _amountInMax, amountIn);
78: 
79:     return amountIn;
80:   }

```


</details>


# [LOW-21] Constructors contains no validation
## Number of instances found
 4 

## Resolution
 In Solidity, when values are being assigned in constructors to unsigned or integer variables, it's crucial to ensure the provided values adhere to the protocol's specific operational boundaries as laid out in the project specifications and documentation. If the constructors lack appropriate validation checks, there's a risk of setting state variables with values that could cause unexpected and potentially detrimental behavior within the contract's operations, violating the intended logic of the protocol. This can compromise the contract's security and impact the maintainability and reliability of the system. In order to avoid such issues, it is recommended to incorporate rigorous validation checks in constructors. These checks should align with the project's defined rules and constraints, making use of Solidity's built-in require function to enforce these conditions. If the validation checks fail, the require function will cause the transaction to revert, ensuring the integrity and adherence to the protocol's expected behavior. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L40-L48
```javascript
40:     constructor(
41:         RngAuction _rngAuction,
42:         ISingleMessageDispatcher _messageDispatcher,
43:         RemoteOwner _remoteOwner,
44:         uint256 _toChainId // <= FOUND
45:     ) RngAuctionRelayer(_rngAuction) {
46:         messageDispatcher = _messageDispatcher; // <= FOUND
47:         account = _remoteOwner; // <= FOUND
48:         toChainId = _toChainId; // <= FOUND
49:     }

```


</details>




# [NC-1] Floating pragma should be avoided
## Number of instances found
 13 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L2-L2
```javascript
2: pragma solidity ^0.8.19; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L2-L2
```javascript
2: pragma solidity ^0.8.0; // <= FOUND

```


</details>


# [NC-2] Empty function blocks
## Number of instances found
 1 

## Resolution
 Empty code blocks (i.e., {}) in a Solidity contract can be harmful as they can lead to ambiguity, misinterpretation, and unintended behavior. When developers encounter empty code blocks, it may be unclear whether the absence of code is intentional or the result of an oversight. This uncertainty can cause confusion during development, testing, and debugging, increasing the likelihood of introducing errors or vulnerabilities. Moreover, empty code blocks may give a false impression of implemented functionality or security measures, creating a misleading sense of assurance. To ensure clarity and maintainability, it is essential to avoid empty code blocks and explicitly document the intended behavior or any intentional omissions. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L26-L26
```javascript
26:     constructor(RngAuction _rngAuction) RngAuctionRelayer(_rngAuction) {
27:     }

```


</details>


# [NC-3] Events regarding state variable changes should emit the previous state variable value
## Number of instances found
 2 

## Resolution
 Modify such events to contain the previous value of the state variable as demonstrated in the example below 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L111-L111
```javascript
111: event SetNextRngService(RNGInterface indexed rngService);

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L36-L36
```javascript
36: event OriginChainOwnerSet(address owner);

```


</details>


# [NC-4] In functions which accept an address as a parameter, there should be a zero address check to prevent bugs
## Number of instances found
 19 

## Resolution
 Implement a zero address check to ensure input isn't the zero address 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L211-L211
```javascript
211:   function swapExactAmountOut(
212:     address _account,
213:     uint256 _amountOut,
214:     uint256 _amountInMax
215:   ) external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L65-L65
```javascript
65:   function createPair(
66:     ILiquidationSource _source,
67:     address _tokenIn,
68:     address _tokenOut,
69:     uint32 _periodLength,
70:     uint32 _periodOffset,
71:     uint32 _targetFirstSaleTime,
72:     SD59x18 _decayConstant,
73:     uint112 _initialAmountIn,
74:     uint112 _initialAmountOut,
75:     uint256 _minimumAuctionAmount
76:   ) external returns (LiquidationPair) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L63-L63
```javascript
63:   function swapExactAmountOut(
64:     LiquidationPair _liquidationPair,
65:     address _receiver,
66:     uint256 _amountOut,
67:     uint256 _amountInMax
68:   ) external onlyTrustedLiquidationPair(_liquidationPair) returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L34-L34
```javascript
34:     function relay(
35:         IRngAuctionRelayListener _rngAuctionRelayListener,
36:         address _relayRewardRecipient
37:     ) external returns (bytes memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L57-L57
```javascript
57:     function relay(
58:         IRngAuctionRelayListener _remoteRngAuctionRelayListener,
59:         address rewardRecipient
60:     ) external returns (bytes32) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L131-L131
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L31-L31
```javascript
31:     function encodeCalldata(address rewardRecipient) internal returns (bytes memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L32-L32
```javascript
32:   function remappingOf(address _addr) public view returns (address) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L47-L47
```javascript
47:   function remapTo(address _destination) external 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L58-L58
```javascript
58:   function _remap(address _caller, address _destination) internal 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L201-L201
```javascript
201:   function liquidatableBalanceOf(address _tokenOut) external override returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L211-L211
```javascript
211:   function liquidate(
212:     address _account,
213:     address _tokenIn,
214:     uint256 _amountIn,
215:     address _tokenOut,
216:     uint256 _amountOut
217:   ) external override onlyPrizeToken(_tokenIn) onlyLiquidationPair(_tokenOut) returns (bool) 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L242-L242
```javascript
242:   function targetOf(address _tokenIn) external view override onlyPrizeToken(_tokenIn) returns (address) 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L28-L28
```javascript
28:     function createVaultBooster(PrizePool _prizePool, address _vault, address _owner) external returns (VaultBooster) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L63-L63
```javascript
63:   function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L96-L96
```javascript
96:   function setOriginChainOwner(address _newOriginChainOwner) external 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L103-L103
```javascript
103:   function _setOriginChainOwner(address _newOriginChainOwner) internal 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L7-L7
```javascript
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L170-L170
```javascript
170:   function startRngRequest(address _rewardRecipient) external 

```


</details>


# [NC-5] Enum values should be used in place of constant array indexes
## Number of instances found
 2 

## Resolution
 Create a commented enum value to use in place of constant array indexes, this makes the code far easier to understand 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L148-L149
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) {
138:     if (_sequenceHasCompleted(_sequenceId)) revert SequenceAlreadyCompleted();
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt);
140:     if (_auctionElapsedSeconds > (_auctionDurationSeconds-1)) revert AuctionExpired();
141:     
142:     UD2x18 rewardFraction = _fractionalReward(_auctionElapsedSeconds);
143:     _auctionResults.rewardFraction = rewardFraction;
144:     _auctionResults.recipient = _rewardRecipient;
145:     _lastSequenceId = _sequenceId;
146: 
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2);
148:     auctionResults[0] = _rngAuctionResult; // <= FOUND
149:     auctionResults[1] = AuctionResult({ // <= FOUND
150:       rewardFraction: rewardFraction,
151:       recipient: _rewardRecipient
152:     });
153: 
154:     uint32 drawId = prizePool.closeDraw(_randomNumber);
155: 
156:     uint256 futureReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
157:     uint256[] memory _rewards = RewardLib.rewards(auctionResults, futureReserve);
158: 
159:     emit RngSequenceCompleted(
160:       _sequenceId,
161:       drawId,
162:       _rewardRecipient,
163:       _auctionElapsedSeconds,
164:       rewardFraction
165:     );
166: 
167:     for (uint8 i = 0; i < _rewards.length; i++) {
168:       uint104 _reward = uint104(_rewards[i]);
169:       if (_reward > 0) {
170:         prizePool.withdrawReserve(auctionResults[i].recipient, _reward);
171:         emit AuctionRewardDistributed(_sequenceId, auctionResults[i].recipient, i, _reward);
172:       }
173:     }

```


</details>


# [NC-6] Zero address checks should be present in constructors which take address(es) as parameters
## Number of instances found
 5 

## Resolution
 Implement a zero address check to prevent wrong address assignation during deployment 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L93-L93
```javascript
93:   constructor(
94:     ILiquidationSource _source,
95:     address _tokenIn,
96:     address _tokenOut,
97:     uint32 _periodLength,
98:     uint32 _periodOffset,
99:     uint32 _targetFirstSaleTime,
100:     SD59x18 _decayConstant,
101:     uint112 _initialAmountIn,
102:     uint112 _initialAmountOut,
103:     uint256 _minimumAuctionAmount
104:   ) {
105:     source = _source;
106:     tokenIn = _tokenIn;
107:     tokenOut = _tokenOut;
108:     decayConstant = _decayConstant;
109:     periodLength = _periodLength;
110:     periodOffset = _periodOffset;
111:     targetFirstSaleTime = _targetFirstSaleTime;
112: 
113:     SD59x18 period59 = convert(int256(uint256(_periodLength)));
114:     if (_decayConstant.mul(period59).unwrap() > uEXP_MAX_INPUT) {
115:       revert DecayConstantTooLarge(wrap(uEXP_MAX_INPUT).div(period59), _decayConstant);
116:     }
117: 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L140-L140
```javascript
140:   constructor(
141:     RNGInterface rng_,
142:     address owner_,
143:     uint64 sequencePeriod_,
144:     uint64 sequenceOffset_,
145:     uint64 auctionDurationSeconds_,
146:     uint64 auctionTargetTime_
147:   ) Ownable(owner_) {
148:     if (sequencePeriod_ == 0) revert SequencePeriodZero();
149:     if (auctionTargetTime_ > auctionDurationSeconds_) revert AuctionTargetTimeExceedsDuration(uint64(auctionTargetTime_), uint64(auctionDurationSeconds_));
150:     sequencePeriod = sequencePeriod_;
151:     sequenceOffset = sequenceOffset_;
152:     auctionDuration = auctionDurationSeconds_;
153:     auctionTargetTime = auctionTargetTime_;
154:     _auctionTargetTimeFraction = intoUD2x18(convert(uint(auctionTargetTime_)).div(convert(uint(auctionDurationSeconds_))));
155:     _setNextRngService(rng_);
156:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L102-L102
```javascript
102:   constructor(
103:     PrizePool prizePool_,
104:     address _rngAuctionRelayer,
105:     uint64 auctionDurationSeconds_,
106:     uint64 auctionTargetTime_
107:   ) {
108:     if (address(prizePool_) == address(0)) revert PrizePoolZeroAddress();
109:     prizePool = prizePool_;
110:     if (address(_rngAuctionRelayer) == address(0)) revert RngRelayerZeroAddress();
111:     if (auctionDurationSeconds_ == 0) revert AuctionDurationZero();
112:     if (auctionTargetTime_ == 0) revert AuctionTargetTimeZero();
113:     if (auctionTargetTime_ > auctionDurationSeconds_) {
114:       revert AuctionTargetTimeExceedsDuration(auctionDurationSeconds_, auctionTargetTime_);
115:     }
116:     rngAuctionRelayer = _rngAuctionRelayer;
117:     _auctionDurationSeconds = auctionDurationSeconds_;
118:     _auctionTargetTimeFraction = UD2x18.wrap(
119:       uint64(convert(auctionTargetTime_).div(convert(_auctionDurationSeconds)).unwrap())
120:     );
121:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L118-L118
```javascript
118:   constructor(
119:     PrizePool _prizePool,
120:     address _vault,
121:     address _owner
122:   ) Ownable(_owner) {
123:     prizePool = _prizePool;
124:     twabController = prizePool.twabController();
125:     vault = _vault;
126:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L51-L51
```javascript
51:   constructor(
52:     uint256 originChainId_,
53:     address executor_,
54:     address __originChainOwner
55:   ) ExecutorAware(executor_) {
56:     if (originChainId_ == 0) revert OriginChainIdZero();
57:     _originChainId = originChainId_;
58:     _setOriginChainOwner(__originChainOwner);
59:   }

```


</details>


# [NC-7] Ownable2Step should be used in place of Ownable
## Number of instances found
 2 

## Resolution
 Ownable2Step further prevents risks posed by centralised privileges as there is a smaller likelihood of the owner being wrongfully changed 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L72-L72
```javascript
72: contract RngAuction is IAuction, Ownable  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L40-L40
```javascript
40: contract VaultBooster is Ownable, ILiquidationSource  // <= FOUND

```


</details>


# [NC-8] Functions which are either private or internal should have a preceding _ in their name
## Number of instances found
 8 

## Resolution
 Add a preceding underscore to the function name, take care to refactor where there functions are called 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L23-L23
```javascript
23:   function purchasePrice(
24:     SD59x18 _amount,
25:     SD59x18 _emissionRate,
26:     SD59x18 _k,
27:     SD59x18 _decayConstant,
28:     SD59x18 _timeSinceLastAuctionStart
29:   ) internal pure returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L54-L54
```javascript
54:   function purchaseAmount(
55:     SD59x18 _price,
56:     SD59x18 _emissionRate,
57:     SD59x18 _k,
58:     SD59x18 _decayConstant,
59:     SD59x18 _timeSinceLastAuctionStart
60:   ) internal pure returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L77-L77
```javascript
77:   function computeK(
78:     SD59x18 _emissionRate,
79:     SD59x18 _decayConstant,
80:     SD59x18 _targetFirstSaleTime,
81:     SD59x18 _purchaseAmount,
82:     SD59x18 _price
83:   ) internal pure returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L25-L25
```javascript
25:   function fractionalReward(
26:     uint64 _elapsedTime,
27:     uint64 _auctionDuration,
28:     UD2x18 _targetTimeFraction,
29:     UD2x18 _targetRewardFraction
30:   ) internal pure returns (UD2x18) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L58-L58
```javascript
58:   function rewards(
59:     AuctionResult[] memory _auctionResults,
60:     uint256 _reserve
61:   ) internal pure returns (uint256[] memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L79-L79
```javascript
79:   function reward(
80:     AuctionResult memory _auctionResult,
81:     uint256 _reserve
82:   ) internal pure returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L31-L31
```javascript
31:     function encodeCalldata(address rewardRecipient) internal returns (bytes memory) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L7-L7
```javascript
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) 

```


</details>


# [NC-9] Public state variables shouldn't have a preceding _ in their name
## Number of instances found
 6 

## Resolution
 Remove the _ from the state variable name, ensure you also refactor where these state variables are internally called 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L57-L57
```javascript
57: uint112 _lastNonZeroAmountIn; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L60-L60
```javascript
60: uint112 _lastNonZeroAmountOut; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L63-L63
```javascript
63: uint96 _amountInForPeriod; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L66-L66
```javascript
66: uint96 _amountOutForPeriod; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L69-L69
```javascript
69: uint16 _period; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L72-L72
```javascript
72: uint48 _lastAuctionTime; // <= FOUND

```


</details>


# [NC-10] Contract lines should not be longer than 110 characters for readability
## Number of instances found
 14 

## Resolution
 Consider spreading these lines over multiple lines to aid in readability and the support of VIM users everywhere. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L347-L347
```javascript
347:       SD59x18 exchangeRateAmountInToAmountOut = convert(int(uint(_lastNonZeroAmountIn))).div(convert(int(uint(_lastNonZeroAmountOut)))); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L149-L149
```javascript
149:     if (auctionTargetTime_ > auctionDurationSeconds_) revert AuctionTargetTimeExceedsDuration(uint64(auctionTargetTime_), uint64(auctionDurationSeconds_)); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L154-L154
```javascript
154:     _auctionTargetTimeFraction = intoUD2x18(convert(uint(auctionTargetTime_)).div(convert(uint(auctionDurationSeconds_)))); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L65-L65
```javascript
65:             RemoteOwnerCallEncoder.encodeCalldata(address(_remoteRngAuctionRelayListener), 0, listenerCalldata) // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L139-L139
```javascript
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L190-L190
```javascript
190:   function computeRewardsWithTotal(AuctionResult[] calldata __auctionResults, uint256 _totalReserve) external returns (uint256[] memory) { // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L234-L234
```javascript
234:   function _computeRewards(AuctionResult[] calldata __auctionResults, uint256 _totalReserve) internal returns (uint256[] memory) { // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L37-L37
```javascript
37:         return abi.encodeWithSelector(IRngAuctionRelayListener.rngComplete.selector, randomNumber, rngCompletedAt, rewardRecipient, sequenceId, results); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner { // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L192-L192
```javascript
192:     _boosts[IERC20(_token)].available = (availableBoost > remainingBalance ? remainingBalance : availableBoost).toUint144(); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L273-L273
```javascript
273:       uint256 totalSupply = twabController.getTotalSupplyTwabBetween(address(vault), uint32(boost.lastAccruedAt), uint32(block.timestamp)); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L274-L274
```javascript
274:       deltaAmount += convert(boost.multiplierOfTotalSupplyPerSecond.intoUD60x18().mul(convert(deltaTime)).mul(convert(totalSupply))); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L28-L28
```javascript
28:     function createVaultBooster(PrizePool _prizePool, address _vault, address _owner) external returns (VaultBooster) { // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L7-L7
```javascript
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) { // <= FOUND

```


</details>


# [NC-11] Specific imports should be used where possible so only used code is imported
## Number of instances found
 3 

## Resolution
 In many cases only some functionality is used from an import. In such cases it makes more sense to use {} to specify what to import and thus save gas whilst improving readability 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L5-L5
```javascript
5: import "LiquidationPair.sol";

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L4-L4
```javascript
4: import "openzeppelin/token/ERC20/IERC20.sol";

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L4-L4
```javascript
4: import "forge-std/console2.sol";

```


</details>


# [NC-12] Use newer solidity versions
## Number of instances found
 4 

## Resolution
 Newer solidity versions have new functionality and are generally more gas efficient too (0.8.19) as such it makes sense to use them provided it is safe to do so 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L2-L2
```javascript
2: pragma solidity ^0.8.0; // <= FOUND

```


</details>


# [NC-13] Not all event definitions are utilizing indexed variables.
## Number of instances found
 9 

## Resolution
 Try to index as much as three variables in event declarations as this is more gas efficient when done on value type variables (uint, address etc) however not for bytes and string variables  

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L26-L26
```javascript
26: event PairCreated( // <= FOUND
27:     LiquidationPair indexed pair,
28:     ILiquidationSource source,
29:     address tokenIn,
30:     address tokenOut,
31:     uint32 periodLength,
32:     uint32 periodOffset,
33:     uint32 targetFirstSaleTime,
34:     SD59x18 decayConstant,
35:     uint112 initialAmountIn,
36:     uint112 initialAmountOut,
37:     uint256 minimumAuctionAmount
38:   );

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L30-L30
```javascript
30: event SwappedExactAmountOut( // <= FOUND
31:     LiquidationPair indexed liquidationPair,
32:     address indexed receiver,
33:     uint256 amountOut,
34:     uint256 amountInMax,
35:     uint256 amountIn
36:   );

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L53-L53
```javascript
53: event AuctionRewardDistributed( // <= FOUND
54:     uint32 indexed sequenceId,
55:     address indexed recipient,
56:     uint32 index,
57:     uint256 reward
58:   );

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L51-L51
```javascript
51: event SetBoost( // <= FOUND
52:     IERC20 indexed token,
53:     address liquidationPair,
54:     UD2x18 multiplierOfTotalSupplyPerSecond,
55:     uint96 tokensPerSecond,
56:     uint144 initialAvailable,
57:     uint48 lastAccruedAt
58:   );

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L64-L64
```javascript
64: event Deposited( // <= FOUND
65:     IERC20 indexed token,
66:     address indexed from,
67:     uint256 amount
68:   );

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L74-L74
```javascript
74: event Withdrawn( // <= FOUND
75:     IERC20 indexed token,
76:     address indexed from,
77:     uint256 amount
78:   );

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L86-L86
```javascript
86: event Liquidated( // <= FOUND
87:     IERC20 indexed token,
88:     address indexed from,
89:     uint256 amountIn,
90:     uint256 amountOut,
91:     uint256 availableBoostBalance
92:   );

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L97-L97
```javascript
97: event BoostAccrued( // <= FOUND
98:     IERC20 indexed token,
99:     uint256 availableBoostBalance
100:   );

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L36-L36
```javascript
36: event OriginChainOwnerSet(address owner); // <= FOUND

```


</details>


# [NC-14] Explicitly define visibility of state variables to prevent misconceptions on what can access the variable
## Number of instances found
 6 

## Resolution
 Such state variables should be marked as private as this is the default visibility 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L57-L57
```javascript
57: uint112 _lastNonZeroAmountIn;

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L60-L60
```javascript
60: uint112 _lastNonZeroAmountOut;

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L63-L63
```javascript
63: uint96 _amountInForPeriod;

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L66-L66
```javascript
66: uint96 _amountOutForPeriod;

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L69-L69
```javascript
69: uint16 _period;

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L72-L72
```javascript
72: uint48 _lastAuctionTime;

```


</details>


# [NC-15] Function names should differ to make the code more readable
## Number of instances found
 10 

## Resolution
 In Solidity, while function overriding allows for functions with the same name to coexist, it is advisable to avoid this practice to enhance code readability and maintainability. Having multiple functions with the same name, even with different parameters or in inherited contracts, can cause confusion and increase the likelihood of errors during development, testing, and debugging. Using distinct and descriptive function names not only clarifies the purpose and behavior of each function, but also helps prevent unintended function calls or incorrect overriding. By adopting a clear and consistent naming convention, developers can create more comprehensible and maintainable smart contracts. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L211-L211
```javascript
211:   function swapExactAmountOut( // <= FOUND
212:     address _account,
213:     uint256 _amountOut,
214:     uint256 _amountInMax
215:   ) external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L63-L63
```javascript
63:   function swapExactAmountOut( // <= FOUND
64:     LiquidationPair _liquidationPair,
65:     address _receiver,
66:     uint256 _amountOut,
67:     uint256 _amountInMax
68:   ) external onlyTrustedLiquidationPair(_liquidationPair) returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L34-L34
```javascript
34:     function relay( // <= FOUND
35:         IRngAuctionRelayListener _rngAuctionRelayListener,
36:         address _relayRewardRecipient
37:     ) external returns (bytes memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L57-L57
```javascript
57:     function relay( // <= FOUND
58:         IRngAuctionRelayListener _remoteRngAuctionRelayListener,
59:         address rewardRecipient
60:     ) external returns (bytes32) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L300-L300
```javascript
300:   function computeRewardFraction(uint64 __auctionElapsedTime) external view returns (UD2x18)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L209-L209
```javascript
209:   function computeRewardFraction(uint64 _auctionElapsedTime) external view returns (UD2x18)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L214-L214
```javascript
214:   function lastSequenceId() external view returns (uint32)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L219-L219
```javascript
219:   function getLastAuctionResult() // <= FOUND
220:     external
221:     view
222:     returns (AuctionResult memory)
223:   

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L31-L31
```javascript
31:     function encodeCalldata(address rewardRecipient) internal returns (bytes memory)  // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L7-L7
```javascript
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory)  // <= FOUND

```


</details>


# [NC-16] It is standard for all external and public functions to be override from an interface
## Number of instances found
 57 

## Resolution
 This is to ensure the whole API is extracted in a interface 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L140-L140
```javascript
140:   function target() external returns (address) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L145-L145
```javascript
145:   function maxAmountOut() external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L152-L152
```javascript
152:   function maxAmountIn() external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L158-L158
```javascript
158:   function computeExactAmountIn(uint256 _amountOut) external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L164-L164
```javascript
164:   function estimateAmountOut(uint256 __amountIn) external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L177-L177
```javascript
177:   function amountInForPeriod() external returns (uint96) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L184-L184
```javascript
184:   function amountOutForPeriod() external returns (uint96) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L191-L191
```javascript
191:   function lastAuctionTime() external returns (uint48) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L198-L198
```javascript
198:   function emissionRate() external returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L205-L205
```javascript
205:   function initialPrice() external returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L211-L211
```javascript
211:   function swapExactAmountOut(
212:     address _account,
213:     uint256 _amountOut,
214:     uint256 _amountInMax
215:   ) external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L229-L229
```javascript
229:   function getElapsedTime() external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L236-L236
```javascript
236:   function getPeriodStart() external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L243-L243
```javascript
243:   function getPeriodEnd() external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L250-L250
```javascript
250:   function lastNonZeroAmountIn() external returns (uint112) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L257-L257
```javascript
257:   function lastNonZeroAmountOut() external returns (uint112) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L65-L65
```javascript
65:   function createPair(
66:     ILiquidationSource _source,
67:     address _tokenIn,
68:     address _tokenOut,
69:     uint32 _periodLength,
70:     uint32 _periodOffset,
71:     uint32 _targetFirstSaleTime,
72:     SD59x18 _decayConstant,
73:     uint112 _initialAmountIn,
74:     uint112 _initialAmountOut,
75:     uint256 _minimumAuctionAmount
76:   ) external returns (LiquidationPair) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L114-L114
```javascript
114:   function totalPairs() external view returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L63-L63
```javascript
63:   function swapExactAmountOut(
64:     LiquidationPair _liquidationPair,
65:     address _receiver,
66:     uint256 _amountOut,
67:     uint256 _amountInMax
68:   ) external onlyTrustedLiquidationPair(_liquidationPair) returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L170-L170
```javascript
170:   function startRngRequest(address _rewardRecipient) external 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L215-L215
```javascript
215:   function canStartNextSequence() external view returns (bool) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L223-L223
```javascript
223:   function isAuctionOpen() external view returns (bool) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L229-L229
```javascript
229:   function auctionElapsedTime() external view returns (uint64) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L234-L234
```javascript
234:   function currentFractionalReward() external view returns (UD2x18) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L239-L239
```javascript
239:   function getLastAuction() external view returns (RngAuctionResult memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L219-L219
```javascript
219:   function getLastAuctionResult()
220:     external
221:     view
222:     returns (AuctionResult memory)
223:   

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L261-L261
```javascript
261:   function openSequenceId() external view returns (uint32) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L214-L214
```javascript
214:   function lastSequenceId() external view returns (uint32) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L277-L277
```javascript
277:   function isRngComplete() external view returns (bool) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L288-L288
```javascript
288:   function getRngResults()
289:     external
290:     returns (
291:       uint256 randomNumber, uint64 rngCompletedAt
292:     )
293:   

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L300-L300
```javascript
300:   function computeRewardFraction(uint64 __auctionElapsedTime) external view returns (UD2x18) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L310-L310
```javascript
310:   function getLastRngService() external view returns (RNGInterface) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L318-L318
```javascript
318:   function getNextRngService() external view returns (RNGInterface) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L326-L326
```javascript
326:   function getSequenceOffset() external view returns (uint64) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L334-L334
```javascript
334:   function getSequencePeriod() external view returns (uint64) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L347-L347
```javascript
347:   function setNextRngService(RNGInterface _rngService) external onlyOwner 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L34-L34
```javascript
34:     function relay(
35:         IRngAuctionRelayListener _rngAuctionRelayListener,
36:         address _relayRewardRecipient
37:     ) external returns (bytes memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L57-L57
```javascript
57:     function relay(
58:         IRngAuctionRelayListener _remoteRngAuctionRelayListener,
59:         address rewardRecipient
60:     ) external returns (bytes32) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L131-L131
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L181-L181
```javascript
181:   function computeRewards(AuctionResult[] calldata __auctionResults) external returns (uint256[] memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L190-L190
```javascript
190:   function computeRewardsWithTotal(AuctionResult[] calldata __auctionResults, uint256 _totalReserve) external returns (uint256[] memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L197-L197
```javascript
197:   function isSequenceCompleted(uint32 _sequenceId) external view returns (bool) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L202-L202
```javascript
202:   function auctionDuration() external view returns (uint64) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L209-L209
```javascript
209:   function computeRewardFraction(uint64 _auctionElapsedTime) external view returns (UD2x18) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L47-L47
```javascript
47:   function remapTo(address _destination) external 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L131-L131
```javascript
131:   function getBoost(IERC20 _token) external returns (Boost memory) 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L171-L171
```javascript
171:   function deposit(IERC20 _token, uint256 _amount) external 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L181-L181
```javascript
181:   function accrue(IERC20 _token) external returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L188-L188
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L28-L28
```javascript
28:     function createVaultBooster(PrizePool _prizePool, address _vault, address _owner) external returns (VaultBooster) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L63-L63
```javascript
63:   function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L81-L81
```javascript
81:   function originChainId() external view returns (uint256) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L85-L85
```javascript
85:   function originChainOwner() external view returns (address) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L96-L96
```javascript
96:   function setOriginChainOwner(address _newOriginChainOwner) external 

```


</details>


# [NC-17] uint variables should have the bit size defined explicitly
## Number of instances found
 4 

## Resolution
 Instead of using uint to declare uint258, explicitly define uint258 to ensure there is no confusion 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L69-L69
```javascript
63:   function swapExactAmountOut(
64:     address _account,
65:     uint256 _amountOut,
66:     uint256 _amountInMax
67:   ) external returns (uint256) {
68:     _checkUpdateAuction();
69:     uint swapAmountIn = _computeExactAmountIn(_amountOut); // <= FOUND
70:     if (swapAmountIn > _amountInMax) {
71:       revert SwapExceedsMax(_amountInMax, swapAmountIn);
72:     }
73:     _amountInForPeriod += uint96(swapAmountIn);
74:     _amountOutForPeriod += uint96(_amountOut);
75:     _lastAuctionTime += uint48(uint256(convert(convert(int256(_amountOut)).div(_emissionRate))));
76:     source.liquidate(_account, tokenIn, swapAmountIn, tokenOut, _amountOut);
77:     return swapAmountIn;
78:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L267-L268
```javascript
266:   function _maxAmountOut() internal returns (uint256) {
267:     uint emissions = uint(convert(_emissionRate.mul(_getElapsedTime()))); // <= FOUND
268:     uint liquidatable = source.liquidatableBalanceOf(tokenOut); // <= FOUND
269:     return emissions > liquidatable ? liquidatable : emissions;
270:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L306-L306
```javascript
297:   function _computeExactAmountIn(uint256 _amountOut) internal returns (uint256) {
298:     if (_amountOut == 0) {
299:       return 0;
300:     }
301:     uint256 maxOut = _maxAmountOut();
302:     if (_amountOut > maxOut) {
303:       revert SwapExceedsAvailable(_amountOut, maxOut);
304:     }
305:     SD59x18 elapsed = _getElapsedTime();
306:     uint purchasePrice = uint256(convert(ContinuousGDA.purchasePrice( // <= FOUND
307:         convert(int(_amountOut)),
308:         _emissionRate,
309:         _initialPrice,
310:         decayConstant,
311:         elapsed
312:       ).ceil()));
313: 
314:     if (purchasePrice == 0) {
315:       revert PurchasePriceIsZero(_amountOut);
316:     }
317: 
318:     return purchasePrice;
319:   }

```


</details>


# [NC-18] Functions within contracts are not ordered according to the solidity style guide
## Number of instances found
 1 

## Resolution
 The following order should be used within contracts

constructor

receive function (if exists)

fallback function (if exists)

external

public

internal

private

Rearrange the contract functions and contructors to fit this ordering 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L10-L10
```javascript
10: contract AddressRemapper  // <= FOUND

```


</details>


# [NC-19] Emits without msg.sender parameter
## Number of instances found
 4 

## Resolution
 If msg.sender play a part in the functionality of a function, any emits of this function should include msg.sender to ensure transparency with users 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L70-L77
```javascript
63:   function swapExactAmountOut(
64:     LiquidationPair _liquidationPair,
65:     address _receiver,
66:     uint256 _amountOut,
67:     uint256 _amountInMax
68:   ) external onlyTrustedLiquidationPair(_liquidationPair) returns (uint256) {
69:     IERC20(_liquidationPair.tokenIn()).safeTransferFrom(
70:       msg.sender, // <= FOUND
71:       _liquidationPair.target(),
72:       _liquidationPair.computeExactAmountIn(_amountOut)
73:     );
74: 
75:     uint256 amountIn = _liquidationPair.swapExactAmountOut(_receiver, _amountOut, _amountInMax);
76: 
77:     emit SwappedExactAmountOut(_liquidationPair, _receiver, _amountOut, _amountInMax, amountIn); // <= FOUND
78: 
79:     return amountIn;
80:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L182-L200
```javascript
170:   function startRngRequest(address _rewardRecipient) external {
171:     if (!_canStartNextSequence()) revert CannotStartNextSequence();
172: 
173:     RNGInterface rng = _nextRng;
174: 
175:     uint64 _auctionElapsedTimeSeconds = _auctionElapsedTime();
176:     if (_auctionElapsedTimeSeconds > auctionDuration) revert AuctionExpired();
177: 
178:     (address _feeToken, uint256 _requestFee) = rng.getRequestFee();
179:     if (_feeToken != address(0) && _requestFee > 0) {
180:       if (IERC20(_feeToken).balanceOf(address(this)) < _requestFee) {
181:         
182:         IERC20(_feeToken).transferFrom(msg.sender, address(this), _requestFee); // <= FOUND
183:       }
184:       
185:       IERC20(_feeToken).safeIncreaseAllowance(address(rng), _requestFee);
186:     }
187: 
188:     (uint32 rngRequestId,) = rng.requestRandomNumber();
189:     uint32 sequenceId = _openSequenceId();
190:     UD2x18 rewardFraction = _currentFractionalReward();
191: 
192:     _lastAuction = RngAuctionResult({
193:       recipient: _rewardRecipient,
194:       rewardFraction: rewardFraction,
195:       sequenceId: sequenceId,
196:       rng: rng,
197:       rngRequestId: rngRequestId
198:     });
199: 
200:     emit RngAuctionCompleted( // <= FOUND
201:       _rewardRecipient,
202:       sequenceId,
203:       rng,
204:       rngRequestId,
205:       _auctionElapsedTimeSeconds,
206:       rewardFraction
207:     );
208:   }

```


</details>


# [NC-20] Functions with array parameters should have length checks in place
## Number of instances found
 3 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L181-L181
```javascript
181:   function computeRewards(AuctionResult[] calldata __auctionResults) external returns (uint256[] memory) {
182:     uint256 totalReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
183:     return _computeRewards(__auctionResults, totalReserve);
184:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L190-L190
```javascript
190:   function computeRewardsWithTotal(AuctionResult[] calldata __auctionResults, uint256 _totalReserve) external returns (uint256[] memory) {
191:     return _computeRewards(__auctionResults, _totalReserve);
192:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L234-L234
```javascript
234:   function _computeRewards(AuctionResult[] calldata __auctionResults, uint256 _totalReserve) internal returns (uint256[] memory) {
235:     return RewardLib.rewards(__auctionResults, _totalReserve);
236:   }

```


</details>


# [NC-21] Interface imports should be declared first
## Number of instances found
 34 

## Resolution
 Amend the ordering of imports to import interfaces first followed by other imports 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L5-L12
```javascript
2: 
3: pragma solidity ^0.8.19;
4: 
5: import { UD2x18 } from "prb-math/UD2x18.sol"; // <= FOUND
6: import { convert } from "prb-math/UD60x18.sol"; // <= FOUND
7: import { PrizePool } from "pt-v5-prize-pool/PrizePool.sol"; // <= FOUND
8: 
9: import { RewardLib } from "libraries/RewardLib.sol"; // <= FOUND
10: import { IRngAuctionRelayListener } from "interfaces/IRngAuctionRelayListener.sol"; // <= FOUND
11: import { IAuction, AuctionResult } from "interfaces/IAuction.sol"; // <= FOUND
12: import { RngAuction } from "RngAuction.sol"; // <= FOUND
13: 
14: 
15: 
16: 
17: error AuctionDurationZero();
18: 
19: 
20: error AuctionTargetTimeZero();
21: 
22: 
23: 
24: 
25: 
26: 
27: error AuctionTargetTimeExceedsDuration(uint64 auctionDuration, uint64 auctionTargetTime);
28: 
29: 
30: error RngRelayerZeroAddress();
31: 
32: 
33: error SequenceAlreadyCompleted();
34: 
35: 
36: error AuctionExpired();

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L5-L8
```javascript
2: 
3: pragma solidity ^0.8.19;
4: 
5: import { UD2x18 } from "prb-math/UD2x18.sol"; // <= FOUND
6: import { UD60x18, convert } from "prb-math/UD60x18.sol"; // <= FOUND
7: 
8: import { AuctionResult } from ".interfaces/IAuction.sol"; // <= FOUND
9: 
10: 
11: 
12: 
13: 
14: library RewardLib {
15:   
16: 
17:   
18: 
19: 
20: 
21: 
22: 
23: 
24: 
25: 
26:   function fractionalReward(
27:     uint64 _elapsedTime,
28:     uint64 _auctionDuration,
29:     UD2x18 _targetTimeFraction,
30:     UD2x18 _targetRewardFraction
31:   ) internal pure returns (UD2x18) {
32:     UD60x18 x = convert(_elapsedTime).div(convert(_auctionDuration));

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L5-L8
```javascript
2: 
3: pragma solidity ^0.8.19;
4: 
5: import { RngAuction } from ".RngAuction.sol"; // <= FOUND
6: import { AuctionResult } from ".interfaces/IAuction.sol"; // <= FOUND
7: import { AddressRemapper } from ".abstract/AddressRemapper.sol"; // <= FOUND
8: import { IRngAuctionRelayListener } from ".interfaces/IRngAuctionRelayListener.sol"; // <= FOUND
9: 
10: 
11: error RngNotCompleted();
12: 
13: 
14: 
15: 
16: abstract contract RngAuctionRelayer is AddressRemapper {
17: 
18:     
19:     RngAuction public immutable rngAuction;
20: 
21:     
22:     
23:     constructor(
24:         RngAuction _rngAuction
25:     ) {
26:         rngAuction = _rngAuction;
27:     }
28: 
29:     
30:     
31:     
32:     function encodeCalldata(address rewardRecipient) internal returns (bytes memory) {

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L5-L13
```javascript
2: 
3: pragma solidity ^0.8.0;
4: 
5: import "forge-std/console2.sol"; // <= FOUND
6: 
7: import { ILiquidationSource } from "pt-v5-liquidator-interfaces/interfaces/ILiquidationSource.sol"; // <= FOUND
8: import { PrizePool, IERC20, TwabController } from "pt-v5-prize-pool/PrizePool.sol"; // <= FOUND
9: import { UD60x18, convert } from "prb-math/UD60x18.sol"; // <= FOUND
10: import { UD2x18, intoUD60x18 } from "prb-math/UD2x18.sol"; // <= FOUND
11: import { Ownable } from "openzeppelin/access/Ownable.sol"; // <= FOUND
12: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol"; // <= FOUND
13: import { SafeCast } from "openzeppelin/utils/math/SafeCast.sol"; // <= FOUND
14: 
15: 
16: error OnlyLiquidationPair();
17: 
18: 
19: 
20: 
21: error InitialAvailableExceedsBalance(uint144 initialAvailable, uint256 balance);
22: 
23: 
24: error InsufficientAvailableBalance(uint256 amountOut, uint256 available);
25: 
26: 
27: error UnsupportedTokenIn();
28: 
29: 
30: struct Boost {
31:   address liquidationPair;
32:   UD2x18 multiplierOfTotalSupplyPerSecond;
33:   uint96 tokensPerSecond;
34:   uint144 available;
35:   uint48 lastAccruedAt;
36: }
37: 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L5-L9
```javascript
2: 
3: pragma solidity ^0.8.19;
4: 
5: import { RemoteOwner } from "remote-owner/RemoteOwner.sol"; // <= FOUND
6: import { RemoteOwnerCallEncoder } from "remote-owner/libraries/RemoteOwnerCallEncoder.sol"; // <= FOUND
7: import { ISingleMessageDispatcher } from "erc5164/interfaces/ISingleMessageDispatcher.sol"; // <= FOUND
8: 
9: import { // <= FOUND
10:     RngAuctionRelayer,
11:     RngAuction,
12:     IRngAuctionRelayListener
13: } from "abstract/RngAuctionRelayer.sol";
14: 
15: 
16: 
17: 
18: 
19: contract RngAuctionRelayerRemoteOwner is RngAuctionRelayer {
20: 
21:     
22:     
23:     
24:     event RelayedToDispatcher(address indexed rewardRecipient, bytes32 indexed messageId);
25: 
26:     
27:     ISingleMessageDispatcher public immutable messageDispatcher;
28: 
29:     
30:     
31:     RemoteOwner public immutable account;
32: 
33:     

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L5-L13
```javascript
2: 
3: pragma solidity ^0.8.19;
4: 
5: import { IERC20 } from "openzeppelin/token/ERC20/IERC20.sol"; // <= FOUND
6: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol"; // <= FOUND
7: import { Ownable } from "owner-manager/Ownable.sol"; // <= FOUND
8: import { RNGInterface } from "rng/RNGInterface.sol"; // <= FOUND
9: import { UD2x18 } from "prb-math/UD2x18.sol"; // <= FOUND
10: import { UD60x18, convert, intoUD2x18 } from "prb-math/UD60x18.sol"; // <= FOUND
11: 
12: import { RewardLib } from "libraries/RewardLib.sol"; // <= FOUND
13: import { IAuction, AuctionResult } from "interfaces/IAuction.sol"; // <= FOUND
14: 
15: 
16: 
17: 
18: 
19: 
20: 
21: 
22: 
23: 
24: struct RngAuctionResult {
25:   address recipient;
26:   UD2x18 rewardFraction;
27:   uint32 sequenceId;
28:   RNGInterface rng;
29:   uint32 rngRequestId;
30: }
31: 
32: 
33: 
34: 
35: error AuctionDurationZero();
36: 
37: 

```


</details>


# [NC-22] A function which defines named returns in it's declaration doesn't need to use return 
## Number of instances found
 1 

## Resolution
 Remove the return statement once ensuring it is safe to do so 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L296-L296
```javascript
288:   function getRngResults()
289:     external
290:     returns (
291:       uint256 randomNumber, uint64 rngCompletedAt
292:     )
293:   {
294:     RNGInterface rng = _lastAuction.rng;
295:     uint32 requestId = _lastAuction.rngRequestId;
296:     return (rng.randomNumber(requestId), rng.completedAt(requestId)); // <= FOUND
297:   }

```


</details>


# [NC-23] Unused state variables present
## Number of instances found
 1 

## Resolution
 If these serve no purpose, they should be safely removed 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L79-L79
```javascript
79: address public immutable rngAuctionRelayer; // <= FOUND

```


</details>


# [NC-24] Constants should be on the left side of the 
## Number of instances found
 14 

## Resolution
 Putting constants on the left side of a comparison operator like `==` or `<` is a best practice known as "Yoda conditions", which can help prevent accidental assignment instead of comparison. In some programming languages, if a variable is mistakenly put on the left with a single `=` instead of `==`, it assigns the constant's value to the variable without any compiler error. However, doing this with the constant on the left would generate an error, as constants cannot be assigned values. Although Solidity's static typing system prevents accidental assignments within conditionals, adopting this practice enhances code readability and consistency, especially when developers are working across multiple languages that support this convention. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L122-L122
```javascript
122:     if (_initialAmountIn == 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L126-L126
```javascript
126:     if (_initialAmountOut == 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L298-L298
```javascript
298:    if (_amountOut == 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L314-L314
```javascript
314:     if (purchasePrice == 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L343-L343
```javascript
343:     if (_emissionRate.unwrap() != 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L30-L30
```javascript
30:    if (_amount.unwrap() == 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L61-L61
```javascript
61:    if (_price.unwrap() == 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L266-L266
```javascript
266:     if (deltaTime == 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L332-L332
```javascript
332:    if (_amountInForPeriod > 0 && _amountOutForPeriod > 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L179-L179
```javascript
179:     if (_feeToken != address(0) && _requestFee > 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L143-L143
```javascript
143:    if (_initialAvailable > 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L269-L269
```javascript
269:     if (boost.tokensPerSecond > 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L272-L272
```javascript
272:     if (boost.multiplierOfTotalSupplyPerSecond.unwrap() > 0)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L38-L38
```javascript
38:     if (_emissionRate.unwrap() > 1e18)  // <= FOUND

```


</details>


# [NC-25] Both immutable and constant state variables should be CONSTANT_CASE
## Number of instances found
 14 

## Resolution
 Make found instants CAPITAL_CASE 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L48-L48
```javascript
48: uint32 public immutable targetFirstSaleTime; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L79-L79
```javascript
79: uint64 public immutable auctionDuration; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L82-L82
```javascript
82: uint64 public immutable auctionTargetTime; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L33-L33
```javascript
33: uint256 public immutable toChainId; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L79-L79
```javascript
79: address public immutable rngAuctionRelayer; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L109-L109
```javascript
109: address public immutable vault; // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L41-L41
```javascript
41: uint256 internal immutable _originChainId; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L54-L54
```javascript
54: uint256 public immutable minimumAuctionAmount; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L89-L89
```javascript
89: uint64 public immutable sequencePeriod; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L97-L97
```javascript
97: uint64 public immutable sequenceOffset; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L41-L41
```javascript
41: uint256 public immutable periodLength; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L45-L45
```javascript
45: uint256 public immutable periodOffset; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L32-L32
```javascript
32: address public immutable tokenIn; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L35-L35
```javascript
35: address public immutable tokenOut; // <= FOUND

```


</details>


# [NC-26] Consider using named mappings
## Number of instances found
 2 

## Resolution
 In Solidity version 0.8.18 and beyond mapping parameters can be named. This makes the purpose and function of a given mapping far clearer which in turn improves readability. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L51-L51
```javascript
51:   mapping(LiquidationPair => bool) public deployedPairs; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L14-L14
```javascript
14:   mapping(address => address) internal _destinationAddress; // <= FOUND

```


</details>


# [NC-27] Default address(0) can be returned
## Number of instances found
 4 

## Resolution
 Allowing a function in Solidity to return the default address (address(0)) can be problematic as it can represent uninitialized or invalid addresses. If such an address is utilized in transfer operations or other sensitive actions, it could lead to loss of funds or unpredicted behavior. It's prudent to include checks in your functions to prevent the return of the zero address, enhancing contract security. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L140-L140
```javascript
140:   function target() external returns (address) {
141:     return source.targetOf(tokenIn);
142:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L32-L32
```javascript
32:   function remappingOf(address _addr) public view returns (address) {
33:     if (_destinationAddress[_addr] == address(0)) {
34:       return _addr;
35:     } else {
36:       return _destinationAddress[_addr];
37:     }
38:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L242-L242
```javascript
242:   function targetOf(address _tokenIn) external view override onlyPrizeToken(_tokenIn) returns (address) {
243:     return address(prizePool);
244:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L85-L85
```javascript
85:   function originChainOwner() external view returns (address) {
86:     return _originChainOwner;
87:   }

```


</details>


# [NC-28] Critical functions should be a two step procedure
## Number of instances found
 5 

## Resolution
 Critical functions in Solidity contracts should follow a two-step procedure to enhance security, minimize human error, and ensure proper access control. By dividing sensitive operations into distinct phases, such as initiation and confirmation, developers can introduce a safeguard against unintended actions or unauthorized access. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L347-L347
```javascript
347:   function setNextRngService(RNGInterface _rngService) external onlyOwner  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner  // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L96-L96
```javascript
96:   function setOriginChainOwner(address _newOriginChainOwner) external  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L430-L430
```javascript
430:   function _setNextRngService(RNGInterface _newRng) internal  // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L103-L103
```javascript
103:   function _setOriginChainOwner(address _newOriginChainOwner) internal  // <= FOUND

```


</details>


# [NC-29] Address values should be used through variables rather than used as literals
## Number of instances found
 11 

## Resolution
 Assigning such addresses during construction is preferred as this allows flexibility when deploying to other EVM chains 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L31-L42
```javascript
25:   function fractionalReward(
26:     uint64 _elapsedTime,
27:     uint64 _auctionDuration,
28:     UD2x18 _targetTimeFraction,
29:     UD2x18 _targetRewardFraction
30:   ) internal pure returns (UD2x18) {
31:     UD60x18 x = convert(_elapsedTime).div(convert(_auctionDuration)); // <= FOUND
32:     UD60x18 t = UD60x18.wrap(_targetTimeFraction.unwrap()); // <= FOUND
33:     UD60x18 r = UD60x18.wrap(_targetRewardFraction.unwrap()); // <= FOUND
34:     UD60x18 rewardFraction; // <= FOUND
35:     if (x.gt(t)) {
36:       UD60x18 tDelta = x.sub(t); // <= FOUND
37:       UD60x18 oneMinusT = convert(1).sub(t); // <= FOUND
38:       rewardFraction = r.add(
39:         convert(1).sub(r).mul(tDelta).mul(tDelta).div(oneMinusT).div(oneMinusT)
40:       );
41:     } else {
42:       UD60x18 tDelta = t.sub(x); // <= FOUND
43:       rewardFraction = r.sub(r.mul(tDelta).mul(tDelta).div(t).div(t));
44:     }
45:     return UD2x18.wrap(uint64(rewardFraction.unwrap()));
46:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L262-L274
```javascript
262:   function _computeAvailable(IERC20 _tokenOut) internal view returns (uint256) { // <= FOUND
263:     Boost memory boost = _boosts[_tokenOut];
264:     uint256 deltaTime = block.timestamp - boost.lastAccruedAt;
265:     uint256 deltaAmount;
266:     if (deltaTime == 0) {
267:       return boost.available;
268:     }
269:     if (boost.tokensPerSecond > 0) {
270:       deltaAmount = boost.tokensPerSecond * deltaTime;
271:     }
272:     if (boost.multiplierOfTotalSupplyPerSecond.unwrap() > 0) {
273:       uint256 totalSupply = twabController.getTotalSupplyTwabBetween(address(vault), uint32(boost.lastAccruedAt), uint32(block.timestamp));
274:       deltaAmount += convert(boost.multiplierOfTotalSupplyPerSecond.intoUD60x18().mul(convert(deltaTime)).mul(convert(totalSupply))); // <= FOUND
275:     }
276:     uint256 availableBalance = _tokenOut.balanceOf(address(this));
277:     deltaAmount = availableBalance > deltaAmount ? deltaAmount : availableBalance;
278:     return boost.available + deltaAmount;
279:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L63-L73
```javascript
63:   function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) { // <= FOUND
64:     
65:     
66:     _checkSender();
67:     (bool success, bytes memory returnData) = target.call{ value: value }(data);
68:     
69:     
70:     
71:     if (!success) revert CallFailed(returnData);
72:     assembly {
73:       return (add(returnData, 0x20), mload(returnData)) // <= FOUND
74:     }
75:   }

```


</details>


# [NC-30] Mixed usage of int/uint with int256/uint256
## Number of instances found
 5 

## Resolution
 Use uint256/int256 in place of uint/int to prevent ambiguity 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L12-L12
```javascript
12: error TargetFirstSaleTimeLtPeriodLength(uint passedTargetSaleTime, uint periodLength); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L217-L217
```javascript
217:     uint swapAmountIn = _computeExactAmountIn(_amountOut); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L267-L267
```javascript
267:     uint emissions = uint(convert(_emissionRate.mul(_getElapsedTime()))); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L268-L268
```javascript
268:     uint liquidatable = source.liquidatableBalanceOf(tokenOut); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L306-L306
```javascript
306:     uint purchasePrice = uint256(convert(ContinuousGDA.purchasePrice( // <= FOUND

```


</details>


# [NC-31] Consider adding emergency-stop functionality
## Number of instances found
 11 

## Resolution
 In the event of a security breach or any unforeseen emergency, swiftly suspending all protocol operations becomes crucial. Having a mechanism in place to halt all functions collectively, instead of pausing individual contracts separately, substantially enhances the efficiency of mitigating ongoing attacks or vulnerabilities. This not only quickens the response time to potential threats but also reduces operational stress during these critical periods. Therefore, consider integrating a 'circuit breaker' or 'emergency stop' function into the smart contract system architecture. Such a feature would provide the capability to suspend the entire protocol instantly, which could prove invaluable during a time-sensitive crisis management situation. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L24-L24
```javascript
24: contract LiquidationPair is ILiquidationPair 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L10-L10
```javascript
10: contract LiquidationPairFactory 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L16-L16
```javascript
16: contract LiquidationRouter 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L72-L72
```javascript
72: contract RngAuction is IAuction, Ownable 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L17-L17
```javascript
17: contract RngAuctionRelayerDirect is RngAuctionRelayer 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L18-L18
```javascript
18: contract RngAuctionRelayerRemoteOwner is RngAuctionRelayer 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L45-L45
```javascript
45: contract RngRelayAuction is IRngAuctionRelayListener, IAuction 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L10-L10
```javascript
10: contract AddressRemapper 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L40-L40
```javascript
40: contract VaultBooster is Ownable, ILiquidationSource 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L9-L9
```javascript
9: contract VaultBoosterFactory  

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L29-L29
```javascript
29: contract RemoteOwner is ExecutorAware 

```


</details>


# [NC-32] Remove forge-std import
## Number of instances found
 1 

## Resolution
 Logging and debugging libraries such as forge-std are crucial tools during the development phase of a smart contract, as they provide critical insights into the execution of the contract. However, it's essential to remove or disable these libraries in the production version of your contract. Leaving such libraries active in the final version can lead to unnecessary gas costs, as logging operations consume gas, and it can potentially expose sensitive internal state information. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L4-L4
```javascript
4: import "forge-std/console2.sol"; // <= FOUND

```


</details>


# [NC-33] Some if-statement can be converted to a ternary
## Number of instances found
 2 

## Resolution
 Improving code readability and compactness is an integral part of optimal programming practices. The use of ternary operators in place of if-else conditions is one such measure. Ternary operators allow us to write conditional statements in a more concise manner, thereby enhancing readability and simplicity. They follow the syntax `condition ? exprIfTrue : exprIfFalse`, which interprets as "if the condition is true, evaluate to `exprIfTrue`, else evaluate to `exprIfFalse`". By adopting this approach, we make our code more streamlined and intuitive, which could potentially aid in better understanding and maintenance of the codebase. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L277-L279
```javascript
277:     if (amount < minimumAuctionAmount) {
278:       
279:       amount = 0; // <= FOUND
280:       
281:     }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L269-L270
```javascript
269:     if (boost.tokensPerSecond > 0) {
270:       deltaAmount = boost.tokensPerSecond * deltaTime; // <= FOUND
271:     }

```


</details>


# [NC-34] File is missing NatSpec
## Number of instances found
 1 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { RemoteOwner } from ".RemoteOwner.sol";
5: 
6: library RemoteOwnerCallEncoder {
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
8:         return abi.encodeWithSelector(
9:             RemoteOwner.execute.selector,
10:             target,
11:             value,
12:             data
13:         );
14:         // assembly {
15:         //    return (add(returnData, 0x20), mload(returnData))
16:         // }
17:     }
18: }
19: 

```


</details>


# [NC-35] Addresses shouldn't be hard-coded
## Number of instances found
 7 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L31-L31
```javascript
31:     UD60x18 x = convert(_elapsedTime).div(convert(_auctionDuration)); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L32-L32
```javascript
32:     UD60x18 t = UD60x18.wrap(_targetTimeFraction.unwrap()); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L33-L33
```javascript
33:     UD60x18 r = UD60x18.wrap(_targetRewardFraction.unwrap()); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L36-L36
```javascript
36:       UD60x18 tDelta = x.sub(t); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L37-L37
```javascript
37:       UD60x18 oneMinusT = convert(1).sub(t); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L42-L42
```javascript
42:       UD60x18 tDelta = t.sub(x); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L274-L274
```javascript
274:       deltaAmount += convert(boost.multiplierOfTotalSupplyPerSecond.intoUD60x18().mul(convert(deltaTime)).mul(convert(totalSupply))); // <= FOUND

```


</details>


# [NC-36] Empty bytes check is missing
## Number of instances found
 2 

## Resolution
 When developing smart contracts in Solidity, it's crucial to validate the inputs of your functions. This includes ensuring that the bytes parameters are not empty, especially when they represent crucial data such as addresses, identifiers, or raw data that the contract needs to process.

Missing empty bytes checks can lead to unexpected behaviour in your contract. For instance, certain operations might fail, produce incorrect results, or consume unnecessary gas when performed with empty bytes. Moreover, missing input validation can potentially expose your contract to malicious activity, including exploitation of unhandled edge cases.

To mitigate these issues, always validate that bytes parameters are not empty when the logic of your contract requires it. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L63-L63
```javascript
63:   function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) {
64:     
65:     
66:     _checkSender();
67:     (bool success, bytes memory returnData) = target.call{ value: value }(data);
68:     
69:     
70:     
71:     if (!success) revert CallFailed(returnData);
72:     assembly {
73:       return (add(returnData, 0x20), mload(returnData))
74:     }
75:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L7-L7
```javascript
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
8:         return abi.encodeWithSelector(
9:             RemoteOwner.execute.selector,
10:             target,
11:             value,
12:             data
13:         );
14:         
15:         
16:         
17:     }

```


</details>


# [NC-37] It's not standard to end and begin a code object on the same line
## Number of instances found
 36 

## Resolution
 Placing the closing and opening brackets of distinct code blocks on the same line can impair code readability and clarity, leading to potential misinterpretations. To improve maintainability and reduce the chances of introducing errors, it is advisable to start each code block on a new line, making the boundaries between different code sections clearer and easier to discern unless it is an else statement. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L4-L4
```javascript
4: import { ILiquidationSource } from "pt-v5-liquidator-interfaces/ILiquidationSource.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L5-L5
```javascript
5: import { ILiquidationPair } from "pt-v5-liquidator-interfaces/ILiquidationPair.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L6-L6
```javascript
6: import { SD59x18, uEXP_MAX_INPUT, wrap, convert, unwrap } from "prb-math/SD59x18.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L8-L8
```javascript
8: import { ContinuousGDA } from "libraries/ContinuousGDA.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L5-L5
```javascript
5: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L7-L7
```javascript
7: import { LiquidationPair } from "LiquidationPair.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L8-L8
```javascript
8: import { LiquidationPairFactory } from "LiquidationPairFactory.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L4-L4
```javascript
4: import { SD59x18, convert, unwrap } from "prb-math/SD59x18.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L4-L4
```javascript
4: import { IERC20 } from "openzeppelin/token/ERC20/IERC20.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L6-L6
```javascript
6: import { Ownable } from "owner-manager/Ownable.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L7-L7
```javascript
7: import { RNGInterface } from "rng/RNGInterface.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L4-L4
```javascript
4: import { UD2x18 } from "prb-math/UD2x18.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L9-L9
```javascript
9: import { UD60x18, convert, intoUD2x18 } from "prb-math/UD60x18.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L8-L8
```javascript
8: import { RewardLib } from "libraries/RewardLib.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L10-L10
```javascript
10: import { IAuction, AuctionResult } from "interfaces/IAuction.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L4-L4
```javascript
4: import { RemoteOwner } from "remote-owner/RemoteOwner.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L5-L5
```javascript
5: import { RemoteOwnerCallEncoder } from "remote-owner/libraries/RemoteOwnerCallEncoder.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L6-L6
```javascript
6: import { ISingleMessageDispatcher } from "erc5164/interfaces/ISingleMessageDispatcher.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L5-L5
```javascript
5: import { convert } from "prb-math/UD60x18.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L6-L6
```javascript
6: import { PrizePool } from "pt-v5-prize-pool/PrizePool.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L9-L9
```javascript
9: import { IRngAuctionRelayListener } from "interfaces/IRngAuctionRelayListener.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L11-L11
```javascript
11: import { RngAuction } from "RngAuction.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L5-L5
```javascript
5: import { UD60x18, convert } from "prb-math/UD60x18.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L7-L7
```javascript
7: import { AuctionResult } from ".interfaces/IAuction.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/interfaces/IRngAuctionRelayListener.sol#L4-L4
```javascript
4: import { AuctionResult } from "IAuction.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L4-L4
```javascript
4: import { RngAuction } from ".RngAuction.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L6-L6
```javascript
6: import { AddressRemapper } from ".abstract/AddressRemapper.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L7-L7
```javascript
7: import { IRngAuctionRelayListener } from ".interfaces/IRngAuctionRelayListener.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L6-L6
```javascript
6: import { ILiquidationSource } from "pt-v5-liquidator-interfaces/interfaces/ILiquidationSource.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L7-L7
```javascript
7: import { PrizePool, IERC20, TwabController } from "pt-v5-prize-pool/PrizePool.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L9-L9
```javascript
9: import { UD2x18, intoUD60x18 } from "prb-math/UD2x18.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L10-L10
```javascript
10: import { Ownable } from "openzeppelin/access/Ownable.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L12-L12
```javascript
12: import { SafeCast } from "openzeppelin/utils/math/SafeCast.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L4-L4
```javascript
4: import { VaultBooster, PrizePool } from "VaultBooster.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L4-L4
```javascript
4: import { ExecutorAware } from "erc5164/abstract/ExecutorAware.sol"; // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L4-L4
```javascript
4: import { RemoteOwner } from ".RemoteOwner.sol"; // <= FOUND

```


</details>


# [NC-38] Function missing natspec comments
## Number of instances found
 5 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L398-L398
```javascript
398:   function _computeRewardFraction(uint64 __auctionElapsedTime) internal view returns (UD2x18) {
399:     return
400:       RewardLib.fractionalReward(
401:         __auctionElapsedTime,
402:         auctionDuration,
403:         _auctionTargetTimeFraction,
404:         _lastAuction.rewardFraction
405:       );
406:   }

```
```javascript
  /* ============ External Functions ============ */
  function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) {
    _checkSender();
    (bool success, bytes memory returnData) = target.call{ value: value }(data);
    if (!success) revert CallFailed(returnData);
    assembly {
      return (add(returnData, 0x20), mload(returnData))
    }
  }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L85-L85
```javascript
85:   function originChainOwner() external view returns (address) {
86:     return _originChainOwner;
87:   }

```
```javascript
  /* ============ Internal Functions ============ */
  function _setOriginChainOwner(address _newOriginChainOwner) internal {
    if (_newOriginChainOwner == address(0)) revert OriginChainOwnerZeroAddress();
    _originChainOwner = _newOriginChainOwner;
    emit OriginChainOwnerSet(_newOriginChainOwner);
  }

```
```javascript
    function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
        return abi.encodeWithSelector(
            RemoteOwner.execute.selector,
            target,
            value,
            data
        );
        //    return (add(returnData, 0x20), mload(returnData))
    }

```


</details>


# [NC-39] NatSpec @param is missing
## Number of instances found
 11 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>

```javascript
  /// @inheritdoc ILiquidationPair
  function computeExactAmountIn(uint256 _amountOut) external returns (uint256) {
    _checkUpdateAuction();
    return _computeExactAmountIn(_amountOut);
  }

```
```javascript
  /// @inheritdoc ILiquidationPair
  function estimateAmountOut(uint256 __amountIn) external returns (uint256) {
    _checkUpdateAuction();
    return uint(convert(ContinuousGDA.purchaseAmount(
      convert(int(__amountIn)),
      _emissionRate,
      _initialPrice,
      decayConstant,
      _getElapsedTime()
    )));
  }

```
```javascript
  /// @inheritdoc ILiquidationPair
  function swapExactAmountOut(
    address _account,
    uint256 _amountOut,
    uint256 _amountInMax
  ) external returns (uint256) {
    _checkUpdateAuction();
    uint swapAmountIn = _computeExactAmountIn(_amountOut);
    if (swapAmountIn > _amountInMax) {
      revert SwapExceedsMax(_amountInMax, swapAmountIn);
    }
    _amountInForPeriod += uint96(swapAmountIn);
    _amountOutForPeriod += uint96(_amountOut);
    _lastAuctionTime += uint48(uint256(convert(convert(int256(_amountOut)).div(_emissionRate))));
    source.liquidate(_account, tokenIn, swapAmountIn, tokenOut, _amountOut);
    return swapAmountIn;
  }

```
```javascript
  /// @notice Computes the reward fraction for the given auction elapsed time.
  function computeRewardFraction(uint64 __auctionElapsedTime) external view returns (UD2x18) {
    return _computeRewardFraction(__auctionElapsedTime);
  }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L398-L398
```javascript
398:   function _computeRewardFraction(uint64 __auctionElapsedTime) internal view returns (UD2x18) {
399:     return
400:       RewardLib.fractionalReward(
401:         __auctionElapsedTime,
402:         auctionDuration,
403:         _auctionTargetTimeFraction,
404:         _lastAuction.rewardFraction
405:       );
406:   }

```
```javascript
  /**
   * @notice Calculates the reward fraction for an auction if it were to be completed after the elapsed time.
   * @dev Uses the last sold fraction as the target price for this auction.
   * @return The reward fraction as a UD2x18 value
   */
  function _fractionalReward(uint64 _elapsedSeconds) internal view returns (UD2x18) {
    return
      RewardLib.fractionalReward(
        _elapsedSeconds,
        _auctionDurationSeconds,
        _auctionTargetTimeFraction,
        _auctionResults.rewardFraction
      );
  }

```
```javascript

  /* ============ Public Functions ============ */
  /**
   * @notice Retrieves the remapping for the given address.
   * @dev If the address does not have a remapping, the input address will be returned.
   * @return The remapped destination address
   */
  function remappingOf(address _addr) public view returns (address) {
    if (_destinationAddress[_addr] == address(0)) {
      return _addr;
    } else {
      return _destinationAddress[_addr];
    }
  }

```
```javascript
  /* ============ External Functions ============ */
  function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) {
    _checkSender();
    (bool success, bytes memory returnData) = target.call{ value: value }(data);
    if (!success) revert CallFailed(returnData);
    assembly {
      return (add(returnData, 0x20), mload(returnData))
    }
  }

```
```javascript
  /* ============ Setters ============ */
  /**
   * @notice Set the OriginChainOwner address.
   * @dev Can only be called once.
   *      If the transaction get front-run at deployment, we can always re-deploy the contract.
   */
  function setOriginChainOwner(address _newOriginChainOwner) external {
    _checkSender();
    _setOriginChainOwner(_newOriginChainOwner);
  }

```
```javascript
  /* ============ Internal Functions ============ */
  function _setOriginChainOwner(address _newOriginChainOwner) internal {
    if (_newOriginChainOwner == address(0)) revert OriginChainOwnerZeroAddress();
    _originChainOwner = _newOriginChainOwner;
    emit OriginChainOwnerSet(_newOriginChainOwner);
  }

```
```javascript
    function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
        return abi.encodeWithSelector(
            RemoteOwner.execute.selector,
            target,
            value,
            data
        );
        //    return (add(returnData, 0x20), mload(returnData))
    }

```


</details>


# [NC-40] NatSpec @return argument is missing
## Number of instances found
 5 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L239-L239
```javascript
239:   function getLastAuction() external view returns (RngAuctionResult memory) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L219-L219
```javascript
219:   function getLastAuctionResult()
220:     external
221:     view
222:     returns (AuctionResult memory)
223:   

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L63-L63
```javascript
63:   function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L7-L7
```javascript
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) 

```


</details>


# [NC-41] Natspec @title is missing from contract/interface/library
## Number of instances found
 1 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L6-L6
```javascript
6: library RemoteOwnerCallEncoder {
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
8:         return abi.encodeWithSelector(
9:             RemoteOwner.execute.selector,
10:             target,
11:             value,
12:             data
13:         );
14:         
15:         //    return (add(returnData, 0x20), mload(returnData))
16:         
17:     }
18: }

```


</details>


# [NC-42] Natspec @author is missing from contract/interface/library
## Number of instances found
 1 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L6-L6
```javascript
6: library RemoteOwnerCallEncoder {
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
8:         return abi.encodeWithSelector(
9:             RemoteOwner.execute.selector,
10:             target,
11:             value,
12:             data
13:         );
14:         
15:         //    return (add(returnData, 0x20), mload(returnData))
16:         
17:     }
18: }

```


</details>


# [NC-43] Assembly code blocks should be thoroughly commented
## Number of instances found
 1 

## Resolution
 In Solidity, assembly blocks are often harder to read and understand due to their low-level nature. Detailed comments can make the code's purpose and functionality clear, aiding in maintenance, debugging, and reviews. Moreover, comments can be crucial for auditors and other developers to understand the contract's security implications, reducing the risk of oversights and vulnerabilities. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L72-L72
```javascript
72: 
73:     assembly {
74:       return (add(returnData, 0x20), mload(returnData))
75:     }

```


</details>


# [NC-44] Return bool not explicit
## Number of instances found
 1 

## Resolution
 In instances where true is returned, there should also be an explicit return false within the function to ensure maintainability and prevent ambiguity 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L211-L236
```javascript
211:   function liquidate(
212:     address _account,
213:     address _tokenIn,
214:     uint256 _amountIn,
215:     address _tokenOut,
216:     uint256 _amountOut
217:   ) external override onlyPrizeToken(_tokenIn) onlyLiquidationPair(_tokenOut) returns (bool) {
218:     uint256 amountAvailable = _computeAvailable(IERC20(_tokenOut));
219:     if (_amountOut > amountAvailable) {
220:       revert InsufficientAvailableBalance(_amountOut, amountAvailable);
221:     }
222:     amountAvailable = (amountAvailable - _amountOut);
223:     _boosts[IERC20(_tokenOut)].available = amountAvailable.toUint144();
224:     _boosts[IERC20(_tokenOut)].lastAccruedAt = uint48(block.timestamp);
225:     prizePool.contributePrizeTokens(vault, _amountIn);
226:     IERC20(_tokenOut).safeTransfer(_account, _amountOut);
227: 
228:     emit Liquidated(
229:       IERC20(_tokenOut),
230:       _account,
231:       _amountIn,
232:       _amountOut,
233:       amountAvailable
234:     );
235: 

```


</details>


# [NC-45] Do not use underscore at the end of variable name
## Number of instances found
 5 

## Resolution
 Adopting a consistent and clear naming convention enhances code readability and maintainability. In Solidity, appending an underscore at the end of a variable name is unconventional and can lead to confusion. It is generally advisable to stick to accepted naming practices to promote ease of understanding and use.
 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L341-L341
```javascript
341:     SD59x18 emissionRate_ = _computeEmissionRate(); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L148-L148
```javascript
148:     if (sequencePeriod_ == 0) revert SequencePeriodZero(); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L111-L111
```javascript
111:     if (auctionDurationSeconds_ == 0) revert AuctionDurationZero(); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L112-L112
```javascript
112:     if (auctionTargetTime_ == 0) revert AuctionTargetTimeZero(); // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L56-L56
```javascript
56:     if (originChainId_ == 0) revert OriginChainIdZero(); // <= FOUND

```


</details>


# [NC-46] Consider using SMTChecker
## Number of instances found
 17 

## Resolution
 The SMTChecker is a valuable tool for Solidity developers as it helps detect potential vulnerabilities and logical errors in the contract's code. By utilizing Satisfiability Modulo Theories (SMT) solvers, it can reason about the potential states a contract can be in, and therefore, identify conditions that could lead to undesirable behavior. This automatic formal verification can catch issues that might otherwise be missed in manual code reviews or standard testing, enhancing the overall contract's security and reliability. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { ExecutorAware } from "erc5164/abstract/ExecutorAware.sol";
5: 
6: /* ============ Custom Errors ============ */
7: 
8: /// @notice Thrown when the originChainId passed to the constructor is zero.
9: error OriginChainIdZero();
10: 
11: /// @notice Thrown when the OriginChainOwner address passed to the constructor is zero address.
12: error OriginChainOwnerZeroAddress();
13: 
14: /// @notice Thrown when the message was dispatched from an unsupported chain ID.
15: error OriginChainIdUnsupported(uint256 fromChainId);
16: 
17: /// @notice Thrown when the message was not executed by the executor.
18: error LocalSenderNotExecutor(address sender);
19: 
20: /// @notice Thrown when the message was not dispatched by the OriginChainOwner on the origin chain.
21: error OriginSenderNotOwner(address sender);
22: 
23: /// @notice Thrown when the call to the target contract failed.
24: error CallFailed(bytes returnData);
25: 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { RemoteOwner } from ".RemoteOwner.sol";
5: 
6: library RemoteOwnerCallEncoder {
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
8:         return abi.encodeWithSelector(
9:             RemoteOwner.execute.selector,
10:             target,
11:             value,
12:             data
13:         );
14:         // assembly {
15:         //    return (add(returnData, 0x20), mload(returnData))
16:         // }
17:     }
18: }
19: 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { UD2x18 } from "prb-math/UD2x18.sol";
5: import { convert } from "prb-math/UD60x18.sol";
6: import { PrizePool } from "pt-v5-prize-pool/PrizePool.sol";
7: 
8: import { RewardLib } from "libraries/RewardLib.sol";
9: import { IRngAuctionRelayListener } from "interfaces/IRngAuctionRelayListener.sol";
10: import { IAuction, AuctionResult } from "interfaces/IAuction.sol";
11: import { RngAuction } from "RngAuction.sol";
12: 
13: /* ============ Custom Errors ============ */
14: 
15: /// @notice Thrown if the auction period is zero.
16: error AuctionDurationZero();
17: 
18: /// @notice Thrown if the auction target time is zero.
19: error AuctionTargetTimeZero();
20: 
21: /**
22:   * @notice Thrown if the auction target time exceeds the auction duration.
23:   * @param auctionTargetTime The auction target time to complete in seconds
24:   * @param auctionDuration The auction duration in seconds
25:   */

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/interfaces/IAuction.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { UD2x18 } from "prb-math/UD2x18.sol";
5: 
6: /* ============ Structs ============ */
7: 
8: /**
9:  * @notice Stores the results of an auction.
10:  * @param recipient The recipient of the auction awards
11:  * @param rewardFraction The fraction of the available rewards to be sent to the recipient
12:  */
13: struct AuctionResult {
14:   address recipient;
15:   UD2x18 rewardFraction;
16: }
17: 
18: /* ============ Interface ============ */
19: 
20: /// @title IAuction
21: /// @author G9 Software Inc.
22: /// @notice Defines some common interfaces for auctions
23: interface IAuction {
24:   /**
25:    * @notice Returns the auction duration in seconds.

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { UD2x18 } from "prb-math/UD2x18.sol";
5: import { UD60x18, convert } from "prb-math/UD60x18.sol";
6: 
7: import { AuctionResult } from ".interfaces/IAuction.sol";
8: 
9: /// @title RewardLib
10: /// @author G9 Software Inc.
11: /// @notice Library for calculating auction rewards.
12: /// @dev This library uses a parabolic fractional dutch auction (PFDA) to calculate rewards. For more details see https://dev.pooltogether.com/protocol/next/design/draw-auction#parabolic-fractional-dutch-auction-pfda
13: library RewardLib {
14:   /* ============ Internal Functions ============ */
15: 
16:   /**
17:    * @notice Calculates the fractional reward using a Parabolic Fractional Dutch Auction (PFDA)
18:    * given the elapsed time, auction time, and target sale parameters.
19:    * @param _elapsedTime The elapsed time since the start of the auction in seconds
20:    * @param _auctionDuration The auction duration in seconds
21:    * @param _targetTimeFraction The target sale time as a fraction of the total auction duration (0.0,1.0]
22:    * @param _targetRewardFraction The target fractional sale price
23:    * @return The reward fraction as a UD2x18 fraction
24:    */
25:   function fractionalReward(

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import {
5:     RngAuctionRelayer,
6:     RngAuction,
7:     IRngAuctionRelayListener
8: } from "abstract/RngAuctionRelayer.sol";
9: 
10: /// @notice Emitted when the relay call fails
11: /// @param returnData The revert message from the relay call
12: error DirectRelayFailed(bytes returnData);
13: 
14: /// @title RngAuctionRelayerDirect
15: /// @author G9 Software Inc.
16: /// @notice This contract will allow anyone to trigger the relay of RNG results to an IRngAuctionRelayListener.
17: contract RngAuctionRelayerDirect is RngAuctionRelayer {
18: 
19:     /// @notice Emitted when the relay was successful.
20:     /// @param rewardRecipient The address of the reward recipient.
21:     /// @param returnData The return data from the relay listener.
22:     event DirectRelaySuccess(address indexed rewardRecipient, bytes returnData);
23: 
24:     /// @notice Constructs a new contract
25:     /// @param _rngAuction The RNG auction to pull results from.

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: /**
5:  * @title AddressRemapper
6:  * @author Generation Software Team
7:  * @notice Allows addresses to provide a remapping to a new address.
8:  * @dev The RngAuction lives on L1, but the rewards are given out on L2s. This contract allows the L1 reward recipients to remap their addresses to their L2 addresses if needed.
9:  */
10: contract AddressRemapper {
11:   /* ============ Variables ============ */
12: 
13:   /// @notice User-defined address remapping
14:   mapping(address => address) internal _destinationAddress;
15: 
16:   /* ============ Events ============ */
17: 
18:   /**
19:    @notice Emitted when a remapping is set.
20:    @param caller Caller address
21:    @param destination Remapped destination address that will be used in place of the caller address
22:    */
23:   event AddressRemapped(address indexed caller, address indexed destination);
24: 
25:   /* ============ Public Functions ============ */

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: 
3: pragma solidity 0.8.19;
4: 
5: import "LiquidationPair.sol";
6: 
7: /// @title LiquidationPairFactory
8: /// @author G9 Software Inc.
9: /// @notice Factory contract for deploying LiquidationPair contracts.
10: contract LiquidationPairFactory {
11: 
12:   /* ============ Events ============ */
13: 
14:   /// @notice Emitted when a new LiquidationPair is created
15:   /// @param pair The address of the new pair
16:   /// @param source The liquidation source that the pair is using
17:   /// @param tokenIn The input token for the pair
18:   /// @param tokenOut The output token for the pair
19:   /// @param periodLength The duration of auctions
20:   /// @param periodOffset The start time offset of auctions
21:   /// @param targetFirstSaleTime The target time for the first auction
22:   /// @param decayConstant The decay constant that the pair is using
23:   /// @param initialAmountIn The initial amount of input tokens (used to compute initial exchange rate)
24:   /// @param initialAmountOut The initial amount of output tokens (used to compute initial exchange rate)
25:   /// @param minimumAuctionAmount The minimum auction size in output tokens

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { RngAuction } from ".RngAuction.sol";
5: import { AuctionResult } from ".interfaces/IAuction.sol";
6: import { AddressRemapper } from ".abstract/AddressRemapper.sol";
7: import { IRngAuctionRelayListener } from ".interfaces/IRngAuctionRelayListener.sol";
8: 
9: /// @notice Emitted when the RNG has not yet completed
10: error RngNotCompleted();
11: 
12: /// @title RngAuctionRelayer
13: /// @author G9 Software Inc.
14: /// @notice Base contarct that relays RNG auction results to a listener
15: abstract contract RngAuctionRelayer is AddressRemapper {
16: 
17:     /// @notice The RNG Auction to get the random number from
18:     RngAuction public immutable rngAuction;
19: 
20:     /// @notice Constructs a new contract
21:     /// @param _rngAuction The RNG auction to retrieve the random number from
22:     constructor(
23:         RngAuction _rngAuction
24:     ) {
25:         rngAuction = _rngAuction;

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity ^0.8.0;
3: 
4: import { VaultBooster, PrizePool } from "VaultBooster.sol";
5: 
6: /// @title VaultBoosterFactory
7: /// @author G9 Software Inc.
8: /// @notice Factory contract for VaultBooster
9: contract VaultBoosterFactory  {
10: 
11:     /// @notice Emitted when a new VaultBooster is created
12:     /// @param vaultBooster The address of the new Vault Booster
13:     /// @param prizePool The address of the prize pool to contribute to
14:     /// @param vault The address of the vault to contribute for
15:     /// @param owner The owner of the VaultBooster
16:     event CreatedVaultBooster(
17:         VaultBooster indexed vaultBooster,
18:         PrizePool indexed prizePool,
19:         address indexed vault,
20:         address owner
21:     );
22: 
23:     /// @notice Creates a new vault booster contract
24:     /// @param _prizePool The prize pool to contribute to
25:     /// @param _vault The vault to contribute for

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity 0.8.19;
3: 
4: import "openzeppelin/token/ERC20/IERC20.sol";
5: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol";
6: 
7: import { LiquidationPair } from "LiquidationPair.sol";
8: import { LiquidationPairFactory } from "LiquidationPairFactory.sol";
9: 
10: error UndefinedLiquidationPairFactory();
11: error UnknownLiquidationPair(LiquidationPair liquidationPair);
12: 
13: /// @title LiquidationRouter
14: /// @author G9 Software Inc.
15: /// @notice Serves as the user-facing swapping interface for Liquidation Pairs.
16: contract LiquidationRouter {
17:   using SafeERC20 for IERC20;
18: 
19:   /* ============ Events ============ */
20: 
21:   /// @notice Emitted when the router is created
22:   event LiquidationRouterCreated(LiquidationPairFactory indexed liquidationPairFactory);
23: 
24:   /// @notice Emitted after a swap occurs
25:   /// @param liquidationPair The pair that was swapped against

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/interfaces/IRngAuctionRelayListener.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { AuctionResult } from "IAuction.sol";
5: 
6: /// @title IRngAuctionRelayListener
7: /// @author G9 Software Inc.
8: /// @notice Interface to receive RNG auction relays
9: interface IRngAuctionRelayListener {
10: 
11:     /// @notice Called by the relayer when the RNG auction is complete
12:     /// @param randomNumber The random number generated by the RNG auction
13:     /// @param rngCompletedAt The timestamp when the RNG service delivered the random number
14:     /// @param rewardRecipient The address of the recipient for the relay reward
15:     /// @param sequenceId The sequence id of the RNG auction
16:     /// @return any custom data it likes to track the relay.
17:     function rngComplete(
18:         uint256 randomNumber,
19:         uint256 rngCompletedAt,
20:         address rewardRecipient,
21:         uint32 sequenceId,
22:         AuctionResult calldata auctionResult
23:     ) external returns (bytes32);
24: }
25: 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity ^0.8.0;
3: 
4: import "forge-std/console2.sol";
5: 
6: import { ILiquidationSource } from "pt-v5-liquidator-interfaces/interfaces/ILiquidationSource.sol";
7: import { PrizePool, IERC20, TwabController } from "pt-v5-prize-pool/PrizePool.sol";
8: import { UD60x18, convert } from "prb-math/UD60x18.sol";
9: import { UD2x18, intoUD60x18 } from "prb-math/UD2x18.sol";
10: import { Ownable } from "openzeppelin/access/Ownable.sol";
11: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol";
12: import { SafeCast } from "openzeppelin/utils/math/SafeCast.sol";
13: 
14: /// @notice Emitted when someone tries to call liquidate and isn't the liquidation pair
15: error OnlyLiquidationPair();
16: 
17: /// @notice Emitted when the initial available exceeds the balance
18: /// @param initialAvailable The initial available
19: /// @param balance The actual token balance
20: error InitialAvailableExceedsBalance(uint144 initialAvailable, uint256 balance);
21: 
22: /// @notice Emitted when the liquidator attempts to liquidate more than the available balance
23: error InsufficientAvailableBalance(uint256 amountOut, uint256 available);
24: 
25: /// @notice Emitted when the liquidator attempts to liquidate for a token other than the prize token 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity 0.8.19;
3: 
4: import { ILiquidationSource } from "pt-v5-liquidator-interfaces/ILiquidationSource.sol";
5: import { ILiquidationPair } from "pt-v5-liquidator-interfaces/ILiquidationPair.sol";
6: import { SD59x18, uEXP_MAX_INPUT, wrap, convert, unwrap } from "prb-math/SD59x18.sol";
7: 
8: import { ContinuousGDA } from "libraries/ContinuousGDA.sol";
9: 
10: error AmountInZero();
11: error AmountOutZero();
12: error TargetFirstSaleTimeLtPeriodLength(uint passedTargetSaleTime, uint periodLength);
13: error SwapExceedsAvailable(uint256 amountOut, uint256 available);
14: error SwapExceedsMax(uint256 amountInMax, uint256 amountIn);
15: error DecayConstantTooLarge(SD59x18 maxDecayConstant, SD59x18 decayConstant);
16: error PurchasePriceIsZero(uint256 amountOut);
17: 
18: /***
19:  * @title LiquidationPair
20:  * @author G9 Software Inc.
21:  * @notice Auctions one token for another in a periodic continuous gradual dutch auction. Auctions occur over a limit period so that the price can be adjusted.
22:  * @dev This contract is designed to be used with the LiquidationRouter contract.
23:  */
24: contract LiquidationPair is ILiquidationPair {
25: 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity 0.8.19;
3: 
4: import { SD59x18, convert, unwrap } from "prb-math/SD59x18.sol";
5: 
6: /// @title ContinuousGDA
7: /// @author G9 Software Inc.
8: /// @notice Implements the Continous Gradual Dutch Auction formula
9: /// See https://www.paradigm.xyz/2022/04/gda
10: /// @dev Pricing formula adapted from https://github.com/FrankieIsLost/gradual-dutch-auction/blob/master/src/ContinuousGDA.sol
11: library ContinuousGDA {
12: 
13:   /// @notice a helpful constant
14:   SD59x18 internal constant ONE = SD59x18.wrap(1e18);
15: 
16:   /// @notice Calculate purchase price for a given amount of tokens
17:   /// @param _amount The amount of tokens to purchase
18:   /// @param _emissionRate The emission rate of the CGDA
19:   /// @param _k The initial price of the CGDA
20:   /// @param _decayConstant The decay constant of the CGDA
21:   /// @param _timeSinceLastAuctionStart The elapsed time since the last consumed timestamp
22:   /// @return The purchase price for the given amount of tokens
23:   function purchasePrice(
24:     SD59x18 _amount,
25:     SD59x18 _emissionRate,

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { RemoteOwner } from "remote-owner/RemoteOwner.sol";
5: import { RemoteOwnerCallEncoder } from "remote-owner/libraries/RemoteOwnerCallEncoder.sol";
6: import { ISingleMessageDispatcher } from "erc5164/interfaces/ISingleMessageDispatcher.sol";
7: 
8: import {
9:     RngAuctionRelayer,
10:     RngAuction,
11:     IRngAuctionRelayListener
12: } from "abstract/RngAuctionRelayer.sol";
13: 
14: /// @title RngAuctionRelayerRemoteOwner
15: /// @author G9 Software Inc.
16: /// @notice This contract allows anyone to relay RNG results to an IRngAuctionRelayListener on another chain.
17: /// @dev This contract uses a Remote Owner, which allows a contract on one chain to operate an address on another chain.
18: contract RngAuctionRelayerRemoteOwner is RngAuctionRelayer {
19: 
20:     /// @notice Emitted when the relay was successfully dispatched to the ERC-5164 Dispatcher
21:     /// @param rewardRecipient The address that shall receive the RNG relay reward.
22:     /// @param messageId The message ID of the dispatched message.
23:     event RelayedToDispatcher(address indexed rewardRecipient, bytes32 indexed messageId);
24: 
25:     /// @notice The ERC-5164 Dispatcher to use to bridge messages

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { IERC20 } from "openzeppelin/token/ERC20/IERC20.sol";
5: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol";
6: import { Ownable } from "owner-manager/Ownable.sol";
7: import { RNGInterface } from "rng/RNGInterface.sol";
8: import { UD2x18 } from "prb-math/UD2x18.sol";
9: import { UD60x18, convert, intoUD2x18 } from "prb-math/UD60x18.sol";
10: 
11: import { RewardLib } from "libraries/RewardLib.sol";
12: import { IAuction, AuctionResult } from "interfaces/IAuction.sol";
13: 
14: /**
15:   * @notice The results of a successful RNG auction.
16:   * @param recipient The recipient of the auction reward
17:   * @param rewardFraction The reward fraction that the user will receive
18:   * @param sequenceId The id of the sequence that this auction belonged to
19:   * @param rng The RNG service that was used to generate the random number
20:   * @param rngRequestId The id of the RNG request that was made
21:   * @dev   The `sequenceId` value should not be assumed to be the same as a prize pool drawId, but the sequence and offset should match the prize pool.
22:   */
23: struct RngAuctionResult {
24:   address recipient;
25:   UD2x18 rewardFraction;

```


</details>


# [NC-47] Contracts should have full test coverage
## Number of instances found
 1 

## Resolution
 Attaining 100% code coverage is not an assurance of a bug-free codebase, but it significantly improves the likelihood of identifying simple bugs and aids in maintaining a stable codebase by preventing regressions during code modifications. Additionally, to achieve complete coverage, code writers usually have to structure their code more modularly, which implies testing each component independently. This reduces the complex interdependencies between modules and layers, creating a more understandable and auditable codebase. Consequently, this practice aids in enhancing code maintainability and reduces the risk of introducing bugs during future changes. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L24-L24
```javascript
24: all // <= FOUND

```


</details>


# [NC-48] Consider using SafeTransferLib.safeTransferETH() or Address.sendValue() for clearer semantic meaning
## Number of instances found
 2 

## Resolution
 For improved code readability and better semantic understanding, it's recommended to use OpenZeppelin's SafeTransferLib.safeTransferETH() or Address.sendValue(). These functions explicitly describe their operation with their naming convention, increasing the comprehensibility of the code. Their usage over lower-level calls enhances the maintainability of your smart contract code by clearly indicating the purpose of the function.  

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L63-L67
```javascript
63:   function execute(address target, uint256 value, bytes calldata data) external returns (bytes memory) { // <= FOUND
64:     
65:     
66:     _checkSender();
67:     (bool success, bytes memory returnData) = target.call{ value: value }(data); // <= FOUND
68:     
69:     
70:     
71:     if (!success) revert CallFailed(returnData);
72:     assembly {
73:       return (add(returnData, 0x20), mload(returnData))
74:     }
75:   }

```


</details>


# [GAS-1] It is more efficient to use block.timestamp directly rather than calling a function to return it
## Number of instances found
 1 

## Resolution
 Creating a function to return block.timestamp is gas inefficient due to the overhead of function storage and execution, while directly accessing block.timestamp in your contract code or as a function argument is a more gas-efficient alternative. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L358-L358
```javascript
357:   function _currentTime() internal view returns (uint64) {
358:     return uint64(block.timestamp); // <= FOUND
359:   }

```


</details>


# [GAS-2] The use of a logical AND in place of double if is slightly less gas efficient in instances where there isn't a corresponding else statement for the given if statement
## Number of instances found
 4 

## Resolution
 Using a double if statement instead of logical AND (&&) can provide similar short-circuiting behavior whereas double if is slightly more efficient. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L332-L332
```javascript
331:   function _updateAuction(uint256 __period) internal {
332:     if (_amountInForPeriod > 0 && _amountOutForPeriod > 0) { // <= FOUND
333:       
334:       _lastNonZeroAmountIn = _amountInForPeriod;
335:       _lastNonZeroAmountOut = _amountOutForPeriod;
336:     }
337:     _amountInForPeriod = 0;
338:     _amountOutForPeriod = 0;
339:     _lastAuctionTime = uint48(periodOffset + periodLength * __period);
340:     _period = uint16(__period);
341:     SD59x18 emissionRate_ = _computeEmissionRate();
342:     _emissionRate = emissionRate_;
343:     if (_emissionRate.unwrap() != 0) {
344:       
345:       SD59x18 timeSinceLastAuctionStart = convert(int(uint(targetFirstSaleTime)));
346:       SD59x18 purchaseAmount = timeSinceLastAuctionStart.mul(emissionRate_);
347:       SD59x18 exchangeRateAmountInToAmountOut = convert(int(uint(_lastNonZeroAmountIn))).div(convert(int(uint(_lastNonZeroAmountOut))));
348:       SD59x18 price = exchangeRateAmountInToAmountOut.mul(purchaseAmount);
349:       _initialPrice = ContinuousGDA.computeK(
350:         emissionRate_,
351:         decayConstant,
352:         timeSinceLastAuctionStart,
353:         purchaseAmount,
354:         price
355:       );
356:     } else {

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L179-L179
```javascript
170:   function startRngRequest(address _rewardRecipient) external {
171:     if (!_canStartNextSequence()) revert CannotStartNextSequence();
172: 
173:     RNGInterface rng = _nextRng;
174: 
175:     uint64 _auctionElapsedTimeSeconds = _auctionElapsedTime();
176:     if (_auctionElapsedTimeSeconds > auctionDuration) revert AuctionExpired();
177: 
178:     (address _feeToken, uint256 _requestFee) = rng.getRequestFee();
179:     if (_feeToken != address(0) && _requestFee > 0) { // <= FOUND
180:       if (IERC20(_feeToken).balanceOf(address(this)) < _requestFee) {
181:         
182:         IERC20(_feeToken).transferFrom(msg.sender, address(this), _requestFee);
183:       }
184:       
185:       IERC20(_feeToken).safeIncreaseAllowance(address(rng), _requestFee);
186:     }
187: 
188:     (uint32 rngRequestId,) = rng.requestRandomNumber();
189:     uint32 sequenceId = _openSequenceId();
190:     UD2x18 rewardFraction = _currentFractionalReward();
191: 
192:     _lastAuction = RngAuctionResult({
193:       recipient: _rewardRecipient,
194:       rewardFraction: rewardFraction,
195:       sequenceId: sequenceId,
196:       rng: rng,
197:       rngRequestId: rngRequestId
198:     });
199: 
200:     emit RngAuctionCompleted(
201:       _rewardRecipient,
202:       sequenceId,
203:       rng,

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L224-L224
```javascript
223:   function isAuctionOpen() external view returns (bool) {
224:     return _canStartNextSequence() && _auctionElapsedTime() <= auctionDuration; // <= FOUND
225:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L423-L423
```javascript
420:   function _isRngComplete() internal view returns (bool) {
421:     RNGInterface rng = _lastAuction.rng;
422:     uint32 requestId = _lastAuction.rngRequestId;
423:     return !_canStartNextSequence() && rng.isRequestComplete(requestId); // <= FOUND
424:   }

```


</details>


# [GAS-3] x + y is more efficient than using += for state variables (likewise for -=)
## Number of instances found
 3 

## Resolution
 In instances found where either += or -= are used against state variables use x = x + y instead 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L221-L223
```javascript
211:   function swapExactAmountOut(
212:     address _account,
213:     uint256 _amountOut,
214:     uint256 _amountInMax
215:   ) external returns (uint256) {
216:     _checkUpdateAuction();
217:     uint swapAmountIn = _computeExactAmountIn(_amountOut);
218:     if (swapAmountIn > _amountInMax) {
219:       revert SwapExceedsMax(_amountInMax, swapAmountIn);
220:     }
221:     _amountInForPeriod += uint96(swapAmountIn); // <= FOUND
222:     _amountOutForPeriod += uint96(_amountOut); // <= FOUND
223:     _lastAuctionTime += uint48(uint256(convert(convert(int256(_amountOut)).div(_emissionRate)))); // <= FOUND
224:     source.liquidate(_account, tokenIn, swapAmountIn, tokenOut, _amountOut);
225:     return swapAmountIn;
226:   }

```


</details>


# [GAS-4] Calling .length in a for loop wastes gas
## Number of instances found
 1 

## Resolution
 Rather than calling .length for an array in a for loop declaration, it is far more gas efficient to cache this length before and use that instead. This will prevent the array length from being called every loop iteration 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L167-L167
```javascript
167: for (uint8 i = 0; i < _rewards.length; i++)  // <= FOUND

```


</details>


# [GAS-5] ++X costs slightly less gas than X++ (same with --)
## Number of instances found
 2 

## Resolution
 Move the ++/-- action to the left of the variable 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L167-L167
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) {
138:     if (_sequenceHasCompleted(_sequenceId)) revert SequenceAlreadyCompleted();
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt);
140:     if (_auctionElapsedSeconds > (_auctionDurationSeconds-1)) revert AuctionExpired();
141:     
142:     UD2x18 rewardFraction = _fractionalReward(_auctionElapsedSeconds);
143:     _auctionResults.rewardFraction = rewardFraction;
144:     _auctionResults.recipient = _rewardRecipient;
145:     _lastSequenceId = _sequenceId;
146: 
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2);
148:     auctionResults[0] = _rngAuctionResult;
149:     auctionResults[1] = AuctionResult({
150:       rewardFraction: rewardFraction,
151:       recipient: _rewardRecipient
152:     });
153: 
154:     uint32 drawId = prizePool.closeDraw(_randomNumber);
155: 
156:     uint256 futureReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
157:     uint256[] memory _rewards = RewardLib.rewards(auctionResults, futureReserve);
158: 
159:     emit RngSequenceCompleted(
160:       _sequenceId,
161:       drawId,
162:       _rewardRecipient,
163:       _auctionElapsedSeconds,
164:       rewardFraction
165:     );
166: 
167:     for (uint8 i = 0; i < _rewards.length; i++) { // <= FOUND
168:       uint104 _reward = uint104(_rewards[i]);
169:       if (_reward > 0) {
170:         prizePool.withdrawReserve(auctionResults[i].recipient, _reward);
171:         emit AuctionRewardDistributed(_sequenceId, auctionResults[i].recipient, i, _reward);
172:       }
173:     }
174: 
175:     return bytes32(uint(drawId));
176:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L65-L65
```javascript
58:   function rewards(
59:     AuctionResult[] memory _auctionResults,
60:     uint256 _reserve
61:   ) internal pure returns (uint256[] memory) {
62:     uint256 remainingReserve = _reserve;
63:     uint256 _auctionResultsLength = _auctionResults.length;
64:     uint256[] memory _rewards = new uint256[](_auctionResultsLength);
65:     for (uint256 i; i < _auctionResultsLength; i++) { // <= FOUND
66:       _rewards[i] = reward(_auctionResults[i], remainingReserve);
67:       remainingReserve = remainingReserve - _rewards[i];
68:     }
69:     return _rewards;
70:   }

```


</details>


# [GAS-6] Internal functions only used once can be inlined so save gas
## Number of instances found
 11 

## Resolution
 If a internal function is only used once it doesn't make sense to modularise it unless the function which does call the function would be overly long and complex otherwise 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L274-L274
```javascript
274:   function _computeEmissionRate() internal returns (SD59x18)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L331-L331
```javascript
331:   function _updateAuction(uint256 __period) internal  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L371-L371
```javascript
371:   function _getPeriodEnd(uint256 __period) internal view returns (uint256)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L23-L23
```javascript
23:   function purchasePrice( // <= FOUND
24:     SD59x18 _amount,
25:     SD59x18 _emissionRate,
26:     SD59x18 _k,
27:     SD59x18 _decayConstant,
28:     SD59x18 _timeSinceLastAuctionStart
29:   ) internal pure returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L54-L54
```javascript
54:   function purchaseAmount( // <= FOUND
55:     SD59x18 _price,
56:     SD59x18 _emissionRate,
57:     SD59x18 _k,
58:     SD59x18 _decayConstant,
59:     SD59x18 _timeSinceLastAuctionStart
60:   ) internal pure returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L77-L77
```javascript
77:   function computeK( // <= FOUND
78:     SD59x18 _emissionRate,
79:     SD59x18 _decayConstant,
80:     SD59x18 _targetFirstSaleTime,
81:     SD59x18 _purchaseAmount,
82:     SD59x18 _price
83:   ) internal pure returns (SD59x18) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L420-L420
```javascript
420:   function _isRngComplete() internal view returns (bool)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L430-L430
```javascript
430:   function _setNextRngService(RNGInterface _newRng) internal  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L79-L79
```javascript
79:   function reward( // <= FOUND
80:     AuctionResult memory _auctionResult,
81:     uint256 _reserve
82:   ) internal pure returns (uint256) 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L58-L58
```javascript
58:   function _remap(address _caller, address _destination) internal  // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L103-L103
```javascript
103:   function _setOriginChainOwner(address _newOriginChainOwner) internal  // <= FOUND

```


</details>


# [GAS-7] Solidity version 0.8.19 is more gas efficient
## Number of instances found
 2 

## Resolution
 Solidity version 0.8.19 introduced a array of gas optimizations which make contracts which use it more efficient. Provided compatability it may be beneficial to upgrade to this version 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L2-L2
```javascript
2: pragma solidity ^0.8.0;

```


</details>


# [GAS-8] Constructors can be marked as payable to save deployment gas
## Number of instances found
 9 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L93-L93
```javascript
93:   constructor(
94:     ILiquidationSource _source,
95:     address _tokenIn,
96:     address _tokenOut,
97:     uint32 _periodLength,
98:     uint32 _periodOffset,
99:     uint32 _targetFirstSaleTime,
100:     SD59x18 _decayConstant,
101:     uint112 _initialAmountIn,
102:     uint112 _initialAmountOut,
103:     uint256 _minimumAuctionAmount
104:   ) {
105:     source = _source;
106:     tokenIn = _tokenIn;
107:     tokenOut = _tokenOut;
108:     decayConstant = _decayConstant;
109:     periodLength = _periodLength;
110:     periodOffset = _periodOffset;
111:     targetFirstSaleTime = _targetFirstSaleTime;
112: 
113:     SD59x18 period59 = convert(int256(uint256(_periodLength)));
114:     if (_decayConstant.mul(period59).unwrap() > uEXP_MAX_INPUT) {
115:       revert DecayConstantTooLarge(wrap(uEXP_MAX_INPUT).div(period59), _decayConstant);
116:     }
117: 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L46-L46
```javascript
46:   constructor(LiquidationPairFactory liquidationPairFactory_) {
47:     if(address(liquidationPairFactory_) == address(0)) {
48:       revert UndefinedLiquidationPairFactory();
49:     }
50:     _liquidationPairFactory = liquidationPairFactory_;
51: 
52:     emit LiquidationRouterCreated(liquidationPairFactory_);
53:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L140-L140
```javascript
140:   constructor(
141:     RNGInterface rng_,
142:     address owner_,
143:     uint64 sequencePeriod_,
144:     uint64 sequenceOffset_,
145:     uint64 auctionDurationSeconds_,
146:     uint64 auctionTargetTime_
147:   ) Ownable(owner_) {
148:     if (sequencePeriod_ == 0) revert SequencePeriodZero();
149:     if (auctionTargetTime_ > auctionDurationSeconds_) revert AuctionTargetTimeExceedsDuration(uint64(auctionTargetTime_), uint64(auctionDurationSeconds_));
150:     sequencePeriod = sequencePeriod_;
151:     sequenceOffset = sequenceOffset_;
152:     auctionDuration = auctionDurationSeconds_;
153:     auctionTargetTime = auctionTargetTime_;
154:     _auctionTargetTimeFraction = intoUD2x18(convert(uint(auctionTargetTime_)).div(convert(uint(auctionDurationSeconds_))));
155:     _setNextRngService(rng_);
156:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L26-L26
```javascript
26:     constructor(RngAuction _rngAuction) RngAuctionRelayer(_rngAuction) {
27:     }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L40-L40
```javascript
40:     constructor(
41:         RngAuction _rngAuction,
42:         ISingleMessageDispatcher _messageDispatcher,
43:         RemoteOwner _remoteOwner,
44:         uint256 _toChainId
45:     ) RngAuctionRelayer(_rngAuction) {
46:         messageDispatcher = _messageDispatcher;
47:         account = _remoteOwner;
48:         toChainId = _toChainId;
49:     }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L102-L102
```javascript
102:   constructor(
103:     PrizePool prizePool_,
104:     address _rngAuctionRelayer,
105:     uint64 auctionDurationSeconds_,
106:     uint64 auctionTargetTime_
107:   ) {
108:     if (address(prizePool_) == address(0)) revert PrizePoolZeroAddress();
109:     prizePool = prizePool_;
110:     if (address(_rngAuctionRelayer) == address(0)) revert RngRelayerZeroAddress();
111:     if (auctionDurationSeconds_ == 0) revert AuctionDurationZero();
112:     if (auctionTargetTime_ == 0) revert AuctionTargetTimeZero();
113:     if (auctionTargetTime_ > auctionDurationSeconds_) {
114:       revert AuctionTargetTimeExceedsDuration(auctionDurationSeconds_, auctionTargetTime_);
115:     }
116:     rngAuctionRelayer = _rngAuctionRelayer;
117:     _auctionDurationSeconds = auctionDurationSeconds_;
118:     _auctionTargetTimeFraction = UD2x18.wrap(
119:       uint64(convert(auctionTargetTime_).div(convert(_auctionDurationSeconds)).unwrap())
120:     );
121:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L22-L22
```javascript
22:     constructor(
23:         RngAuction _rngAuction
24:     ) {
25:         rngAuction = _rngAuction;
26:     }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L118-L118
```javascript
118:   constructor(
119:     PrizePool _prizePool,
120:     address _vault,
121:     address _owner
122:   ) Ownable(_owner) {
123:     prizePool = _prizePool;
124:     twabController = prizePool.twabController();
125:     vault = _vault;
126:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L51-L51
```javascript
51:   constructor(
52:     uint256 originChainId_,
53:     address executor_,
54:     address __originChainOwner
55:   ) ExecutorAware(executor_) {
56:     if (originChainId_ == 0) revert OriginChainIdZero();
57:     _originChainId = originChainId_;
58:     _setOriginChainOwner(__originChainOwner);
59:   }

```


</details>


# [GAS-9] Usage of smaller uint/int types causes overhead
## Number of instances found
 42 

## Resolution
 When using a smaller int/uint type it first needs to be converted to it's 258 bit counterpart to be operated, this increases the gass cost and thus should be avoided. However it does make sense to use smaller int/uint values within structs provided you pack the struct properly. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L135-L168
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId, // <= FOUND
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) {
138:     if (_sequenceHasCompleted(_sequenceId)) revert SequenceAlreadyCompleted();
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt); // <= FOUND
140:     if (_auctionElapsedSeconds > (_auctionDurationSeconds-1)) revert AuctionExpired();
141:     
142:     UD2x18 rewardFraction = _fractionalReward(_auctionElapsedSeconds);
143:     _auctionResults.rewardFraction = rewardFraction;
144:     _auctionResults.recipient = _rewardRecipient;
145:     _lastSequenceId = _sequenceId;
146: 
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2);
148:     auctionResults[0] = _rngAuctionResult;
149:     auctionResults[1] = AuctionResult({
150:       rewardFraction: rewardFraction,
151:       recipient: _rewardRecipient
152:     });
153: 
154:     uint32 drawId = prizePool.closeDraw(_randomNumber); // <= FOUND
155: 
156:     uint256 futureReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
157:     uint256[] memory _rewards = RewardLib.rewards(auctionResults, futureReserve);
158: 
159:     emit RngSequenceCompleted(
160:       _sequenceId,
161:       drawId,
162:       _rewardRecipient,
163:       _auctionElapsedSeconds,
164:       rewardFraction
165:     );
166: 
167:     for (uint8 i = 0; i < _rewards.length; i++) { // <= FOUND
168:       uint104 _reward = uint104(_rewards[i]); // <= FOUND
169:       if (_reward > 0) {
170:         prizePool.withdrawReserve(auctionResults[i].recipient, _reward);
171:         emit AuctionRewardDistributed(_sequenceId, auctionResults[i].recipient, i, _reward);
172:       }
173:     }
174: 
175:     return bytes32(uint(drawId));
176:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L69-L69
```javascript
69: uint16 _period; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L69-L74
```javascript
65:   function createPair(
66:     ILiquidationSource _source,
67:     address _tokenIn,
68:     address _tokenOut,
69:     uint32 _periodLength, // <= FOUND
70:     uint32 _periodOffset, // <= FOUND
71:     uint32 _targetFirstSaleTime, // <= FOUND
72:     SD59x18 _decayConstant,
73:     uint112 _initialAmountIn, // <= FOUND
74:     uint112 _initialAmountOut, // <= FOUND
75:     uint256 _minimumAuctionAmount
76:   ) external returns (LiquidationPair) {
77:     LiquidationPair _liquidationPair = new LiquidationPair(
78:       _source,
79:       _tokenIn,
80:       _tokenOut,
81:       _periodLength,
82:       _periodOffset,
83:       _targetFirstSaleTime,
84:       _decayConstant,
85:       _initialAmountIn,
86:       _initialAmountOut,
87:       _minimumAuctionAmount
88:     );
89: 
90:     allPairs.push(_liquidationPair);
91:     deployedPairs[_liquidationPair] = true;
92: 
93:     emit PairCreated(
94:       _liquidationPair,
95:       _source,
96:       _tokenIn,
97:       _tokenOut,
98:       _periodLength,

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L175-L189
```javascript
170:   function startRngRequest(address _rewardRecipient) external {
171:     if (!_canStartNextSequence()) revert CannotStartNextSequence();
172: 
173:     RNGInterface rng = _nextRng;
174: 
175:     uint64 _auctionElapsedTimeSeconds = _auctionElapsedTime(); // <= FOUND
176:     if (_auctionElapsedTimeSeconds > auctionDuration) revert AuctionExpired();
177: 
178:     (address _feeToken, uint256 _requestFee) = rng.getRequestFee();
179:     if (_feeToken != address(0) && _requestFee > 0) {
180:       if (IERC20(_feeToken).balanceOf(address(this)) < _requestFee) {
181:         
182:         IERC20(_feeToken).transferFrom(msg.sender, address(this), _requestFee);
183:       }
184:       
185:       IERC20(_feeToken).safeIncreaseAllowance(address(rng), _requestFee);
186:     }
187: 
188:     (uint32 rngRequestId,) = rng.requestRandomNumber(); // <= FOUND
189:     uint32 sequenceId = _openSequenceId(); // <= FOUND
190:     UD2x18 rewardFraction = _currentFractionalReward();
191: 
192:     _lastAuction = RngAuctionResult({
193:       recipient: _rewardRecipient,
194:       rewardFraction: rewardFraction,
195:       sequenceId: sequenceId,
196:       rng: rng,
197:       rngRequestId: rngRequestId
198:     });
199: 
200:     emit RngAuctionCompleted(
201:       _rewardRecipient,
202:       sequenceId,
203:       rng,
204:       rngRequestId,
205:       _auctionElapsedTimeSeconds,
206:       rewardFraction
207:     );
208:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L291-L295
```javascript
288:   function getRngResults()
289:     external
290:     returns (
291:       uint256 randomNumber, uint64 rngCompletedAt // <= FOUND
292:     )
293:   {
294:     RNGInterface rng = _lastAuction.rng;
295:     uint32 requestId = _lastAuction.rngRequestId; // <= FOUND
296:     return (rng.randomNumber(requestId), rng.completedAt(requestId));
297:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L422-L422
```javascript
420:   function _isRngComplete() internal view returns (bool) {
421:     RNGInterface rng = _lastAuction.rng;
422:     uint32 requestId = _lastAuction.rngRequestId; // <= FOUND
423:     return !_canStartNextSequence() && rng.isRequestComplete(requestId);
424:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L197-L197
```javascript
197:   function isSequenceCompleted(uint32 _sequenceId) external view returns (bool) { // <= FOUND
198:     return _sequenceHasCompleted(_sequenceId);
199:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L241-L241
```javascript
241:   function _sequenceHasCompleted(uint32 _sequenceId) internal view returns (bool) { // <= FOUND
242:     return _lastSequenceId >= _sequenceId;
243:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L33-L35
```javascript
31:     function encodeCalldata(address rewardRecipient) internal returns (bytes memory) {
32:         if (!rngAuction.isRngComplete()) revert RngNotCompleted();
33:         (uint256 randomNumber, uint64 rngCompletedAt) = rngAuction.getRngResults(); // <= FOUND
34:         AuctionResult memory results = rngAuction.getLastAuctionResult();
35:         uint32 sequenceId = rngAuction.openSequenceId(); // <= FOUND
36:         results.recipient = remappingOf(results.recipient);
37:         return abi.encodeWithSelector(IRngAuctionRelayListener.rngComplete.selector, randomNumber, rngCompletedAt, rewardRecipient, sequenceId, results);
38:     }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L48-L48
```javascript
48: uint32 public immutable targetFirstSaleTime; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L84-L84
```javascript
84: uint32 internal _lastSequenceId; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L72-L72
```javascript
72: uint48 _lastAuctionTime; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L300-L300
```javascript
300:   function computeRewardFraction(uint64 __auctionElapsedTime) external view returns (UD2x18) { // <= FOUND
301:     return _computeRewardFraction(__auctionElapsedTime);
302:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L370-L370
```javascript
365:   function _openSequenceId() internal view returns (uint32) {
366:     
367: 
368: 
369: 
370:     uint64 currentTime = _currentTime(); // <= FOUND
371:     if (currentTime < sequenceOffset) {
372:       return 0;
373:     }
374:     return uint32((currentTime - sequenceOffset) / sequencePeriod);
375:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L382-L382
```javascript
381:   function _auctionElapsedTime() internal view returns (uint64) {
382:     uint64 currentTime = _currentTime(); // <= FOUND
383:     if (currentTime < sequenceOffset) {
384:       return 0;
385:     }
386:     return (_currentTime() - sequenceOffset) % sequencePeriod;
387:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L398-L398
```javascript
398:   function _computeRewardFraction(uint64 __auctionElapsedTime) internal view returns (UD2x18) { // <= FOUND
399:     return
400:       RewardLib.fractionalReward(
401:         __auctionElapsedTime,
402:         auctionDuration,
403:         _auctionTargetTimeFraction,
404:         _lastAuction.rewardFraction
405:       );
406:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L209-L209
```javascript
209:   function computeRewardFraction(uint64 _auctionElapsedTime) external view returns (UD2x18) { // <= FOUND
210:     return _fractionalReward(_auctionElapsedTime);
211:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L250-L250
```javascript
250:   function _fractionalReward(uint64 _elapsedSeconds) internal view returns (UD2x18) { // <= FOUND
251:     return
252:       RewardLib.fractionalReward(
253:         _elapsedSeconds,
254:         _auctionDurationSeconds,
255:         _auctionTargetTimeFraction,
256:         _auctionResults.rewardFraction
257:       );
258:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L26-L27
```javascript
25:   function fractionalReward(
26:     uint64 _elapsedTime, // <= FOUND
27:     uint64 _auctionDuration, // <= FOUND
28:     UD2x18 _targetTimeFraction,
29:     UD2x18 _targetRewardFraction
30:   ) internal pure returns (UD2x18) {
31:     UD60x18 x = convert(_elapsedTime).div(convert(_auctionDuration));
32:     UD60x18 t = UD60x18.wrap(_targetTimeFraction.unwrap());
33:     UD60x18 r = UD60x18.wrap(_targetRewardFraction.unwrap());
34:     UD60x18 rewardFraction;
35:     if (x.gt(t)) {
36:       UD60x18 tDelta = x.sub(t);
37:       UD60x18 oneMinusT = convert(1).sub(t);
38:       rewardFraction = r.add(
39:         convert(1).sub(r).mul(tDelta).mul(tDelta).div(oneMinusT).div(oneMinusT)
40:       );
41:     } else {
42:       UD60x18 tDelta = t.sub(x);
43:       rewardFraction = r.sub(r.mul(tDelta).mul(tDelta).div(t).div(t));
44:     }
45:     return UD2x18.wrap(uint64(rewardFraction.unwrap()));
46:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L79-L79
```javascript
79: uint64 public immutable auctionDuration; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L82-L82
```javascript
82: uint64 public immutable auctionTargetTime; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L89-L89
```javascript
89: uint64 public immutable sequencePeriod; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L97-L97
```javascript
97: uint64 public immutable sequenceOffset; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L87-L87
```javascript
87: uint64 internal _auctionDurationSeconds; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner { // <= FOUND
143:     if (_initialAvailable > 0) {
144:       uint256 balance = _token.balanceOf(address(this));
145:       if (balance < _initialAvailable) {
146:         revert InitialAvailableExceedsBalance(_initialAvailable, balance);
147:       }
148:     }
149:     _boosts[_token] = Boost({
150:       liquidationPair: _liquidationPair,
151:       multiplierOfTotalSupplyPerSecond: _multiplierOfTotalSupplyPerSecond,
152:       tokensPerSecond: _tokensPerSecond,
153:       available: _initialAvailable,
154:       lastAccruedAt: uint48(block.timestamp)
155:     });
156: 
157:     emit SetBoost(
158:       _token,
159:       _liquidationPair,
160:       _multiplierOfTotalSupplyPerSecond,
161:       _tokensPerSecond,
162:       _initialAvailable,
163:       uint48(block.timestamp)
164:     );
165:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L63-L63
```javascript
63: uint96 _amountInForPeriod; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L66-L66
```javascript
66: uint96 _amountOutForPeriod; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L57-L57
```javascript
57: uint112 _lastNonZeroAmountIn; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L60-L60
```javascript
60: uint112 _lastNonZeroAmountOut; // <= FOUND

```


</details>


# [GAS-10] Avoid updating storage when the value hasn't changed
## Number of instances found
 3 

## Resolution
 In Solidity, manipulating contract storage comes with significant gas costs. One can optimize gas usage by preventing unnecessary storage updates when the new value is the same as the existing one. If an existing value is the same as the new one, not reassigning it to the storage could potentially save substantial amounts of gas, notably 2900 gas for a 'Gsreset'. This saving may come at the expense of a cold storage load operation ('Gcoldsload'), which costs 2100 gas, or a warm storage access operation ('Gwarmaccess'), which costs 100 gas. Therefore, the gas efficiency of your contract can be significantly improved by adding a check that compares the new value with the current one before any storage update operation. If the values are the same, you can bypass the storage operation, thereby saving gas. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L347-L347
```javascript
347:   function setNextRngService(RNGInterface _rngService) external onlyOwner {
348:     _setNextRngService(_rngService);
349:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L142-L142
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner {
143:     if (_initialAvailable > 0) {
144:       uint256 balance = _token.balanceOf(address(this));
145:       if (balance < _initialAvailable) {
146:         revert InitialAvailableExceedsBalance(_initialAvailable, balance);
147:       }
148:     }
149:     _boosts[_token] = Boost({
150:       liquidationPair: _liquidationPair,
151:       multiplierOfTotalSupplyPerSecond: _multiplierOfTotalSupplyPerSecond,
152:       tokensPerSecond: _tokensPerSecond,
153:       available: _initialAvailable,
154:       lastAccruedAt: uint48(block.timestamp)
155:     });
156: 
157:     emit SetBoost(
158:       _token,
159:       _liquidationPair,
160:       _multiplierOfTotalSupplyPerSecond,
161:       _tokensPerSecond,
162:       _initialAvailable,
163:       uint48(block.timestamp)
164:     );
165:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L96-L96
```javascript
96:   function setOriginChainOwner(address _newOriginChainOwner) external {
97:     _checkSender();
98:     _setOriginChainOwner(_newOriginChainOwner);
99:   }

```


</details>


# [GAS-11] Use != 0 instead of > 0
## Number of instances found
 6 

## Resolution
 Replace spotted instances with != 0 for uints as this uses less gas 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L332-L332
```javascript
331:   function _updateAuction(uint256 __period) internal {
332:     if (_amountInForPeriod > 0 && _amountOutForPeriod > 0) { // <= FOUND
333:       
334:       _lastNonZeroAmountIn = _amountInForPeriod;
335:       _lastNonZeroAmountOut = _amountOutForPeriod;
336:     }
337:     _amountInForPeriod = 0;
338:     _amountOutForPeriod = 0;
339:     _lastAuctionTime = uint48(periodOffset + periodLength * __period);
340:     _period = uint16(__period);
341:     SD59x18 emissionRate_ = _computeEmissionRate();
342:     _emissionRate = emissionRate_;
343:     if (_emissionRate.unwrap() != 0) {
344:       
345:       SD59x18 timeSinceLastAuctionStart = convert(int(uint(targetFirstSaleTime)));
346:       SD59x18 purchaseAmount = timeSinceLastAuctionStart.mul(emissionRate_);
347:       SD59x18 exchangeRateAmountInToAmountOut = convert(int(uint(_lastNonZeroAmountIn))).div(convert(int(uint(_lastNonZeroAmountOut))));
348:       SD59x18 price = exchangeRateAmountInToAmountOut.mul(purchaseAmount);
349:       _initialPrice = ContinuousGDA.computeK(
350:         emissionRate_,
351:         decayConstant,
352:         timeSinceLastAuctionStart,
353:         purchaseAmount,
354:         price
355:       );
356:     } else {

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L179-L179
```javascript
170:   function startRngRequest(address _rewardRecipient) external {
171:     if (!_canStartNextSequence()) revert CannotStartNextSequence();
172: 
173:     RNGInterface rng = _nextRng;
174: 
175:     uint64 _auctionElapsedTimeSeconds = _auctionElapsedTime();
176:     if (_auctionElapsedTimeSeconds > auctionDuration) revert AuctionExpired();
177: 
178:     (address _feeToken, uint256 _requestFee) = rng.getRequestFee();
179:     if (_feeToken != address(0) && _requestFee > 0) { // <= FOUND
180:       if (IERC20(_feeToken).balanceOf(address(this)) < _requestFee) {
181:         
182:         IERC20(_feeToken).transferFrom(msg.sender, address(this), _requestFee);
183:       }
184:       
185:       IERC20(_feeToken).safeIncreaseAllowance(address(rng), _requestFee);
186:     }
187: 
188:     (uint32 rngRequestId,) = rng.requestRandomNumber();
189:     uint32 sequenceId = _openSequenceId();
190:     UD2x18 rewardFraction = _currentFractionalReward();
191: 
192:     _lastAuction = RngAuctionResult({
193:       recipient: _rewardRecipient,
194:       rewardFraction: rewardFraction,
195:       sequenceId: sequenceId,
196:       rng: rng,
197:       rngRequestId: rngRequestId
198:     });
199: 
200:     emit RngAuctionCompleted(
201:       _rewardRecipient,
202:       sequenceId,
203:       rng,

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L169-L169
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) {
138:     if (_sequenceHasCompleted(_sequenceId)) revert SequenceAlreadyCompleted();
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt);
140:     if (_auctionElapsedSeconds > (_auctionDurationSeconds-1)) revert AuctionExpired();
141:     
142:     UD2x18 rewardFraction = _fractionalReward(_auctionElapsedSeconds);
143:     _auctionResults.rewardFraction = rewardFraction;
144:     _auctionResults.recipient = _rewardRecipient;
145:     _lastSequenceId = _sequenceId;
146: 
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2);
148:     auctionResults[0] = _rngAuctionResult;
149:     auctionResults[1] = AuctionResult({
150:       rewardFraction: rewardFraction,
151:       recipient: _rewardRecipient
152:     });
153: 
154:     uint32 drawId = prizePool.closeDraw(_randomNumber);
155: 
156:     uint256 futureReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
157:     uint256[] memory _rewards = RewardLib.rewards(auctionResults, futureReserve);
158: 
159:     emit RngSequenceCompleted(
160:       _sequenceId,
161:       drawId,
162:       _rewardRecipient,
163:       _auctionElapsedSeconds,
164:       rewardFraction
165:     );
166: 
167:     for (uint8 i = 0; i < _rewards.length; i++) {
168:       uint104 _reward = uint104(_rewards[i]);
169:       if (_reward > 0) { // <= FOUND
170:         prizePool.withdrawReserve(auctionResults[i].recipient, _reward);
171:         emit AuctionRewardDistributed(_sequenceId, auctionResults[i].recipient, i, _reward);
172:       }
173:     }
174: 
175:     return bytes32(uint(drawId));
176:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L143-L143
```javascript
142:   function setBoost(IERC20 _token, address _liquidationPair, UD2x18 _multiplierOfTotalSupplyPerSecond, uint96 _tokensPerSecond, uint144 _initialAvailable) external onlyOwner {
143:     if (_initialAvailable > 0) { // <= FOUND
144:       uint256 balance = _token.balanceOf(address(this));
145:       if (balance < _initialAvailable) {
146:         revert InitialAvailableExceedsBalance(_initialAvailable, balance);
147:       }
148:     }
149:     _boosts[_token] = Boost({
150:       liquidationPair: _liquidationPair,
151:       multiplierOfTotalSupplyPerSecond: _multiplierOfTotalSupplyPerSecond,
152:       tokensPerSecond: _tokensPerSecond,
153:       available: _initialAvailable,
154:       lastAccruedAt: uint48(block.timestamp)
155:     });
156: 
157:     emit SetBoost(
158:       _token,
159:       _liquidationPair,
160:       _multiplierOfTotalSupplyPerSecond,
161:       _tokensPerSecond,
162:       _initialAvailable,
163:       uint48(block.timestamp)
164:     );
165:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L269-L272
```javascript
262:   function _computeAvailable(IERC20 _tokenOut) internal view returns (uint256) {
263:     Boost memory boost = _boosts[_tokenOut];
264:     uint256 deltaTime = block.timestamp - boost.lastAccruedAt;
265:     uint256 deltaAmount;
266:     if (deltaTime == 0) {
267:       return boost.available;
268:     }
269:     if (boost.tokensPerSecond > 0) { // <= FOUND
270:       deltaAmount = boost.tokensPerSecond * deltaTime;
271:     }
272:     if (boost.multiplierOfTotalSupplyPerSecond.unwrap() > 0) { // <= FOUND
273:       uint256 totalSupply = twabController.getTotalSupplyTwabBetween(address(vault), uint32(boost.lastAccruedAt), uint32(block.timestamp));
274:       deltaAmount += convert(boost.multiplierOfTotalSupplyPerSecond.intoUD60x18().mul(convert(deltaTime)).mul(convert(totalSupply)));
275:     }
276:     uint256 availableBalance = _tokenOut.balanceOf(address(this));
277:     deltaAmount = availableBalance > deltaAmount ? deltaAmount : availableBalance;
278:     return boost.available + deltaAmount;
279:   }

```


</details>


# [GAS-12] Integer increments by one can be unchecked to save on gas fees
## Number of instances found
 2 

## Resolution
 Using unchecked increments in Solidity can save on gas fees by bypassing built-in overflow checks, thus optimizing gas usage, but requires careful assessment of potential risks and edge cases to avoid unintended consequences. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L167-L167
```javascript
131:   function rngComplete(
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) {
138:     if (_sequenceHasCompleted(_sequenceId)) revert SequenceAlreadyCompleted();
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt);
140:     if (_auctionElapsedSeconds > (_auctionDurationSeconds-1)) revert AuctionExpired();
141:     
142:     UD2x18 rewardFraction = _fractionalReward(_auctionElapsedSeconds);
143:     _auctionResults.rewardFraction = rewardFraction;
144:     _auctionResults.recipient = _rewardRecipient;
145:     _lastSequenceId = _sequenceId;
146: 
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2);
148:     auctionResults[0] = _rngAuctionResult;
149:     auctionResults[1] = AuctionResult({
150:       rewardFraction: rewardFraction,
151:       recipient: _rewardRecipient
152:     });
153: 
154:     uint32 drawId = prizePool.closeDraw(_randomNumber);
155: 
156:     uint256 futureReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
157:     uint256[] memory _rewards = RewardLib.rewards(auctionResults, futureReserve);
158: 
159:     emit RngSequenceCompleted(
160:       _sequenceId,
161:       drawId,
162:       _rewardRecipient,
163:       _auctionElapsedSeconds,
164:       rewardFraction
165:     );
166: 
167:     for (uint8 i = 0; i < _rewards.length; i++) { // <= FOUND
168:       uint104 _reward = uint104(_rewards[i]);
169:       if (_reward > 0) {
170:         prizePool.withdrawReserve(auctionResults[i].recipient, _reward);
171:         emit AuctionRewardDistributed(_sequenceId, auctionResults[i].recipient, i, _reward);
172:       }
173:     }
174: 
175:     return bytes32(uint(drawId));
176:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L65-L65
```javascript
58:   function rewards(
59:     AuctionResult[] memory _auctionResults,
60:     uint256 _reserve
61:   ) internal pure returns (uint256[] memory) {
62:     uint256 remainingReserve = _reserve;
63:     uint256 _auctionResultsLength = _auctionResults.length;
64:     uint256[] memory _rewards = new uint256[](_auctionResultsLength);
65:     for (uint256 i; i < _auctionResultsLength; i++) { // <= FOUND
66:       _rewards[i] = reward(_auctionResults[i], remainingReserve);
67:       remainingReserve = remainingReserve - _rewards[i];
68:     }
69:     return _rewards;
70:   }

```


</details>


# [GAS-13] Default int values are manually reset
## Number of instances found
 5 

## Resolution
 Using .delete is better than resetting a Solidity variable to its default value manually because it frees up storage space on the Ethereum blockchain, resulting in gas cost savings. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L274-L279
```javascript
274:   function _computeEmissionRate() internal returns (SD59x18) { // <= FOUND
275:     uint256 amount = source.liquidatableBalanceOf(tokenOut);
276:     
277:     if (amount < minimumAuctionAmount) {
278:       
279:       amount = 0; // <= FOUND
280:       
281:     }
282:     return convert(int256(amount)).div(convert(int32(int(periodLength))));
283:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L331-L338
```javascript
331:   function _updateAuction(uint256 __period) internal { // <= FOUND
332:     if (_amountInForPeriod > 0 && _amountOutForPeriod > 0) {
333:       
334:       _lastNonZeroAmountIn = _amountInForPeriod;
335:       _lastNonZeroAmountOut = _amountOutForPeriod;
336:     }
337:     _amountInForPeriod = 0; // <= FOUND
338:     _amountOutForPeriod = 0; // <= FOUND
339:     _lastAuctionTime = uint48(periodOffset + periodLength * __period);
340:     _period = uint16(__period);
341:     SD59x18 emissionRate_ = _computeEmissionRate();
342:     _emissionRate = emissionRate_;
343:     if (_emissionRate.unwrap() != 0) {
344:       
345:       SD59x18 timeSinceLastAuctionStart = convert(int(uint(targetFirstSaleTime)));
346:       SD59x18 purchaseAmount = timeSinceLastAuctionStart.mul(emissionRate_);
347:       SD59x18 exchangeRateAmountInToAmountOut = convert(int(uint(_lastNonZeroAmountIn))).div(convert(int(uint(_lastNonZeroAmountOut))));
348:       SD59x18 price = exchangeRateAmountInToAmountOut.mul(purchaseAmount);
349:       _initialPrice = ContinuousGDA.computeK(
350:         emissionRate_,
351:         decayConstant,
352:         timeSinceLastAuctionStart,
353:         purchaseAmount,
354:         price
355:       );
356:     } else {
357:       _initialPrice = wrap(0);
358:     }
359:   }

```


</details>


# [GAS-14] <= or >= is more efficient than < or > 
## Number of instances found
 1 

## Resolution
 Make such found comparisons to the <=/>= equivalent when comparing against integer literals 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L38-L38
```javascript
23:   function purchasePrice(
24:     SD59x18 _amount,
25:     SD59x18 _emissionRate,
26:     SD59x18 _k,
27:     SD59x18 _decayConstant,
28:     SD59x18 _timeSinceLastAuctionStart
29:   ) internal pure returns (SD59x18) {
30:     if (_amount.unwrap() == 0) {
31:       return SD59x18.wrap(0);
32:     }
33:     SD59x18 topE = _decayConstant.mul(_amount).div(_emissionRate);
34:     topE = topE.exp().sub(ONE);
35:     SD59x18 bottomE = _decayConstant.mul(_timeSinceLastAuctionStart);
36:     bottomE = bottomE.exp();
37:     SD59x18 result;
38:     if (_emissionRate.unwrap() > 1e18) { // <= FOUND
39:       result = _k.div(_emissionRate).mul(topE).div(bottomE);
40:     } else {
41:       result = _k.mul(topE.div(_emissionRate.mul(bottomE)));
42:     }
43:     return result;
44:   }

```


</details>


# [GAS-15] State variables used within a function more than once should be cached to save gas
## Number of instances found
 15 

## Resolution
 Cache such variables and perform operations on them, if operations include modifications to the state variable(s) then remember to equate the state variable to it's cached counterpart at the end 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L331-L347
```javascript
331:   function _updateAuction(uint256 __period) internal { // <= FOUND
332:     if (_amountInForPeriod > 0 && _amountOutForPeriod > 0) { // <= FOUND
333:       
334:       _lastNonZeroAmountIn = _amountInForPeriod; // <= FOUND
335:       _lastNonZeroAmountOut = _amountOutForPeriod; // <= FOUND
336:     }
337:     _amountInForPeriod = 0; // <= FOUND
338:     _amountOutForPeriod = 0; // <= FOUND
339:     _lastAuctionTime = uint48(periodOffset + periodLength * __period); // <= FOUND
340:     _period = uint16(__period); // <= FOUND
341:     SD59x18 emissionRate_ = _computeEmissionRate();
342:     _emissionRate = emissionRate_;
343:     if (_emissionRate.unwrap() != 0) {
344:       
345:       SD59x18 timeSinceLastAuctionStart = convert(int(uint(targetFirstSaleTime)));
346:       SD59x18 purchaseAmount = timeSinceLastAuctionStart.mul(emissionRate_);
347:       SD59x18 exchangeRateAmountInToAmountOut = convert(int(uint(_lastNonZeroAmountIn))).div(convert(int(uint(_lastNonZeroAmountOut)))); // <= FOUND
348:       SD59x18 price = exchangeRateAmountInToAmountOut.mul(purchaseAmount);
349:       _initialPrice = ContinuousGDA.computeK(
350:         emissionRate_,
351:         decayConstant,
352:         timeSinceLastAuctionStart,
353:         purchaseAmount,
354:         price
355:       );
356:     } else {
357:       _initialPrice = wrap(0);
358:     }
359:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L287-L291
```javascript
287:   function _getElapsedTime() internal view returns (SD59x18) { // <= FOUND
288:     if (block.timestamp < _lastAuctionTime) { // <= FOUND
289:       return wrap(0);
290:     }
291:     return convert(int256(block.timestamp)).sub(convert(int256(uint256(_lastAuctionTime)))); // <= FOUND
292:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L131-L144
```javascript
131:   function rngComplete( // <= FOUND
132:     uint256 _randomNumber,
133:     uint256 _rngCompletedAt,
134:     address _rewardRecipient,
135:     uint32 _sequenceId,
136:     AuctionResult calldata _rngAuctionResult
137:   ) external returns (bytes32) {
138:     if (_sequenceHasCompleted(_sequenceId)) revert SequenceAlreadyCompleted();
139:     uint64 _auctionElapsedSeconds = uint64(block.timestamp < _rngCompletedAt ? 0 : block.timestamp - _rngCompletedAt);
140:     if (_auctionElapsedSeconds > (_auctionDurationSeconds-1)) revert AuctionExpired();
141:     
142:     UD2x18 rewardFraction = _fractionalReward(_auctionElapsedSeconds);
143:     _auctionResults.rewardFraction = rewardFraction; // <= FOUND
144:     _auctionResults.recipient = _rewardRecipient; // <= FOUND
145:     _lastSequenceId = _sequenceId;
146: 
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2);
148:     auctionResults[0] = _rngAuctionResult;
149:     auctionResults[1] = AuctionResult({
150:       rewardFraction: rewardFraction,
151:       recipient: _rewardRecipient
152:     });
153: 
154:     uint32 drawId = prizePool.closeDraw(_randomNumber);
155: 
156:     uint256 futureReserve = prizePool.reserve() + prizePool.reserveForOpenDraw();
157:     uint256[] memory _rewards = RewardLib.rewards(auctionResults, futureReserve);
158: 
159:     emit RngSequenceCompleted(
160:       _sequenceId,
161:       drawId,
162:       _rewardRecipient,
163:       _auctionElapsedSeconds,
164:       rewardFraction
165:     );
166: 
167:     for (uint8 i = 0; i < _rewards.length; i++) {
168:       uint104 _reward = uint104(_rewards[i]);

```


</details>


# [GAS-16] Mappings used within a function more than once should be cached to save gas
## Number of instances found
 6 

## Resolution
 Cache such mappings and perform operations on them, if operations include modifications to the mapping(s) then remember to equate the mapping to it's cached counterpart at the end 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L32-L36
```javascript
32:   function remappingOf(address _addr) public view returns (address) { // <= FOUND
33:     if (_destinationAddress[_addr] == address(0)) { // <= FOUND
34:       return _addr;
35:     } else {
36:       return _destinationAddress[_addr]; // <= FOUND
37:     }
38:   }

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L211-L224
```javascript
211:   function liquidate( // <= FOUND
212:     address _account,
213:     address _tokenIn,
214:     uint256 _amountIn,
215:     address _tokenOut,
216:     uint256 _amountOut
217:   ) external override onlyPrizeToken(_tokenIn) onlyLiquidationPair(_tokenOut) returns (bool) {
218:     uint256 amountAvailable = _computeAvailable(IERC20(_tokenOut));
219:     if (_amountOut > amountAvailable) {
220:       revert InsufficientAvailableBalance(_amountOut, amountAvailable);
221:     }
222:     amountAvailable = (amountAvailable - _amountOut);
223:     _boosts[IERC20(_tokenOut)].available = amountAvailable.toUint144(); // <= FOUND
224:     _boosts[IERC20(_tokenOut)].lastAccruedAt = uint48(block.timestamp); // <= FOUND
225:     prizePool.contributePrizeTokens(vault, _amountIn);
226:     IERC20(_tokenOut).safeTransfer(_account, _amountOut);
227: 
228:     emit Liquidated(
229:       IERC20(_tokenOut),
230:       _account,
231:       _amountIn,
232:       _amountOut,
233:       amountAvailable
234:     );
235: 
236:     return true;
237:   }

```


</details>


# [GAS-17] Use assembly to check for the zero address
## Number of instances found
 5 

## Resolution
 
Using assembly for address comparisons in Solidity can save gas because it allows for more direct access to the Ethereum Virtual Machine (EVM), reducing the overhead of higher-level operations. Solidity's high-level abstraction simplifies coding but can introduce additional gas costs. Using assembly for simple operations like address comparisons can be more gas-efficient. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L170-L179
```javascript
170:   function startRngRequest(address _rewardRecipient) external {
171:     if (!_canStartNextSequence()) revert CannotStartNextSequence();
172: 
173:     RNGInterface rng = _nextRng;
174: 
175:     uint64 _auctionElapsedTimeSeconds = _auctionElapsedTime();
176:     if (_auctionElapsedTimeSeconds > auctionDuration) revert AuctionExpired();
177: 
178:     (address _feeToken, uint256 _requestFee) = rng.getRequestFee();
179:     if (_feeToken != address(0) && _requestFee > 0) { // <= FOUND
180:       if (IERC20(_feeToken).balanceOf(address(this)) < _requestFee) {
181:         
182:         IERC20(_feeToken).transferFrom(msg.sender, address(this), _requestFee);
183:       }
184:       
185:       IERC20(_feeToken).safeIncreaseAllowance(address(rng), _requestFee);
186:     }
187: 
188:     (uint32 rngRequestId,) = rng.requestRandomNumber();
189:     uint32 sequenceId = _openSequenceId();
190:     UD2x18 rewardFraction = _currentFractionalReward();
191: 
192:     _lastAuction = RngAuctionResult({
193:       recipient: _rewardRecipient,
194:       rewardFraction: rewardFraction,

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L430-L431
```javascript
430:   function _setNextRngService(RNGInterface _newRng) internal {
431:     if (address(_newRng) == address(0)) revert RngZeroAddress(); // <= FOUND
432: 
433:     
434:     
435:     _nextRng = _newRng;
436: 
437:     emit SetNextRngService(_newRng);
438:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L79-L83
```javascript
79:   function reward(
80:     AuctionResult memory _auctionResult,
81:     uint256 _reserve
82:   ) internal pure returns (uint256) {
83:     if (_auctionResult.recipient == address(0)) return 0; // <= FOUND
84:     if (_reserve == 0) return 0;
85:     return
86:       convert(
87:         UD60x18.wrap(UD2x18.unwrap(_auctionResult.rewardFraction)).mul(convert(_reserve))
88:       );
89:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L32-L33
```javascript
32:   function remappingOf(address _addr) public view returns (address) {
33:     if (_destinationAddress[_addr] == address(0)) { // <= FOUND
34:       return _addr;
35:     } else {
36:       return _destinationAddress[_addr];
37:     }
38:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L103-L104
```javascript
103:   function _setOriginChainOwner(address _newOriginChainOwner) internal {
104:     if (_newOriginChainOwner == address(0)) revert OriginChainOwnerZeroAddress(); // <= FOUND
105: 
106:     _originChainOwner = _newOriginChainOwner;
107: 
108:     emit OriginChainOwnerSet(_newOriginChainOwner);
109:   }

```


</details>


# [GAS-18] Use storage instead of memory for structs/arrays
## Number of instances found
 3 

## Resolution
 In Solidity, using storage instead of memory for structs and arrays in function parameters can result in gas savings. When data is passed as a storage reference, the function operates directly on the original data stored in contract storage, without needing to create a copy. Conversely, when memory is used, a copy of the data is created, which incurs additional gas costs. However, it's essential to note that while using storage references can save gas, it also means that any changes made to the data inside the function will modify the original data stored in the contract, which may not always be the desired behavior. Therefore, developers should carefully consider the implications of using storage versus memory based on the specific requirements of their functions. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L59-L61
```javascript
58:   function rewards(
59:     AuctionResult[] memory _auctionResults, // <= FOUND
60:     uint256 _reserve
61:   ) internal pure returns (uint256[] memory)  // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L80-L80
```javascript
79:   function reward(
80:     AuctionResult memory _auctionResult, // <= FOUND
81:     uint256 _reserve
82:   ) internal pure returns (uint256) 

```


</details>


# [GAS-19] Can transfer 0
## Number of instances found
 1 

## Resolution
 In Solidity, performing unnecessary operations can consume more gas than needed, leading to cost inefficiencies. For instance, if a `transfer` function doesn't have a zero amount check and someone calls it with a zero amount, unnecessary gas will be consumed in executing the function, even though the state of the contract remains the same. By implementing a zero amount check, such unnecessary function calls can be avoided, thereby saving gas and making the contract more efficient.
 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L188-L193
```javascript
188:   function withdraw(IERC20 _token, uint256 _amount) external onlyOwner {
189:     uint256 availableBoost = _accrue(_token);
190:     uint256 availableBalance = _token.balanceOf(address(this));
191:     uint256 remainingBalance = availableBalance - _amount;
192:     _boosts[IERC20(_token)].available = (availableBoost > remainingBalance ? remainingBalance : availableBoost).toUint144();
193:     _token.transfer(msg.sender, _amount); // <= FOUND
194: 
195:     emit Withdrawn(_token, msg.sender, _amount);
196:   }

```


</details>


# [GAS-20] Redundant state variable getters
## Number of instances found
 2 

## Resolution
 Getters for public state variables are automatically generated so there is no need to code them manually and lose gas 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L335-L335
```javascript
334:   function getSequencePeriod() external view returns (uint64) {
335:     return sequencePeriod; // <= FOUND
336:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L327-L327
```javascript
326:   function getSequenceOffset() external view returns (uint64) {
327:     return sequenceOffset; // <= FOUND
328:   }

```


</details>


# [GAS-21] State variables which are not modified within functions should be set as constants or immutable for values set at deployment
## Number of instances found
 1 

## Resolution
 Set state variables listed below as constant or immutable for values set at deployment. Ensure it is safe to do so 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L87-L87
```javascript
87: uint64 internal _auctionDurationSeconds;

```


</details>


# [GAS-22] Redundant else statement
## Number of instances found
 1 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>

```javascript
23:   function purchasePrice(
24:     SD59x18 _amount,
25:     SD59x18 _emissionRate,
26:     SD59x18 _k,
27:     SD59x18 _decayConstant,
28:     SD59x18 _timeSinceLastAuctionStart
29:   ) internal pure returns (SD59x18) {
30:     if (_amount.unwrap() == 0) {
31:       return SD59x18.wrap(0);
32:     }
33:     SD59x18 topE = _decayConstant.mul(_amount).div(_emissionRate);
34:     topE = topE.exp().sub(ONE);
35:     SD59x18 bottomE = _decayConstant.mul(_timeSinceLastAuctionStart);
36:     bottomE = bottomE.exp();
37:     SD59x18 result;
38:     if (_emissionRate.unwrap() > 1e18) {
39:       result = _k.div(_emissionRate).mul(topE).div(bottomE);
40:     } else {
41:       result = _k.mul(topE.div(_emissionRate.mul(bottomE)));
42:     }
43:     return result;
44:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L32-L32
```javascript
32:   function remappingOf(address _addr) public view returns (address) { // <= FOUND
33:     if (_destinationAddress[_addr] == address(0)) {
34:       return _addr;
35:     } else {
36:       return _destinationAddress[_addr];
37:     }
38:   }

```


</details>


# [GAS-23] Don't use _msgSender() if not supporting EIP-2771
## Number of instances found
 1 

## Resolution
 From a gas efficiency perspective, using `_msgSender()` in a contract not intended to support EIP-2771 could add unnecessary overhead. The `_msgSender()` function includes checks to determine if the transaction was forwarded, which involves extra function calls that consume more gas than a simple `msg.sender`.

If a contract doesn't require EIP-2771 meta-transaction support, using `msg.sender` directly is more gas efficient. `msg.sender` is a globally accessible variable in Solidity that doesn't require an extra function call, making it a less costly choice.

In the context of Ethereum, where every operation has a gas cost, it's crucial to eliminate unnecessary computations to optimize contract execution and minimize transaction fees. Therefore, if EIP-2771 support isn't necessary, it's recommended to use `msg.sender` instead of `_msgSender()`. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L120-L120
```javascript
120:     if (_msgSender() != address(_originChainOwner)) revert OriginSenderNotOwner(_msgSender()); // <= FOUND

```


</details>


# [GAS-24] Unbounded Gas Consumption Risk Due to External Call Recipients
## Number of instances found
 1 

## Resolution
 In the context of Solidity, external function calls without a specified gas limit present a significant risk. The callee contract has the potential to consume all the gas allocated to the transaction, causing an undesired revert and disrupt the function's execution. To mitigate this, it's recommended to explicitly set a gas limit when performing external calls using addr.call{gas: <amount>}. This limits the gas forwarded to the callee, preventing potential pitfalls and offering better control over transaction execution. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L39-L39
```javascript
34:     function relay(
35:         IRngAuctionRelayListener _rngAuctionRelayListener,
36:         address _relayRewardRecipient
37:     ) external returns (bytes memory) {
38:         bytes memory data = encodeCalldata(_relayRewardRecipient);
39:         (bool success, bytes memory returnData) = address(_rngAuctionRelayListener).call(data); // <= FOUND
40:         if (!success) {
41:             revert DirectRelayFailed(returnData);
42:         }
43:         emit DirectRelaySuccess(_relayRewardRecipient, returnData);
44:         return returnData;
45:     }

```


</details>


# [GAS-25] Consider activating via-ir for deploying
## Number of instances found
 17 

## Resolution
 The Solidity compiler's Intermediate Representation (IR) based code generator, which can be activated using --via-ir on the command line or {"viaIR": true} in the options, serves a dual purpose. Firstly, it boosts the transparency and audibility of code generation, which enhances developers' comprehension and control over the contract's final bytecode. Secondly, it enables more sophisticated optimization passes that span multiple functions, thereby potentially leading to more efficient bytecode.

It's important to note that using the IR-based code generator may lengthen compile times due to the extra optimization steps. Therefore, it's advised to test your contract with and without this option enabled to measure the performance and gas cost implications. If the IR-based code generator significantly enhances your contract's performance or reduces gas costs, consider using the --via-ir flag during deployment. This way, you can leverage more advanced compiler optimizations without hindering your development workflow. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { ExecutorAware } from "erc5164/abstract/ExecutorAware.sol";
5: 
6: /* ============ Custom Errors ============ */
7: 
8: /// @notice Thrown when the originChainId passed to the constructor is zero.
9: error OriginChainIdZero();
10: 
11: /// @notice Thrown when the OriginChainOwner address passed to the constructor is zero address.
12: error OriginChainOwnerZeroAddress();
13: 
14: /// @notice Thrown when the message was dispatched from an unsupported chain ID.
15: error OriginChainIdUnsupported(uint256 fromChainId);
16: 
17: /// @notice Thrown when the message was not executed by the executor.
18: error LocalSenderNotExecutor(address sender);
19: 
20: /// @notice Thrown when the message was not dispatched by the OriginChainOwner on the origin chain.
21: error OriginSenderNotOwner(address sender);
22: 
23: /// @notice Thrown when the call to the target contract failed.
24: error CallFailed(bytes returnData);
25: 

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/libraries/RemoteOwnerCallEncoder.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { RemoteOwner } from ".RemoteOwner.sol";
5: 
6: library RemoteOwnerCallEncoder {
7:     function encodeCalldata(address target, uint256 value, bytes memory data) internal pure returns (bytes memory) {
8:         return abi.encodeWithSelector(
9:             RemoteOwner.execute.selector,
10:             target,
11:             value,
12:             data
13:         );
14:         // assembly {
15:         //    return (add(returnData, 0x20), mload(returnData))
16:         // }
17:     }
18: }
19: 

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { UD2x18 } from "prb-math/UD2x18.sol";
5: import { convert } from "prb-math/UD60x18.sol";
6: import { PrizePool } from "pt-v5-prize-pool/PrizePool.sol";
7: 
8: import { RewardLib } from "libraries/RewardLib.sol";
9: import { IRngAuctionRelayListener } from "interfaces/IRngAuctionRelayListener.sol";
10: import { IAuction, AuctionResult } from "interfaces/IAuction.sol";
11: import { RngAuction } from "RngAuction.sol";
12: 
13: /* ============ Custom Errors ============ */
14: 
15: /// @notice Thrown if the auction period is zero.
16: error AuctionDurationZero();
17: 
18: /// @notice Thrown if the auction target time is zero.
19: error AuctionTargetTimeZero();
20: 
21: /**
22:   * @notice Thrown if the auction target time exceeds the auction duration.
23:   * @param auctionTargetTime The auction target time to complete in seconds
24:   * @param auctionDuration The auction duration in seconds
25:   */

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/interfaces/IAuction.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { UD2x18 } from "prb-math/UD2x18.sol";
5: 
6: /* ============ Structs ============ */
7: 
8: /**
9:  * @notice Stores the results of an auction.
10:  * @param recipient The recipient of the auction awards
11:  * @param rewardFraction The fraction of the available rewards to be sent to the recipient
12:  */
13: struct AuctionResult {
14:   address recipient;
15:   UD2x18 rewardFraction;
16: }
17: 
18: /* ============ Interface ============ */
19: 
20: /// @title IAuction
21: /// @author G9 Software Inc.
22: /// @notice Defines some common interfaces for auctions
23: interface IAuction {
24:   /**
25:    * @notice Returns the auction duration in seconds.

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { UD2x18 } from "prb-math/UD2x18.sol";
5: import { UD60x18, convert } from "prb-math/UD60x18.sol";
6: 
7: import { AuctionResult } from ".interfaces/IAuction.sol";
8: 
9: /// @title RewardLib
10: /// @author G9 Software Inc.
11: /// @notice Library for calculating auction rewards.
12: /// @dev This library uses a parabolic fractional dutch auction (PFDA) to calculate rewards. For more details see https://dev.pooltogether.com/protocol/next/design/draw-auction#parabolic-fractional-dutch-auction-pfda
13: library RewardLib {
14:   /* ============ Internal Functions ============ */
15: 
16:   /**
17:    * @notice Calculates the fractional reward using a Parabolic Fractional Dutch Auction (PFDA)
18:    * given the elapsed time, auction time, and target sale parameters.
19:    * @param _elapsedTime The elapsed time since the start of the auction in seconds
20:    * @param _auctionDuration The auction duration in seconds
21:    * @param _targetTimeFraction The target sale time as a fraction of the total auction duration (0.0,1.0]
22:    * @param _targetRewardFraction The target fractional sale price
23:    * @return The reward fraction as a UD2x18 fraction
24:    */
25:   function fractionalReward(

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import {
5:     RngAuctionRelayer,
6:     RngAuction,
7:     IRngAuctionRelayListener
8: } from "abstract/RngAuctionRelayer.sol";
9: 
10: /// @notice Emitted when the relay call fails
11: /// @param returnData The revert message from the relay call
12: error DirectRelayFailed(bytes returnData);
13: 
14: /// @title RngAuctionRelayerDirect
15: /// @author G9 Software Inc.
16: /// @notice This contract will allow anyone to trigger the relay of RNG results to an IRngAuctionRelayListener.
17: contract RngAuctionRelayerDirect is RngAuctionRelayer {
18: 
19:     /// @notice Emitted when the relay was successful.
20:     /// @param rewardRecipient The address of the reward recipient.
21:     /// @param returnData The return data from the relay listener.
22:     event DirectRelaySuccess(address indexed rewardRecipient, bytes returnData);
23: 
24:     /// @notice Constructs a new contract
25:     /// @param _rngAuction The RNG auction to pull results from.

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: /**
5:  * @title AddressRemapper
6:  * @author Generation Software Team
7:  * @notice Allows addresses to provide a remapping to a new address.
8:  * @dev The RngAuction lives on L1, but the rewards are given out on L2s. This contract allows the L1 reward recipients to remap their addresses to their L2 addresses if needed.
9:  */
10: contract AddressRemapper {
11:   /* ============ Variables ============ */
12: 
13:   /// @notice User-defined address remapping
14:   mapping(address => address) internal _destinationAddress;
15: 
16:   /* ============ Events ============ */
17: 
18:   /**
19:    @notice Emitted when a remapping is set.
20:    @param caller Caller address
21:    @param destination Remapped destination address that will be used in place of the caller address
22:    */
23:   event AddressRemapped(address indexed caller, address indexed destination);
24: 
25:   /* ============ Public Functions ============ */

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: 
3: pragma solidity 0.8.19;
4: 
5: import "LiquidationPair.sol";
6: 
7: /// @title LiquidationPairFactory
8: /// @author G9 Software Inc.
9: /// @notice Factory contract for deploying LiquidationPair contracts.
10: contract LiquidationPairFactory {
11: 
12:   /* ============ Events ============ */
13: 
14:   /// @notice Emitted when a new LiquidationPair is created
15:   /// @param pair The address of the new pair
16:   /// @param source The liquidation source that the pair is using
17:   /// @param tokenIn The input token for the pair
18:   /// @param tokenOut The output token for the pair
19:   /// @param periodLength The duration of auctions
20:   /// @param periodOffset The start time offset of auctions
21:   /// @param targetFirstSaleTime The target time for the first auction
22:   /// @param decayConstant The decay constant that the pair is using
23:   /// @param initialAmountIn The initial amount of input tokens (used to compute initial exchange rate)
24:   /// @param initialAmountOut The initial amount of output tokens (used to compute initial exchange rate)
25:   /// @param minimumAuctionAmount The minimum auction size in output tokens

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/RngAuctionRelayer.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { RngAuction } from ".RngAuction.sol";
5: import { AuctionResult } from ".interfaces/IAuction.sol";
6: import { AddressRemapper } from ".abstract/AddressRemapper.sol";
7: import { IRngAuctionRelayListener } from ".interfaces/IRngAuctionRelayListener.sol";
8: 
9: /// @notice Emitted when the RNG has not yet completed
10: error RngNotCompleted();
11: 
12: /// @title RngAuctionRelayer
13: /// @author G9 Software Inc.
14: /// @notice Base contarct that relays RNG auction results to a listener
15: abstract contract RngAuctionRelayer is AddressRemapper {
16: 
17:     /// @notice The RNG Auction to get the random number from
18:     RngAuction public immutable rngAuction;
19: 
20:     /// @notice Constructs a new contract
21:     /// @param _rngAuction The RNG auction to retrieve the random number from
22:     constructor(
23:         RngAuction _rngAuction
24:     ) {
25:         rngAuction = _rngAuction;

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity ^0.8.0;
3: 
4: import { VaultBooster, PrizePool } from "VaultBooster.sol";
5: 
6: /// @title VaultBoosterFactory
7: /// @author G9 Software Inc.
8: /// @notice Factory contract for VaultBooster
9: contract VaultBoosterFactory  {
10: 
11:     /// @notice Emitted when a new VaultBooster is created
12:     /// @param vaultBooster The address of the new Vault Booster
13:     /// @param prizePool The address of the prize pool to contribute to
14:     /// @param vault The address of the vault to contribute for
15:     /// @param owner The owner of the VaultBooster
16:     event CreatedVaultBooster(
17:         VaultBooster indexed vaultBooster,
18:         PrizePool indexed prizePool,
19:         address indexed vault,
20:         address owner
21:     );
22: 
23:     /// @notice Creates a new vault booster contract
24:     /// @param _prizePool The prize pool to contribute to
25:     /// @param _vault The vault to contribute for

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity 0.8.19;
3: 
4: import "openzeppelin/token/ERC20/IERC20.sol";
5: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol";
6: 
7: import { LiquidationPair } from "LiquidationPair.sol";
8: import { LiquidationPairFactory } from "LiquidationPairFactory.sol";
9: 
10: error UndefinedLiquidationPairFactory();
11: error UnknownLiquidationPair(LiquidationPair liquidationPair);
12: 
13: /// @title LiquidationRouter
14: /// @author G9 Software Inc.
15: /// @notice Serves as the user-facing swapping interface for Liquidation Pairs.
16: contract LiquidationRouter {
17:   using SafeERC20 for IERC20;
18: 
19:   /* ============ Events ============ */
20: 
21:   /// @notice Emitted when the router is created
22:   event LiquidationRouterCreated(LiquidationPairFactory indexed liquidationPairFactory);
23: 
24:   /// @notice Emitted after a swap occurs
25:   /// @param liquidationPair The pair that was swapped against

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/interfaces/IRngAuctionRelayListener.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { AuctionResult } from "IAuction.sol";
5: 
6: /// @title IRngAuctionRelayListener
7: /// @author G9 Software Inc.
8: /// @notice Interface to receive RNG auction relays
9: interface IRngAuctionRelayListener {
10: 
11:     /// @notice Called by the relayer when the RNG auction is complete
12:     /// @param randomNumber The random number generated by the RNG auction
13:     /// @param rngCompletedAt The timestamp when the RNG service delivered the random number
14:     /// @param rewardRecipient The address of the recipient for the relay reward
15:     /// @param sequenceId The sequence id of the RNG auction
16:     /// @return any custom data it likes to track the relay.
17:     function rngComplete(
18:         uint256 randomNumber,
19:         uint256 rngCompletedAt,
20:         address rewardRecipient,
21:         uint32 sequenceId,
22:         AuctionResult calldata auctionResult
23:     ) external returns (bytes32);
24: }
25: 

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity ^0.8.0;
3: 
4: import "forge-std/console2.sol";
5: 
6: import { ILiquidationSource } from "pt-v5-liquidator-interfaces/interfaces/ILiquidationSource.sol";
7: import { PrizePool, IERC20, TwabController } from "pt-v5-prize-pool/PrizePool.sol";
8: import { UD60x18, convert } from "prb-math/UD60x18.sol";
9: import { UD2x18, intoUD60x18 } from "prb-math/UD2x18.sol";
10: import { Ownable } from "openzeppelin/access/Ownable.sol";
11: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol";
12: import { SafeCast } from "openzeppelin/utils/math/SafeCast.sol";
13: 
14: /// @notice Emitted when someone tries to call liquidate and isn't the liquidation pair
15: error OnlyLiquidationPair();
16: 
17: /// @notice Emitted when the initial available exceeds the balance
18: /// @param initialAvailable The initial available
19: /// @param balance The actual token balance
20: error InitialAvailableExceedsBalance(uint144 initialAvailable, uint256 balance);
21: 
22: /// @notice Emitted when the liquidator attempts to liquidate more than the available balance
23: error InsufficientAvailableBalance(uint256 amountOut, uint256 available);
24: 
25: /// @notice Emitted when the liquidator attempts to liquidate for a token other than the prize token 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity 0.8.19;
3: 
4: import { ILiquidationSource } from "pt-v5-liquidator-interfaces/ILiquidationSource.sol";
5: import { ILiquidationPair } from "pt-v5-liquidator-interfaces/ILiquidationPair.sol";
6: import { SD59x18, uEXP_MAX_INPUT, wrap, convert, unwrap } from "prb-math/SD59x18.sol";
7: 
8: import { ContinuousGDA } from "libraries/ContinuousGDA.sol";
9: 
10: error AmountInZero();
11: error AmountOutZero();
12: error TargetFirstSaleTimeLtPeriodLength(uint passedTargetSaleTime, uint periodLength);
13: error SwapExceedsAvailable(uint256 amountOut, uint256 available);
14: error SwapExceedsMax(uint256 amountInMax, uint256 amountIn);
15: error DecayConstantTooLarge(SD59x18 maxDecayConstant, SD59x18 decayConstant);
16: error PurchasePriceIsZero(uint256 amountOut);
17: 
18: /***
19:  * @title LiquidationPair
20:  * @author G9 Software Inc.
21:  * @notice Auctions one token for another in a periodic continuous gradual dutch auction. Auctions occur over a limit period so that the price can be adjusted.
22:  * @dev This contract is designed to be used with the LiquidationRouter contract.
23:  */
24: contract LiquidationPair is ILiquidationPair {
25: 

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/libraries/ContinuousGDA.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: GPL-3.0
2: pragma solidity 0.8.19;
3: 
4: import { SD59x18, convert, unwrap } from "prb-math/SD59x18.sol";
5: 
6: /// @title ContinuousGDA
7: /// @author G9 Software Inc.
8: /// @notice Implements the Continous Gradual Dutch Auction formula
9: /// See https://www.paradigm.xyz/2022/04/gda
10: /// @dev Pricing formula adapted from https://github.com/FrankieIsLost/gradual-dutch-auction/blob/master/src/ContinuousGDA.sol
11: library ContinuousGDA {
12: 
13:   /// @notice a helpful constant
14:   SD59x18 internal constant ONE = SD59x18.wrap(1e18);
15: 
16:   /// @notice Calculate purchase price for a given amount of tokens
17:   /// @param _amount The amount of tokens to purchase
18:   /// @param _emissionRate The emission rate of the CGDA
19:   /// @param _k The initial price of the CGDA
20:   /// @param _decayConstant The decay constant of the CGDA
21:   /// @param _timeSinceLastAuctionStart The elapsed time since the last consumed timestamp
22:   /// @return The purchase price for the given amount of tokens
23:   function purchasePrice(
24:     SD59x18 _amount,
25:     SD59x18 _emissionRate,

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { RemoteOwner } from "remote-owner/RemoteOwner.sol";
5: import { RemoteOwnerCallEncoder } from "remote-owner/libraries/RemoteOwnerCallEncoder.sol";
6: import { ISingleMessageDispatcher } from "erc5164/interfaces/ISingleMessageDispatcher.sol";
7: 
8: import {
9:     RngAuctionRelayer,
10:     RngAuction,
11:     IRngAuctionRelayListener
12: } from "abstract/RngAuctionRelayer.sol";
13: 
14: /// @title RngAuctionRelayerRemoteOwner
15: /// @author G9 Software Inc.
16: /// @notice This contract allows anyone to relay RNG results to an IRngAuctionRelayListener on another chain.
17: /// @dev This contract uses a Remote Owner, which allows a contract on one chain to operate an address on another chain.
18: contract RngAuctionRelayerRemoteOwner is RngAuctionRelayer {
19: 
20:     /// @notice Emitted when the relay was successfully dispatched to the ERC-5164 Dispatcher
21:     /// @param rewardRecipient The address that shall receive the RNG relay reward.
22:     /// @param messageId The message ID of the dispatched message.
23:     event RelayedToDispatcher(address indexed rewardRecipient, bytes32 indexed messageId);
24: 
25:     /// @notice The ERC-5164 Dispatcher to use to bridge messages

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L1-L1
```javascript
1: // SPDX-License-Identifier: MIT
2: pragma solidity ^0.8.19;
3: 
4: import { IERC20 } from "openzeppelin/token/ERC20/IERC20.sol";
5: import { SafeERC20 } from "openzeppelin/token/ERC20/utils/SafeERC20.sol";
6: import { Ownable } from "owner-manager/Ownable.sol";
7: import { RNGInterface } from "rng/RNGInterface.sol";
8: import { UD2x18 } from "prb-math/UD2x18.sol";
9: import { UD60x18, convert, intoUD2x18 } from "prb-math/UD60x18.sol";
10: 
11: import { RewardLib } from "libraries/RewardLib.sol";
12: import { IAuction, AuctionResult } from "interfaces/IAuction.sol";
13: 
14: /**
15:   * @notice The results of a successful RNG auction.
16:   * @param recipient The recipient of the auction reward
17:   * @param rewardFraction The reward fraction that the user will receive
18:   * @param sequenceId The id of the sequence that this auction belonged to
19:   * @param rng The RNG service that was used to generate the random number
20:   * @param rngRequestId The id of the RNG request that was made
21:   * @dev   The `sequenceId` value should not be assumed to be the same as a prize pool drawId, but the sequence and offset should match the prize pool.
22:   */
23: struct RngAuctionResult {
24:   address recipient;
25:   UD2x18 rewardFraction;

```


</details>


# [GAS-26] The result of a function call should be cached rather than re-calling the function
## Number of instances found
 19 

## Resolution
 External calls in Solidity are costly in terms of gas usage. This can significantly impact contract efficiency and cost. Functions that make repetitive calls to fetch the same data from other contracts can cause unnecessary gas expenditure. To optimize this, it's advisable to store the returned value of these function calls in a state variable, essentially caching the data. This data can be updated at regular intervals or under specific conditions instead of fetching it from the external contract on every invocation. Be sure to analyze the frequency of data change in the external contract to balance data freshness with gas efficiency when implementing caching. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L145-L147
```javascript
145:   function maxAmountOut() external returns (uint256) { // <= FOUND
146:     _checkUpdateAuction();
147:     return _maxAmountOut(); // <= FOUND
148:   }

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPair.sol#L229-L231
```javascript
229:   function getElapsedTime() external returns (uint256) { // <= FOUND
230:     _checkUpdateAuction();
231:     return uint256(convert(_getElapsedTime())); // <= FOUND
232:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L215-L216
```javascript
215:   function canStartNextSequence() external view returns (bool) { // <= FOUND
216:     return _canStartNextSequence(); // <= FOUND
217:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L229-L230
```javascript
229:   function auctionElapsedTime() external view returns (uint64) { // <= FOUND
230:     return _auctionElapsedTime(); // <= FOUND
231:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L234-L235
```javascript
234:   function currentFractionalReward() external view returns (UD2x18) { // <= FOUND
235:     return _currentFractionalReward(); // <= FOUND
236:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L261-L262
```javascript
261:   function openSequenceId() external view returns (uint32) { // <= FOUND
262:     return _openSequenceId(); // <= FOUND
263:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L277-L278
```javascript
277:   function isRngComplete() external view returns (bool) { // <= FOUND
278:     return _isRngComplete(); // <= FOUND
279:   }

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L381-L386
```javascript
381:   function _auctionElapsedTime() internal view returns (uint64) { // <= FOUND
382:     uint64 currentTime = _currentTime(); // <= FOUND
383:     if (currentTime < sequenceOffset) {
384:       return 0;
385:     }
386:     return (_currentTime() - sequenceOffset) % sequencePeriod; // <= FOUND
387:   }

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L117-L120
```javascript
117:   function _checkSender() internal view {
118:     if (!isTrustedExecutor(msg.sender)) revert LocalSenderNotExecutor(msg.sender);
119:     if (_fromChainId() != _originChainId) revert OriginChainIdUnsupported(_fromChainId()); // <= FOUND
120:     if (_msgSender() != address(_originChainOwner)) revert OriginSenderNotOwner(_msgSender()); // <= FOUND
121:   }

```


</details>




# [GAS-28] Add unchecked {} for subtractions where the operands cannot underflow
## Number of instances found
 3 

## Resolution
 n Solidity 0.8.x and above, arithmetic operations like subtraction automatically check for underflows and overflows, and revert the transaction if such a condition is met. This built-in safety feature provides a layer of security against potential numerical errors. However, these automatic checks also come with additional gas costs.

In some situations, you may already have a guard condition, like a require() statement or an if statement, that ensures the safety of the arithmetic operation. In such cases, the automatic check becomes redundant and leads to unnecessary gas expenditure.

For example, you may have a function that subtracts a smaller number from a larger one, and you may have already verified that the smaller number is indeed smaller. In this case, you're already sure that the subtraction operation won't underflow, so there's no need for the automatic check.

In these situations, you can use the unchecked { } block around the subtraction operation to skip the automatic check. This will reduce gas costs and make your contract more efficient, without sacrificing security. However, it's critical to use unchecked { } only when you're absolutely sure that the operation is safe. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L67-L67
```javascript
67:       remainingReserve = remainingReserve - _rewards[i]; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L191-L191
```javascript
191:     uint256 remainingBalance = availableBalance - _amount; // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L264-L264
```javascript
264:     uint256 deltaTime = block.timestamp - boost.lastAccruedAt; // <= FOUND

```


</details>


# [GAS-29] Use bitmap to save gas
## Number of instances found
 1 

## Resolution
 Bitmaps in Solidity are essentially a way of representing a set of boolean values within an integer type variable such as `uint256`. Each bit in the integer represents a true or false value (1 or 0), thus allowing efficient storage of multiple boolean values.

Bitmaps can save gas in the Ethereum network because they condense a lot of information into a small amount of storage. In Ethereum, storage is one of the most significant costs in terms of gas usage. By reducing the amount of storage space needed, you can potentially save on gas fees.

Here's a quick comparison:

If you were to represent 256 different boolean values in the traditional way, you would have to declare 256 different `bool` variables. Given that each `bool` occupies a storage slot and each storage slot costs 20,000 gas to initialize, you would end up paying a considerable amount of gas.

On the other hand, if you were to use a bitmap, you could store these 256 boolean values within a single `uint256` variable. In other words, you'd only pay for a single storage slot, resulting in significant gas savings.

However, it's important to note that while bitmaps can provide gas efficiencies, they do add complexity to the code, making it harder to read and maintain. Also, using bitmaps is efficient only when dealing with a large number of boolean variables that are frequently changed or accessed together. 

In contrast, the straightforward counterpart to bitmaps would be using arrays or mappings to store boolean values, with each `bool` value occupying its own storage slot. This approach is simpler and more readable but could potentially be more expensive in terms of gas usage. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L91-L91
```javascript
91:     deployedPairs[_liquidationPair] = true; // <= FOUND

```


</details>


# [GAS-30] Use assembly to emit events
## Number of instances found
 17 

## Resolution
 With the use of inline assembly in Solidity, we can take advantage of low-level features like scratch space and the free memory pointer, offering more gas-efficient ways of emitting events. The scratch space is a certain area of memory where we can temporarily store data, and the free memory pointer indicates the next available memory slot. Using these, we can efficiently assemble event data without incurring additional memory expansion costs. However, safety is paramount: to avoid overwriting or leakage, we must cache the free memory pointer before use and restore it afterward, ensuring that it points to the correct memory location post-operation. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationPairFactory.sol#L93-L93
```javascript
93:     emit PairCreated( // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L52-L52
```javascript
52:     emit LiquidationRouterCreated(liquidationPairFactory_); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-cgda-liquidator/tree/7f95bcacd4a566c2becb98d55c1886cadbaa8897/src/LiquidationRouter.sol#L77-L77
```javascript
77:     emit SwappedExactAmountOut(_liquidationPair, _receiver, _amountOut, _amountInMax, amountIn); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L200-L200
```javascript
200:     emit RngAuctionCompleted( // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuction.sol#L437-L437
```javascript
437:     emit SetNextRngService(_newRng); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerDirect.sol#L43-L43
```javascript
43:         emit DirectRelaySuccess(_relayRewardRecipient, returnData); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngAuctionRelayerRemoteOwner.sol#L67-L67
```javascript
67:         emit RelayedToDispatcher(rewardRecipient, messageId); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L159-L159
```javascript
159:     emit RngSequenceCompleted( // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L171-L171
```javascript
171:         emit AuctionRewardDistributed(_sequenceId, auctionResults[i].recipient, i, _reward); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/abstract/AddressRemapper.sol#L60-L60
```javascript
60:     emit AddressRemapped(_caller, _destination); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L157-L157
```javascript
157:     emit SetBoost( // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L175-L175
```javascript
175:     emit Deposited(_token, msg.sender, _amount); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L195-L195
```javascript
195:     emit Withdrawn(_token, msg.sender, _amount); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L228-L228
```javascript
228:     emit Liquidated( // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBooster.sol#L254-L254
```javascript
254:     emit BoostAccrued(_tokenOut, available); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-vault-boost/tree/9d640051ab61a0fdbcc9500814b7f8242db9aec2/src/VaultBoosterFactory.sol#L31-L31
```javascript
31:         emit CreatedVaultBooster(booster, _prizePool, _vault, _owner); // <= FOUND

```

https://github.com/GenerationSoftware/remote-owner/tree/285749ab51e98afc8ebb4e4049a4348d669a3e9d/src/RemoteOwner.sol#L108-L108
```javascript
108:     emit OriginChainOwnerSet(_newOriginChainOwner); // <= FOUND

```


</details>


# [GAS-31] Shorten the array rather than copying to a new one
## Number of instances found
 2 

## Resolution
 Leveraging inline assembly in Solidity provides the ability to directly manipulate the length slot of an array, thereby altering its length without the need to copy the elements to a new array of the desired size. This technique is more gas-efficient as it avoids the computational expense associated with array duplication. However, this method circumvents the type-checking and safety mechanisms of high-level Solidity and should be used judiciously. Always ensure that the array doesn't contain vital data beyond the revised length, as this data will become unreachable yet still consume storage space. 

## Findings
 Findings are labeled with ' <= FOUND' 


<details><summary>Click to show findings</summary>


https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/RngRelayAuction.sol#L147-L147
```javascript
147:     AuctionResult[] memory auctionResults = new AuctionResult[](2); // <= FOUND

```

https://github.com/GenerationSoftware/pt-v5-draw-auction/tree/f1c6d14a1772d6609de1870f8713fb79977d51c1/src/libraries/RewardLib.sol#L64-L64
```javascript
64:     uint256[] memory _rewards = new uint256[](_auctionResultsLength); // <= FOUND

```


</details>

# Contest details are not available. Why not?
The contest is limited to specific participants. Most Code4rena contests are open and public, but some have special requirements. In those cases, the code and contest details remain private (at least for now).

## Automated Findings / Publicly Known Issues

The 4naly3er report can be found [here](https://github.com/code-423n4/2023-11-panoptic/blob/main/4naly3er-report.md).

Automated findings output for the audit can be found [here](https://github.com/code-423n4/2023-11-panoptic/blob/main/bot-report.md) within 24 hours of audit opening.

_Note for C4 wardens: Anything included in this `Automated Findings / Publicly Known Issues` section is considered a publicly known issue and is ineligible for awards._

- Transfers of ERC1155 SFPM tokens are very limited by design. It is expected that certain accounts will be unable to transfer or receive tokens. 
Some tokens may not be transferable at all.
- Construction helper functions (prefixed with add) in the TokenId library and other types do not perform extensive input validation. Passing invalid or nonsensical inputs into these functions or attempting to overwrite already filled slots may yield unexpected or invalid results. This is by design, so it is expected that users
of these functions will validate the inputs beforehand. 
- Pools with a tick spacing of 1 are not currently supported. For the purposes of this audit, the only tick spacings that are supported are 10, 60, and 200 (corresponding to fee tiers of 5bps, 30bps, and 100bps respectively).
- Very large quantities of tokens are not supported. It should be assumed that for any given pool, the cumulative amount of tokens that enter the system (associated with that pool, through adding liquidity, collection, etc.) will not exceed 2^127 - 1. Note that this is only a per-pool assumption, so if it is broken on one pool it should not affect the operation of any other pools, only the pool in question.

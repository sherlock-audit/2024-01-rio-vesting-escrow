
# Rio Vesting Escrow contest details

- Join [Sherlock Discord](https://discord.gg/MABEWyASkp)
- Submit findings using the issue page in your private contest repo (label issues as med or high)
- [Read for more details](https://docs.sherlock.xyz/audits/watsons)

# Q&A

### Q: On what chains are the smart contracts going to be deployed?
Mainnet
___

### Q: Which ERC20 tokens do you expect will interact with the smart contracts? 
Any, with the exception of rebasing tokens and tokens that charge a fee on transfer.
___

### Q: Which ERC721 tokens do you expect will interact with the smart contracts? 
None
___

### Q: Do you plan to support ERC1155?
No
___

### Q: Which ERC777 tokens do you expect will interact with the smart contracts? 
None
___

### Q: Are there any FEE-ON-TRANSFER tokens interacting with the smart contracts?

No
___

### Q: Are there any REBASING tokens interacting with the smart contracts?

No
___

### Q: Are the admins of the protocols your contracts integrate with (if any) TRUSTED or RESTRICTED?
TRUSTED
___

### Q: Is the admin/owner of the protocol/contracts TRUSTED or RESTRICTED?
TRUSTED
___

### Q: Are there any additional protocol roles? If yes, please explain in detail:
Factory Owner: This role can update the manager, update the voting adaptor, revoke unvested tokens, revoke all tokens (if enabled), and disable full revocation (if enabled).
Factory Manager: This role can revoke unvested tokens. This role should not be able to execute any other functions.
Vesting Escrow Recipient: This role can delegate, vote, vote with reason, and claim tokens. This role should not be able to claim tokens before they're vested.
___

### Q: Is the code/contract expected to comply with any EIPs? Are there specific assumptions around adhering to those EIPs that Watsons should be aware of?
No
___

### Q: Please list any known issues/acceptable risks that should not result in a valid finding.
The ability for the factory owner to swap out the voting adaptor while a delegate, vote, or vote with reason call is pending in order to trick a recipient into executing an arbitrary call.
___

### Q: Please provide links to previous audits (if any).
Not a direct audit, but worth mentioning as it's an audit of the Vyper code that the vesting escrow was originally "forked" from: https://github.com/lidofinance/lido-vesting-escrow/blob/main/audits/lido-trp-vesting-escrow.pdf
___

### Q: Are there any off-chain mechanisms or off-chain procedures for the protocol (keeper bots, input validation expectations, etc)?
No
___

### Q: In case of external protocol integrations, are the risks of external contracts pausing or executing an emergency withdrawal acceptable? If not, Watsons will submit issues related to these situations that can harm your protocol's functionality.
Yes, the risks of external governance integrations pausing or otherwise halting delegation and voting are acceptable.
___

### Q: Do you expect to use any of the following tokens with non-standard behaviour with the smart contracts?
No
___

### Q: Add links to relevant protocol resources
https://github.com/rio-org/rio-vesting-escrow/blob/main/README.md
___



# Audit scope


[rio-vesting-escrow @ cd1601bb2862fdaebe3196689176b384f1324c4c](https://github.com/rio-org/rio-vesting-escrow/tree/cd1601bb2862fdaebe3196689176b384f1324c4c)
- [rio-vesting-escrow/src/VestingEscrow.sol](rio-vesting-escrow/src/VestingEscrow.sol)
- [rio-vesting-escrow/src/VestingEscrowFactory.sol](rio-vesting-escrow/src/VestingEscrowFactory.sol)
- [rio-vesting-escrow/src/adaptors/OZVotingAdaptor.sol](rio-vesting-escrow/src/adaptors/OZVotingAdaptor.sol)



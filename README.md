#Crowdfunding Smart Contract
This is a smart contract written in Solidity for managing a crowdfunding campaign on the Ethereum blockchain. The contract allows contributors to send funds to a beneficiary until a funding goal is reached or the campaign's deadline passes. If the funding goal is not met, contributors can request a refund.

##Features
Funding Goal: Set a target amount that the campaign aims to raise.
Deadline: The campaign runs for a specified number of days.
Minimum Contribution: Set a minimum amount that each contributor must send.
Automatic Refund: If the funding goal is not reached by the deadline, contributors can claim a refund.
Extendable Deadline: The campaign's deadline can be extended if necessary.
##Contract Parameters
beneficiary: The address that will receive the funds if the funding goal is met.
goal: The target amount of Ether to be raised.
deadline: The timestamp after which the campaign will automatically close.
minimumContribution: The minimum amount of Ether required to contribute to the campaign.
###Functions
1. constructor
Initializes the contract with the beneficiary address, funding goal, duration of the campaign in days, and minimum contribution amount.
constructor(
    address payable _beneficiary,
    uint _goal,
    uint _durationInDays,
    uint _minimumContribution
)
2. contribute
Allows users to contribute to the campaign. Checks if the crowdsale is still open, if the contribution meets the minimum requirement, and if the campaign is still within the deadline.
function contribute() public payable
3. checkGoalReached
Checks if the funding goal has been reached and transfers the raised amount to the beneficiary. This function can only be called after the crowdsale is closed.
function checkGoalReached() public
4. closeCrowdsale
Closes the crowdsale, preventing any further contributions. This function should be called after the deadline has passed.
function closeCrowdsale() public
5. refund
Allows contributors to claim a refund if the funding goal was not reached. This function can only be called after the crowdsale is closed.
function refund() public
6. extendDeadline
Allows the beneficiary to extend the deadline of the crowdsale by a specified number of days.
function extendDeadline(uint _extraDays) public
##Deployment
To deploy this contract, you need to use a Solidity-compatible Ethereum development environment like Remix or Truffle. Make sure you have a compatible wallet like MetaMask set up with enough Ether to deploy the contract.

###Example Deployment:
Set up your environment with a wallet and some Ether.
Compile the contract using the Solidity compiler.
Deploy the contract by passing the required constructor parameters:
_beneficiary: The wallet address to receive the funds.
_goal: The fundraising target in wei.
_durationInDays: The duration of the campaign in days.
_minimumContribution: The minimum contribution amount in wei.
##License
This project is licensed under the MIT License.


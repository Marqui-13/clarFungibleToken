#Clarity Fungible Token Smart Contract

This README documents the official Clarity fungible token smart contract, modeled after the ERC-20 token standard. This contract allows for the creation, transfer, and management of a fungible token on the Stacks blockchain. The contract includes features such as minting tokens, transferring tokens between accounts, managing allowances for third-party transfers, and querying account balances.

##Features

	•	Token Minting: Initial tokens are minted and distributed to specified accounts upon contract deployment.
	•	Token Transfer: Allows token holders to transfer their tokens to another principal (account).
	•	Allowance Management: Enables token holders to authorize a third party to transfer a specified amount of their tokens.
	•	Balance Queries: Provides the ability to query the token balance of any account.

##Contract Functions

###Public Functions

	•	transfer-token: Transfers tokens from the sender to a specified recipient.
	•	transfer-from: Allows a spender to transfer tokens from one account to another, given they have enough allowance.
	•	approve: Authorizes a spender to withdraw tokens up to a specified amount.
	•	revoke: Revokes a previously set allowance for a spender.
	•	balance-of: Returns the balance of tokens held by a specified account.

###Private Functions

	•	mint: Mints new tokens to a specified account. This function is called upon contract initialization to set up the initial token distribution.
	•	transfer: Handles the transfer logic, ensuring tokens are transferred only if the sender has enough balance.
	•	increase-allowance and decrease-allowance: Manage the allowance a token holder provides to a spender.
	•	allowance-of: Returns the amount of tokens a spender is allowed to transfer on behalf of an owner.

##Getting Started

To interact with this smart contract, you’ll need:

	•	A Clarity compatible wallet.
	•	Access to the Stacks Blockchain API for deploying and interacting with the contract.
	•	STX tokens to cover transaction fees on the testnet.

##Deployment

	1.	Clone this repository to your local machine.
	2.	Use Clarinet or the Stacks Blockchain API to deploy the contract on the Stacks blockchain.

##Example Usage

###Minting Tokens:

The contract automatically mints and distributes tokens to predefined accounts upon initialization.

###Transferring Tokens:

(contract-call? .your-contract-address transfer-token u100 .recipient-address)

###Approving a Spender:

(contract-call? .your-contract-address approve u100 .spender-address)

###Transferring Tokens on Behalf of Another Account:

(contract-call? .your-contract-address transfer-from u50 .owner-address .recipient-address)

##Contributing

Contributions to this contract or documentation are welcome. Please fork the repository, make your changes, and submit a pull request for review.

##License

This project is licensed under the GNU General Public License as published by the Free Software Foundation, either version 3 of the License or (at your option) any later version.

##Disclaimer

This contract is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this project. If not, see http://www.gnu.org/licenses/.

##Contact

For any inquiries or contributions, please open an issue in the GitHub repository associated with this contract.

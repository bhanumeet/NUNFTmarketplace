# Decentralized-NFT-Marketplace

This project is a decentralized marketplace for NFTs where creators can deploy their images and associated metadata to IPFS (InterPlanetary File System) and mint NFTs (Non-Fungible Tokens) to a specified token address. The ownership of these NFTs is then transferred to the marketplace admin, who gains the ability to list these NFTs on the marketplace.

Users can connect their wallets to the platform, allowing them to buy the listed NFTs. Additionally, users have the capability to relist purchased NFTs on the marketplace, enabling a fluid and user-driven marketplace experience.

The user interface (UI) of this marketplace is deployed to IPFS, ensuring decentralized access and availability to all users. This decentralized approach enhances the platform's resilience and accessibility, aligning with the principles of decentralization central to blockchain and NFT technologies.

## Installation

To install and set up this project, follow these steps:

#### 1. Clone the Repository

Clone the repository to your local machine using Git:

`git clone https://github.com/rakshithvk19/Decentralized-NFT-Marketplace.git`

#### 2. Install Frontend Dependencies

Navigate to the `frontend` directory:

`cd decentralized-nft-marketplace/frontend`

Install the required Node.js packages:

`npm install`

#### 3. Configure Pinata for IPFS Deployment

To deploy images and NFT metadata to IPFS, you'll need to generate your own API key and JWT (JSON Web Token) from Pinata. Follow the Pinata documentation to obtain these credentials.

#### 4. Install Foundry and ERC721 Libraries

Ensure you have Foundry and the ERC721 libraries from OpenZeppelin installed. If not already installed, use npm to install:

`forge install @openzeppelin/foundry --no-comit`

`forge install @openzeppelin/contracts --no-commit`

#### 5. Set Up Environment Variables

Create a `.env` file in the project root directory and add the following variables:

```plaintext
PRIVATE_KEY=your_wallet_private_key
RPC_URL=rpc_url_for_your_chosen_network
```

Replace your_wallet_private_key with your Ethereum wallet's private key (for contract deployment), and rpc_url_for_your_chosen_network with the RPC URL of the Ethereum network you want to deploy the contracts to (e.g., Holskey).

#### 6. Deploy Contracts to Chosen Network

Use the make command and specify the target network to deploy the contracts. For example, to deploy the contracts to the holskey network:

`make deploy holskey`

Replace holskey with the name of your target network configured in the project.

By following these steps, you'll have the project set up locally with dependencies installed and contracts deployed to the specified network, ready for use.

## Usage

### 1. Artist Minting and Listing NFTs

#### Connect Wallet and Add NFT:

- The artist (creator) connects their Ethereum wallet to the frontend of the marketplace.
- They upload an image for the NFT, along with providing a name and description for the artwork.
- The frontend triggers a process where the NFT image is stored on IPFS (InterPlanetary File System).

#### Minting the NFT:

- Using the deployed `Token.sol` contract, the artist mints the NFT by providing the IPFS URL of the image, name, and description.
- The metadata (name, description, IPFS URL) is stored as part of the token metadata within the contract.

### 2. Listing NFTs for Sale

#### Setting Listing Price:

- Once the NFT is minted, the artist can set a listing price for the NFT.
- The listing price is denominated in the specified cryptocurrency (e.g., Ethereum).

#### Transferring Ownership to Marketplace:

- To list the NFT on the marketplace, the artist initiates a transfer of ownership of the NFT to the marketplace owner's address.

### 3. Buying and Selling on the Marketplace

#### Connecting Wallet to Marketplace:

- Users (collectors) connect their Ethereum wallet to the decentralized marketplace frontend.

#### Browsing Listed NFTs:

- Users can view all the listed NFTs available for sale on the marketplace.
- They can also see the NFTs they currently own.

#### Purchasing NFTs:

- To buy an NFT, users can select the desired artwork and proceed with the purchase by confirming the transaction via their wallet.
- The payment is made directly to the seller's wallet, and the ownership of the NFT is transferred to the buyer.

#### Relisting NFTs:

- Owners of NFTs can relist their artworks on the marketplace if they wish to sell them again.
- They can adjust the listing price or update the metadata associated with the NFT.

### Data Flow Diagram

1. Minting of the NFT by creator.

   ![Minting of the NFT by creator](./Documentation/Minting%20NFT%20by%20Artist.png)

2. Listing and Buying of the NFT by user.
   ![Listing and Buying of the NFT by user](./Documentation/Listing%20of%20NFT.png)

### Licenses

[MIT](https://choosealicense.com/licenses/mit/)

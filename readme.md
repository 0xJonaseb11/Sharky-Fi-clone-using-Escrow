# Build A Lending & Borrowing Platform

Based on the [Build A Lending & Borrowing Platform](https://calyptus.co/courses/9-build-a-lending-borrowing-platform/) module, this walkthrough takes you through the process of creating a platform where users can lend SOL in exchange for NFTs from a specific collection, all facilitated through a secure vault system using [Anchor](https://www.anchor-lang.com/).

## Table of Contents
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [Questions](#questions)
- [License](#license)

## Getting Started

To use this fork, you need to have [yarn](https://yarnpkg.com/getting-started/install), [Anchor](https://www.anchor-lang.com/docs/installation) and the [Solana cli suite](https://solana.com/developers/guides/getstarted/setup-local-development) installed on your machine. 

It is highly recommended that you start this project from scratch, following along with the tutorial. 

To use the fork, follow the steps outlined below: 

1. Clone your forked repo.

```bash
git clone https://github.com/<YOUR-USERNAME>/Sharky-Fi-clone-using-Escrow
```

2. Change directory into the root of your cloned repo and install missing node packages

```bash
yarn install
```

**NOTE:** You must use yarn to install the dependencies. If you use a different package manager, you will run into issues minting the NFT.

3. Build your anchor project.

```bash
anchor build
```

4. List the project deployment keys and copy the address to a clipboard

```bash
anchor keys list
```

5. Update your [`Anchor.toml`](Anchor.toml) file, by using the address generated in the previous step. 

```toml
[programs.devnet]
nft_lend_borrow = "<ADD YOUR ADDRESS HERE>"
```

6. Update your [`lib.rs`](programs/nft-lend-borrow/src/lib.rs) file by adding the the address generated in step 4 to the `declare_id!()` macro

```rust
    // snip

pub use errors::ErrorCodes;
pub use instructions::*;
pub use states::*;

declare_id!("<PLACE YOUR ADDRESS HERE>");

#[program]
pub mod nft_lend_borrow {
    // snip
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Questions

Did you encounter a challenge following the tutorial or running the fork? 
Head over to our [learning support](https://discord.com/channels/1130457754826461216/1132978998155165806) channel on our [Discord](https://discord.gg/38KftAhW) or alternatively, raise a ticket. 

We are always happy to lend a helping hand

## License

All files within this repository are licensed under the MIT License unless explicitly stated otherwise.

100% Open Source software.

© 2023 [Calyptus] - See [LICENSE](https://opensource.org/license/mit/) for details.

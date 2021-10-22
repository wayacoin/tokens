Trust Wallet Assets Info
Check

Overview
Trust Wallet token repository is a comprehensive, up-to-date collection of information about several thousands (!) of crypto tokens.

Trust Wallet uses token logos from this source, alongside a number of other projects.

The repository contains token info from several blockchains, info on dApps, staking validators, etc. For every token a logo and optional additional information is available (such data is not available on-chain).

Such a large collection can be maintained only through a community effort, so feel free to add your token.



How to add token
Please note that brand new tokens are not accepted, the projects have to be sound, with information available, and non-minimal circulation (for limit details see https://community.trustwallet.com/t/how-to-submit-a-token-logo/3863).

Assets App
The Assets web app can be used for most new token additions (Github account is needed).

Quick starter
Details of the repository structure and contribution guidelines are listed on the Developers site. Here is a quick starter summary for the most common use case.

Adding an ERC20 token checklist:

 Make sure your smartcontract has more than 2,500 address holders, otherwise you will be rejected
 Fork the Github repository
 Create folder with name of token smartcontact address in checksum format blockchains/ethereum/assets/<token_smartcontract_address>/.
 Tell your designer that token image must be in PNG format, avoid transparent background, recommended size 256x256px, max. 512x512px, with max file size of 100kB, for further details read image rules.
 Upload your logo with file named logo.png to previously created folder with smartcontract address, and if you done all correctly your path should look like this. blockchains/ethereum/assets/0x1234567461d3f8Db7496581774Bd869C83D51c93/logo.png
 Create info.json file with info about the token/project
 Create a pull request to the main repo
 Pay the processing fee
Documentation
For details, see the Developers site:

Contribution guidelines

Repository details

Scripts
There are several scripts available for maintainers:

npm run check -- Execute validation checks; also used in continuous integration.
npm run check-sanity -- Strict subset of checks
npm run fix -- Perform automatic fixes where possible
npm run fix-sanity -- Stricter subset
npm run updateAuto -- Run automatic updates from external sources, executed regularly (GitHub action)
npm run update -- Run manual updates from external sources, for manual use.
npm test -- Run script unit tests
npm lint -- Run Lint static code check
On Checks
This repo contais a set of scripts for verification of all the information. Implemented as Typescript scripts, available through npm run check, and executed in CI build; checks the whole repo. There are similar check logic implemeted:

in assets-management app; for checking changed token files in PRs, or when creating a PR. Implemented as a Typescript library, checks diffs, can be run from browser environment.
in merge-fee-bot, which runs as a GitHub app shows result in PR comment. Also uses library, but executes in a non-browser environment.
Trading pair maintenance
Info on supported trading pairs are stored in tokenlist.json files. Trading pairs can be updated -- from Uniswap/Ethereum and PancakeSwap/Smartchain -- using update script (and checking in changes). Minimal limit values for trading pair inclusion are set in the config.ts file. There are also options for force-include and force-exclude in the config.

Disclaimer
Trust Wallet team allows anyone to submit new assets to this repository. However, this does not mean that we are in direct partnership with all of the projects.

Trust Wallet team will reject projects that are deemed as scam or fraudulent after careful review. Trust Wallet team reserves the right to change the terms of asset submissions at any time due to changing market conditions, risk of fraud, or any other factors we deem relevant.

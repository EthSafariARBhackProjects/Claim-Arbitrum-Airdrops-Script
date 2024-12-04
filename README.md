# Arbitrum airdrop claimer
This script is created in order to claim an Arbitrum airdrop instantly when distribution starts.
After claiming script can transfer tokens to any address. It also supports multiple accounts, so you can even claim on 50+ accounts and still send tokens to different addresses 

## Disclaimer
This script was created for an EthSafari Arbitrum hackathon. We are not responsible for any issues which can occur when using this script.

## How to run
In order to run this script you need to have Node.js installed. You can [download Node.js here](https://nodejs.org/en/download).
Once you have Node.js follow the next steps:
1) Open terminal in repository folder and type `npm install` or `yarn`
2) Run script by typing `npm start` or `yarn start`
3) If you want to pre-approve ARB for DEXes run `npm run approve` or `yarn approve`

## How to open terminal? 
https://www.groovypost.com/howto/open-command-window-terminal-window-specific-folder-windows-mac-linux/

## How to configure
In order to use this script you need to have your own Arbitrum and Ethereum RPC which you can obtain on [Alchemy](https://alchemy.com/?r=baefaebe6e6ad7e2) or any other provider.
Main configuration can be found in `config.js` file. Just follow the instruction below:
1) Create an account on [Alchemy](https://alchemy.com/?r=baefaebe6e6ad7e2).
2) In Alchemy Dashboard create 2 apps:
   - Ethereum mainnet chain
   - Arbitrum mainnet chain
5) Open `config.js` file and edit the next fields:
   - Replace `RPC_ARBITRUM_HTTP` with your Arbitrum HTTPS key from Alchemy.
   - Replace `RPC_ETHEREUM_WSS` with your Ethereum WEBSOCKETS key from Alchemy.
8) In `config.js` find `ACCOUNTS` array and put your accounts. If you want to claim without sending tokens then leave `addressToSendTokens` empty.

Example:
```javascript
const RPC_ARBITRUM_HTTP = "https://arb-mainnet.g.alchemy.com/v2/sMsdjLabS-N1oSGcpMn23Q21UOcZQP";
const RPC_ETHEREUM_WSS = "wss://eth-mainnet.g.alchemy.com/v2/sMsdjLabS-N1oSGcpMn23Q21UOcZQP";
        
export const ACCOUNTS = [
  {
    privateKey: "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    addressToSendTokens: "0x2D5500B322a061d8FF56287C278d6B64086AA0fD"
  },
  {
    privateKey: "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    addressToSendTokens: "" // <- claim only, no transfertheeoduol001

  },
]
```

## Approve for DEXes
There is also a script to pre-approve ARB token for trading on DEXes. You can approve from all your accounts and be ready once trading on DEX starts. By default I added only Uniswap for approval but you can edit `DEXES` in `config.js` and add more DEXes to approve.

In order to use approve script run `npm run approve` or `yarn approve`. Make sure to configure `config.js` first.

## Errors
If you see an error something like `TypeError [ERR_UNKNOWN_FILE_EXTENSION]` or `The engine "node" is incompatible with this module` then you need to use another version of Node.js. This script is supposed to work with Node.js >= 16.15.0.
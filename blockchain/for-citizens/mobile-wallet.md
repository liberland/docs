# Using mobile wallet with Liberland Blockchain

Liberland Blockchain supports using [SubWallet](https://www.subwallet.app/) for interacting with Liberland Blockchain and dApps. This guide will walk you through setting up the SubWallet app.

## Install SubWallet

[Install SubWallet](https://www.subwallet.app/download.html)

## Add account

Either [create a new account](https://docs.subwallet.app/main/mobile-app-user-guide/account-management/create-a-new-account-with-new-seed-phrase) or [import an existing one](https://docs.subwallet.app/main/mobile-app-user-guide/account-management/import-restore-an-account).

If you're importing an existing account for use on Liberland Blockchain, it must be an existing Polkadot account. 

## Get your wallet address

![Show address - 1](../media/subwallet/show-address.jpeg)

1. Tap the **Account** at the top (not the button)
2. Tap the **pencil icon**
3. Next to **Account Address**, click the copy icon (two pieces of paper)
4. Tap the `X` in the top-right corner to return to the app's home screen

## Use Liberland Wallet dApp

![Use dApp - 1](../media/subwallet/use-dapp-1.png)

1. Tap the **Browser** button in the bottom menu
2. In the **Search or enter website** field, input `https://blockchain.liberland.org/`
3. Confirm, and the page should load

    ![Use dApp - 2](../media/subwallet/use-dapp-2.png)
4. Tap the account you wish to connect to the dApp - the checkmark to the right should turn green
5. Tap **Connect**
6. You may now login to the dApp and complete the [Onboarding](onboarding.md).

## Add Liberland Network (Optional)

![Opening network settings guide - 1](../media/subwallet/add-network-1.png)

1. From the home screen, tap the menu icon in top-left corner
2. Tap **Manage Networks**
3. Tap **+** icon in the top-right corner

![Opening network settings guide - 2](../media/subwallet/add-network-2.png)

4. In the `Provider URL` field, enter `wss://mainnet.liberland.org` and confirm
   * use `wss://testchain.liberland.org` for Bastiat testnet
5. Once confirmed, the **Chain name**, **Symbol** and **Chain type** fields should fill automatically
6. Tap **Save**, and return to the home screen


# MetaMaskConnectWidget

## Overview

`MetaMaskConnectWidget` is a `StatefulWidget` that enables integration between a Flutter application and the MetaMask wallet via WalletConnect v2. It displays a QR code to establish the connection and fetches the user's Ethereum wallet address and native ETH balance using `webthree`.

---

## Features

- Establishes WalletConnect v2 session.
- Displays QR Code for MetaMask connection.
- Extracts wallet address from session data.
- Fetches ETH balance from Ethereum Mainnet.
- Uses Infura as RPC provider.
- Displays ETH balance with auto-refresh support.

---

## Dependencies

- `webthree` for Ethereum interaction.
- `http` for RPC communication.
- `qr_flutter` for QR code rendering.

---

## Key Components

### Variables

| Variable         | Type           | Description                                 |
|------------------|----------------|---------------------------------------------|
| `wcClient`       | `Web3App`      | WalletConnect V2 client instance            |
| `ethClient`      | `Web3Client`   | Ethereum client for on-chain queries        |
| `session`        | `SessionData?` | WalletConnect session data                  |
| `walletAddress`  | `String?`      | Connected wallet address                    |
| `nativeBalance`  | `BigInt?`      | ETH balance in wei                          |
| `connectionUri`  | `String?`      | URI shown in QR code for connection         |
| `rpcUrl`         | `String`       | RPC endpoint (Infura project URL required)  |

---

### Lifecycle

#### `initState()`
Initializes Ethereum client and starts WalletConnect session setup.

#### `initWalletConnect()`
- Instantiates `Web3App` with metadata.
- Sets up listeners for session connection.
- Initiates connection with Ethereum Mainnet via required namespaces.

#### `fetchBalance()`
- Queries ETH balance using the connected wallet address.
- Converts value from wei to ether using `EtherAmount`.

---

### UI Layout

The widget displays:

- QR Code to initiate WalletConnect connection (when not connected).
- Wallet address and balance (when connected).
- A button to manually refresh the ETH balance.

---

### Utility

#### `_formatEther(BigInt? wei): String`
Converts `wei` to `ether` and formats to 4 decimal places.

---

## Notes

- Replace `'YOUR_INFURA_PROJECT_ID'` and `'YOUR_WALLETCONNECT_PROJECT_ID'` with actual keys before using in production.
- Make sure MetaMask mobile app is used to scan the QR code for WalletConnect session initiation.

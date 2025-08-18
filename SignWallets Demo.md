
# For The Signers/Wallets Demo *seed phrase management

This demo shows the basics of managing Bitcoin wallets through seed phrases.
We walk through:

Creating a wallet and generating a seed phrase.

Backing up and restoring from the seed.

Removing a wallet and confirming funds are still recoverable.

The goal is to illustrate the three golden rules:

Bitcoin is money you hold yourself.

If you know your seed, you can always recover.

Even if a wallet is deleted, your Bitcoin is safe as long as you control the seed.

## 🛠 resources
- https://sparrowwallet.com/
- https://blockstream.com/jade/


# Signers / Wallets Demo – Seed Phrase Management

This demo walks through how Bitcoin wallets are created, restored, and secured using **seed phrases**.

⚠️ **Important:** Never share your real seed phrase. Always use demo seeds and test funds.

---

## Getting Started

### Tools Required
- **Jade Hardware Wallet** (Blockstream Jade or similar)
- **Sparrow Wallet** (desktop wallet: [sparrowwallet.com](https://sparrowwallet.com))
- **Blockstream Green** (mobile wallet: iOS/Android)

### Demo Setup
- Prepare a **testnet** or **regtest** environment with small amounts of bitcoin.  
- Have Jade initialized with a demo wallet holding test funds.  
- Install Sparrow on your laptop and Blockstream Green on your phone.  

---

## Roadmap

1. **Show funds on hardware (Jade)**
   - Power on **Jade** with a demo wallet containing a small bitcoin amount.
   - Display balance and a receive address.

2. **Create a software wallet in Sparrow**
   - Open **Sparrow Wallet** → *File → New Wallet*.
   - Select *Mnemonic Words (24)* → generate or enter a demo 24-word seed.
   - Let Sparrow derive accounts/addresses from the seed.

3. **(Optional) Send a small transaction**
   - Transfer a tiny amount between Jade and Sparrow to demonstrate sending and receiving.

4. **Explain the seed**
   - Show (conceptually) how a **24-word seed** creates keys and addresses.
   - Emphasize: *Seed → Keys → Addresses → Wallet*.

5. **Tour Sparrow’s power-user features**
   - Highlight: coin control, labels, xpub/descriptors export, watch-only mode, and PSBT flow.

6. **Use Blockstream Green (mobile)**
   - Open **Blockstream Green** → *Restore Wallet*.
   - Enter the same 24-word seed.
   - After sync, the **same balance** appears.

7. **Delete a wallet to prove funds aren’t on the device**
   - Remove the wallet in Sparrow and Blockstream Green.
   - Explain: coins stay on the blockchain — the **seed** is the key.

8. **Restore from the seed**
   - Re-create the Sparrow wallet using the same 24 words.
   - After sync/rescan, the **balance reappears**.

9. **Re-initialize Jade with a new seed**
   - Wipe Jade → create a **new seed** on the device.
   - Pair/import into Sparrow or Green.
   - Wait for sync — same process, same result.

10. **Recap – The 3 Golden Rules**
   1. Bitcoin is money **you hold**.  
   2. If you know your **seed**, you can always recover.  
   3. Deleting a wallet does not delete your bitcoin — the **seed** is what matters.

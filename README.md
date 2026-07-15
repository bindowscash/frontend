# Gotham.cash Frontend

> Official frontend interface for the bindows.cash on-chain mixer protocol.

---

## 🧩 About

Bindows.cash is a decentralized, non-custodial privacy protocol that enables anonymous transfers of assets across BSC. Inspired by the principles of Tornado Cash but simplified for practical use, it uses cryptographic commitments (SHA-256 + Keccak256) to unlink deposit and withdrawal actions.

- No upgradeability
- No self-destruct
- No pause/ownership
- Off-chain commitment generation
- 1% fee on withdrawal only, funding 50% of the $BINDOWS staking pool
- Fully client-side architecture

This frontend allows users to interact with fixed-amount mixer pools, generate deposit commitments off-chain, and withdraw funds using a signed proof to prevent frontrunning or theft.

---

## ⚙️ Tech Stack

- **React** – UI framework
- **Tailwind CSS** – Styling and dark mode support
- **Ethers.js** – Blockchain interaction
- **Vite** or **CRA** (depending on setup) – Build tool
- **Web3 Wallets** – MetaMask & compatible wallets
- **Static JSON-RPC Providers** – No backend API or provider services used

---

## 🚀 Deployment Guide

The frontend is fully static and can be deployed on any web host (GitHub Pages, Vercel, Namecheap, etc.).
This simplicity helps to enhance resilience and prevent censorship, builds trust and helps auditability.
Deploying your own front-end allows you to eliminate any third-party dependency and maximize anonymity (if run locally, your IP and Browser data are hidden).
Also, if for any reason the main bindows.cash domain is down or suspended, users can still access the mixer and use the pools.
Multiplying the mirrors reinforces the project's trustless & permissionless philosophy, making it fully decentralized.
⚠️ Always verify that the mirror you are using is up-to-date to the current version, as some people may deploy malicious versions to steal your funds. The official deployment on bindows.cash domain is the reference.

### 1. Clone the repository

```bash
git clone https://github.com/bindowscash/frontend.git
cd frontend
```

### 2. Install dependencies

```bash
npm install
```

### 3. Deploy

You can now upload the contents of build/ to your preferred host.
For example, using FTP:
- Upload the contents of build/ into your /public_html/ directory
- Ensure your domain points to this location
- Make sure .htaccess or routing configurations allow index.html to load correctly

For GitHub Pages (if enabled):

```bash
npm install --save-dev gh-pages
npm run deploy
```

Check the homepage field in your package.json and ensure it’s correctly set (e.g., "homepage": "https://username.github.io/repo").


---

## 📄 Contract Addresses

All pool contracts are deployed and hardcoded in the frontend.
Full address list available in /src/constants/addresses.js or in our contracts repository.

---

🛡️ Security Notes

- Users must generate their own secrets securely (ideally offline) - our front-end does it
- The signer of the withdrawal must match the one who created the original deposit commitment
- Commitment collisions are extremely unlikely (uses SHA-256 + Keccak)
- Frontrunning is mitigated through signature-based withdrawal authentication
- Contracts cannot be paused, upgraded, or disabled
- No administrative keys, ownership, or proxy patterns

---

📜 Disclaimer

Bindows.cash is a permissionless, privacy-focused protocol. It does not monitor or control user activity.
Even if your personal data are not stored (IP, notes, browser data, login times...), you are responsible of your own use of the dApp, make sure that you have a good OPSEC (VPN, TOR, proxies, delay between deposit/withdrawal...)

- Use at your own risk.
- You are solely responsible for complying with the laws of your jurisdiction.
- This software is provided as-is, without warranty of any kind. It is experimental.
- The secret note generated on deposit is the only key to withdraw your funds afterwards. If you lose it, your funds are lost forever in the contract. Don't trust anyone pretending that they can recover your funds. The developer will never ask you to share your secret notes, and he cannot recover funds from lost notes. So keep them in a safe place.

We do not provide custodial services, KYC, or compliance checks.

---

📫 Contact & Links

- Website: https://bindows.cash
- Docs: https://bindowscash.gitbook.io
- GitHub: https://github.com/bindowscash
- Telegram: https://t.me/bindowscash
- Twitter/X: https://x.com/bindowscash

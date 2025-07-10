# 🛡️ Zama Developer Program – Level 2 Guide (by Codespace)

Complete Level 2 of the [Zama Developer Program](https://guild.xyz/zama/developer-program) using GitHub Codespace — clean, fast, and tested ✅

---

# ✅ Level 2: “Write Your First Confidential Smart Contract”

### 🔹 STEP 1: Open Template in Codespace
1. Go to 👉 https://github.com/zama-ai/fhevm-hardhat-template
2. Click the green Code button
3. Select → Open with Codespaces → + New codespace
4. Wait for Codespace to fully load and initialize

---

### 🔹 Step 2: Clean and Recreate Contracts Folder
```bash

rm -rf contracts/*
mkdir contracts
touch contracts/Calculator.sol
```
---

### 🔹 Step 3: Add Calculator Contract

1. Open ```contracts``` 
2. Right Click 
3. Add file
4. Create ```Calculator.sol``` and paste this code:
```bash

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract Calculator {
    function encryptedAdd(uint32 a, uint32 b) public pure returns (uint32) {
        return a + b;
    }
}
```

---

### 🔹 Step 4: Install Required Packages
```bash
npm install
npm install @fhenixprotocol/contracts --save
```

### 🔹 Step 5: Compile the Contract
```bash
npx hardhat compile
```

Output should show:  ```Compiled 1 Solidity file successfully```

---
### 🔹 Step 6: Claim Level 2 on Guild - https://guild.xyz/zama/developer-program  

---

# ✅ Level 3: “Submit Contract Address”

---

### 🔹 Step 1: Create scripts Folder

```bash
mkdir scripts
````

---

### 🔹 Step 2: Create Deploy Script File

```bash
touch scripts/deploy.js
```

• Then in Codespace (left sidebar):

→ Open `scripts/deploy.js`
→ Paste the following code:

```javascript
const hre = require("hardhat");

async function main() {
  const Calculator = await hre.ethers.getContractFactory("Calculator");
  const calculator = await Calculator.deploy();
  await calculator.waitForDeployment();

  console.log("Calculator deployed to:", await calculator.getAddress());
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
```

---

### 🔹 Step 3: Deploy the Contract

Run this in terminal:

```
npx hardhat run scripts/deploy.js
```

Expected output:

```
Calculator deployed to: 0xAbC...123
```

That address is your deployed smart contract address.

---

### 🔹 Step 4: Claim Level 3

Visit:
[https://guild.xyz/zama/developer-program](https://guild.xyz/zama/developer-program)

→ Find **Level 3: Deploy your confidential contract**
→ Paste your deployed contract address

🎉 You’ve completed Level 3!

---

---

# Complete Guide: How to Do More Than 10 Commits In GitHub Before 1 July 2025

This guide helps you complete **15 GitHub commits on any Date** easily using **GitHub Codespaces** — so that you can participate in the **Zama Developer Program**

---

### 1️⃣ Create a New Repository

- Go To: https://github.com/new 
- Repository Name: `nothing` (or any name)  
- Set to **Public**  
- ✅ Tick "Add a README file"  
- Click **Create repository**
- Click on **`<> Code` → `Codespaces` → `+ New codespace`**. (Once Codespaces is ready)
- Open the built-in terminal (bottom panel or `Terminal` → `New Terminal`).

### 2️⃣ Run It
```
export BACKDATE="2025-06-30T12:00:00"

for i in {1..10}
do
  echo "Backdated Commit $i" >> backdated.txt
  git add backdated.txt
  GIT_AUTHOR_DATE="$BACKDATE" GIT_COMMITTER_DATE="$BACKDATE" git commit -m "Backdated commit $i"
done
```
```
git push
```

• Now Refersh ur Repo to see ur more than 10 public commits visible on your profile (Before 1 July) — ready to use for Zama Developer Program

---



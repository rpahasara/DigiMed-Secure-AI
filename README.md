# 🩺 DigiMed — A Privacy-Preserving Healthcare Blockchain System

We didn’t set out just to build another healthcare system. But we knew one thing for sure: patient data should never be the price of digital convenience.

We’re a team of four cybersecurity students passionate about blending blockchain, AI, and real-world impact. This is DigiMed: a secure, smart healthcare platform that protects sensitive information while delivering trust, speed, and usability. 💡🔐

---

## 🚀 What DigiMed Does (And Why It Matters)

- 🧠 **ZKPs (Zero-Knowledge Proofs)** verify blood pressure without revealing actual values.
- 🛡️ **Role-Based Access Control** keeps data flowing only where it should — Admins, Doctors, and Insurance Providers.
- 🔍 **Insurance Claim Verification** is now smart and secure, powered by proof, not exposure.
- 📊 **Dashboards for Everyone** — from user management to medical record submission and claim validation.

---

## 🧰 What You’ll Need

- 🖥️ Node.js v14+
- 🗃️ MongoDB v4.4+
- 🧪 Ganache (local blockchain testing)
- 🦊 MetaMask browser wallet
- 🧠 Circom (ZKP compiler)
- 🧾 Git

---

## ⚙️ Quickstart: Get It Running

1. **Clone the repo and install dependencies**
    ```bash
    git clone <repo_url>
    cd project_directory
    npm install
    cd backend && npm install
    cd ../frontend && npm install
    npm install -g circom
    ```

2. **Compile ZKP Circuit**
    ```bash
    cd circuits
    circom bloodPressureRange.circom --r1cs --wasm --sym
    ```

3. **Initialize Backend ZKP System**
    ```bash
    cd backend
    node scripts/setup-complete.js   # Generates ZKP keys and circuit
    node scripts/setup-roles.js      # Deploys contracts and roles
    ```

4. **Configure .env**
    - Add contract address and account roles from above scripts

5. **Ganache Setup**
    - Download + launch Ganache
    - Add these 3 accounts in MetaMask:
        1. 👨‍💼 Admin
        2. 👩‍⚕️ Doctor
        3. 🧑‍💼 Insurance Provider

6. **Run the System**
    ```bash
    # Start MongoDB
    # Backend
    cd backend && node server.js
    # Frontend
    npm start
    ```

---

## 👥 Roles & Permissions

| Role               | What They Can Do                          |
|--------------------|-------------------------------------------|
| Admin              | Manage users 🔐                           |
| Doctor             | Register patients, submit claims 📝       |
| Insurance Provider | Verify claims with ZKPs 🔎                |

🔑 **Note:** Order of accounts matters (from Ganache)!

---

## 🧪 How To Test

- **ZKP Test**
    ```bash
    cd backend && node scripts/test-zkp.js
    ```

- **Doctor Flow**
    - Log in as Doctor
    - Submit claims (try 130, 150 etc.)
    - Eligibility checks run via ZKP 💉

- **Insurance Flow**
    - Log in as Insurance Provider
    - Review and verify claims — no actual values leaked. Just trustless proof.

---

## ❗ Troubleshooting Tips

- 🦊 **MetaMask not connecting?**
    - Check Ganache, network config, account selection
- 🗃️ **MongoDB not found?**
    - Make sure it’s running + `.env` DB string is correct
- 🧠 **ZKP verification fails?**
    - Re-run setup scripts, check for circuit errors

---

## 🔐 Security Highlights

- ✅ ZKPs = No data leakage, only proof
- ✅ Role-based access = Least privilege
- ✅ JWT = Safe authentication
- ✅ Encrypted DB = Data at rest secured
- 🔐 Coming soon: **Two-Factor Auth**

---

This wasn’t just another academic submission; it was a blueprint for how modern secure systems should be built. We broke things. We fixed them. We figured it out together — one ZKP at a time. 💪👨‍💻👩‍💻

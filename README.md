
# 📱 Mobile Automation Team – Complete Setup Guide

This guide will walk you through setting up your local environment for working on the **Mobile Test Automation** project at Tandem.

---

## 🔗 Repository Access

**Clone this repo**:

```bash
git clone https://github.com/Tandem-Mobile/mobile-test-automation.git
```

### ✅ Organization Access

Make sure you're a member of:
- [`tandem-diabetes`](https://github.com/tandem-diabetes)
- [`tandem-mobile`](https://github.com/Tandem-Mobile)

If not, raise an **ITSD ticket** for access and reach out to your team for guidance.

---

## 🔐 Generate GitHub Personal Access Token

1. Go to **GitHub** → **Settings**
2. Navigate to:
   ```
   Developer Settings → Personal access tokens → Tokens (classic)
   ```
3. Click **Generate new token (classic)**

### ⚙️ Configuration:

- **Name**: Use a clear label
- **Expiration**: Select **No expiration**
- **Scopes** to check:

#### `repo`
- repo:status
- repo_deployment
- public_repo
- repo:invite
- security_events

#### `write:packages`
- read:packages

#### `user`
- read:user
- user:email
- user:follow

> 📌 Save the token securely — it's shown only once!

---

## 📝 Configure .npmrc

Open the `.npmrc` file in the root of the repo and **add this line**:

```ini
//npm.pkg.github.com/:_authToken=${NPM_TOKEN}
```

---

## 💻 Set Environment Token

In your terminal:

```bash
export NPM_TOKEN=<your-github-token>
```

> Do **not** include quotes.

---

## 🧱 Node.js Version Setup

Install and use the required version:

```bash
nvm install 16.20.2
nvm use 16.20.2
```

Then install dependencies:

```bash
npm install
```

> 🆘 If errors occur, contact your team.

---

## 🚀 Automaton JS Setup

### 1. Download Required ZIPs

Download both files from the following link:

🔗 [https://bamboo.tandemdiabetes.com/browse/AUT-AUTL-633/artifact/shared/automatonjs/](https://bamboo.tandemdiabetes.com/browse/AUT-AUTL-633/artifact/shared/automatonjs/)

- `automatonsjs.zip`
- `Bamboo_simulators_<...>_Linux.zip`

### 2. Linux Environment

If you're on **Windows**, ensure you have **WSL (Windows Subsystem for Linux)** enabled and follow setup steps in this README.

### 3. Node.js Version

Automaton JS requires:

```bash
nvm install 18.17.1
nvm use 18.17.1
```

### 4. Folder Structure

Unzip the files and ensure the simulator is placed under:

```
sd-sim/
├── gui
├── HelperFunctions
├── interface
└── simulators   ← Place simulator files here
```

### 5. Run the Project

```bash
node index.js
```

Open browser:

```
http://localhost:4000
```

---

## 📱 Android Studio Setup

### 1. Download

[Download Android Studio](https://developer.android.com/studio)

### 2. Setup Checklist

- [ ] Install Android Studio
- [ ] Create a sample project
- [ ] Use **Device Manager** to create and start an emulator
- [ ] Use **SDK Manager** to install:
  - Platform Tools
  - Emulator
  - Correct Android API version

### 3. Set Environment Variables

#### For macOS/Linux:
```bash
export ANDROID_HOME=<your-sdk-path>
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

#### For Windows (User Variables):
```
ANDROID_HOME = C:\Users\<YourName>\AppData\Local\Android\Sdk
```

System `PATH` additions:
```
%ANDROID_HOME%\tools
%ANDROID_HOME%\tools\bin
%ANDROID_HOME%\platform-tools
```

---

# ✅ Setup Checklists

### 🧪 Automaton JS Only

- [ ] Git installed
- [ ] Node.js v18.17.1 installed via NVM
- [ ] Automaton zip files downloaded
- [ ] Simulator placed in `sd-sim/simulators`
- [ ] `node index.js` executed
- [ ] Open `http://localhost:4000`

---

### 📱 Android Studio & Emulator Only

- [ ] Android Studio installed
- [ ] Sample project created
- [ ] Emulator created in Device Manager
- [ ] SDK components installed
- [ ] Environment variables set

---

### 🧰 Full Setup

If you're working with **both**, follow everything in:
- [Automaton JS Only](#-automaton-js-only)
- [Android Studio & Emulator Only](#-android-studio--emulator-only)

And additionally:
- [ ] Access to GitHub orgs
- [ ] GitHub PAT created
- [ ] `.npmrc` configured
- [ ] `NPM_TOKEN` set in terminal

---

Cheers,  
**Mobile Automation Team**

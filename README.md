
# 🚀  Automation Project: Environment Setup Guide

This guide walks you through setting up the local development environment for Tandem automation projects on **Windows, macOS, and Linux**.

---

## 🧰 Required Software

### 1. Git

**Install Git:**

- **Windows:** [https://git-scm.com/downloads](https://git-scm.com/downloads)
- **macOS:** Git is often pre-installed. If not, install via:
  ```bash
  brew install git
  ```
- **Linux (Debian/Ubuntu):**
  ```bash
  sudo apt update && sudo apt install git
  ```

**Verify Installation:**
```bash
git --version
```

---

### 2. Node Version Manager (NVM)

#### ➤ **Install NVM:**

- **Windows:**  
  [nvm-windows](https://github.com/coreybutler/nvm-windows/releases)

  > 🔁 Restart the system after installation.

- **macOS/Linux:**  
  Install using the official script:
  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
  source ~/.bashrc    # or ~/.zshrc
  ```

#### ✅ Use NVM:
```bash
nvm install <version>
nvm use <version>
node --version
```

---

### 3. Android Studio

**Download:**

- All OS: [https://developer.android.com/studio](https://developer.android.com/studio)

**Setup Steps:**
1. Install Android Studio.
2. Launch and create a **sample project** to verify.
3. Open **Device Manager** to create and run an **Android emulator**.
4. Use **SDK Manager** to install SDKs as required.

---

### 4. Appium

Install Appium globally using npm:
```bash
npm install --location=global appium
```

> May require `sudo` on macOS/Linux:
```bash
sudo npm install -g appium
```

---

### 5. Appium Inspector

**Download:**

- [Appium Inspector GitHub Releases](https://github.com/appium/appium-inspector/releases)

Install the appropriate binary for:
- Windows: `.exe`
- macOS: `.dmg`
- Linux: `.AppImage`

---

### 6. Visual Studio Code

**Download:**

- [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

**Recommended Extensions:**
- Appium
- ESLint
- Prettier
- JavaScript / TypeScript support

---

## ⚙️ Environment Variables Setup

### ➤ Android SDK Path (`ANDROID_HOME`)

| Platform | Suggested Value |
|----------|-----------------|
| **Windows** | `C:\Users\<YourName>\AppData\Local\Android\Sdk` |
| **macOS**   | `/Users/<YourName>/Library/Android/sdk` |
| **Linux**   | `/home/<YourName>/Android/Sdk` |

Set the following:

### **User or Shell Environment Variables:**

```bash
export ANDROID_HOME=<your-sdk-path>
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

For **macOS/Linux**, add this to your shell config (`~/.bashrc`, `~/.zshrc`, or `~/.bash_profile`).

For **Windows**, set environment variables via:
- **User Variables**:
  - `ANDROID_HOME = <sdk_path>`
  - `NVM_HOME = <nvm_path>`

- **System PATH** (append):
  ```
  %NVM_HOME%
  %NVM_SYMLINK%
  %ANDROID_HOME%\tools
  %ANDROID_HOME%\tools\bin
  %ANDROID_HOME%\platform-tools
  ```

Example full path:
```
C:\Users\<YourName>\AppData\Local\Android\Sdk\platform-tools
```

---

## ✅ Final Setup Checklist

- [ ] Git installed
- [ ] NVM installed and Node.js version configured
- [ ] Android Studio + SDK + Emulator setup
- [ ] Appium and Appium Inspector installed
- [ ] Environment variables configured
- [ ] VS Code with required extensions

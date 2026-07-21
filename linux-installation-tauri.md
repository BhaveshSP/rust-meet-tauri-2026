# Tauri Setup on Linux (Ubuntu/Debian)

This guide walks through installing everything required to develop **Tauri** applications on Ubuntu and Debian-based Linux distributions.

## System Requirements

- Ubuntu 22.04+ or another Debian-based distribution
- sudo privileges
- Internet connection

---

# 1. Install Rust

Rust is the programming language used to build the native backend of a Tauri application.

Install Rust:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Load Cargo into your current shell:

```bash
source "$HOME/.cargo/env"
```

Verify the installation:

```bash
rustc --version
cargo --version
```

Update Rust:

```bash
rustup update
```

---

# 2. Install Node.js (LTS)

Install Node.js using the official NodeSource repository.

```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt install -y nodejs
```

Verify the installation:

```bash
node --version
npm --version
```

---

# 3. Install System Dependencies

Install the packages required by Tauri:

```bash
sudo apt update

sudo apt install -y \
build-essential \
pkg-config \
libwebkit2gtk-4.1-dev \
libgtk-3-dev \
libayatana-appindicator3-dev \
librsvg2-dev
```

---

# 4. Install Visual Studio Code

Download Visual Studio Code:

https://code.visualstudio.com/

Or install it using Snap:

```bash
sudo snap install code --classic
```

Recommended extensions:

- Rust Analyzer
- Tauri
- Even Better TOML

---

# Verify Your Installation

Run the following commands:

```bash
rustc --version
cargo --version
node --version
npm --version
```

If each command prints a version number, your Linux environment is ready for Tauri development.

# 5. Create a New Tauri Project

Using npm:

```bash
npm create tauri-app@latest
```

Or using pnpm:

```bash
pnpm create tauri-app
```

Or using Yarn:

```bash
yarn create tauri-app
```

Follow the prompts to choose your preferred frontend framework and package manager.

---

# 6. Open the Project

Navigate to your project directory:

```bash
cd your-project
```

Open it in Visual Studio Code:

```bash
code .
```

Install project dependencies:

```bash
npm install
```

---

# 7. Run the Application

Start the development server:

```bash
npm run tauri dev
```

This launches both the frontend development server and the native desktop application.

---

# 8. Build a Release

Create an optimized production build:

```bash
npm run tauri build
```

The generated binaries can be found in:

```text
src-tauri/target/release/bundle/
```

---

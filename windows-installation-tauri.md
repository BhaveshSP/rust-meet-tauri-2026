# Tauri Setup on Windows

This guide walks through installing everything required to develop **Tauri** applications on Windows.

## System Requirements

- Windows 10 or Windows 11 (64-bit)
- Administrator access
- Internet connection

---

# 1. Install Rust

Rust is the programming language used to build the native backend of a Tauri application.

If Winget is unavailable, download the installer from:

https://rustup.rs/

After installation, restart your terminal.

Verify the installation:

```powershell
rustc --version
cargo --version
```

Update Rust to the latest version:

```powershell
rustup update
```

---

# 2. Install Node.js (LTS)

Node.js is required for the frontend development tools.

Install using Winget:

```powershell
winget install OpenJS.NodeJS.LTS
```

Or download it from:

https://nodejs.org/

Verify the installation:

```powershell
node --version
npm --version
```

---

# 3. Install Visual Studio Community

Tauri requires Microsoft's C++ compiler and the Windows SDK.

Download Visual Studio Community:

https://visualstudio.microsoft.com/vs/community/

During installation, select the following workload:

- **Desktop development with C++**

Ensure the following components are included:

- MSVC C++ Build Tools (latest)
- Windows 10 SDK or Windows 11 SDK
- C++ CMake tools for Windows

No additional workloads are required.

---

# Verify Your Installation

Run the following commands:

```powershell
rustc --version
cargo --version
node --version
npm --version
```

If each command prints a version number, your Windows environment is ready for Tauri development.

# 4. Install Visual Studio Code

Download Visual Studio Code:

https://code.visualstudio.com/

Recommended extensions:

- Rust Analyzer
- Tauri
- Even Better TOML

---

# 5. Create a New Tauri Project

Using pnpm (recommended):

```powershell
pnpm create tauri-app
```

Or using npm:

```powershell
npm create tauri-app@latest
```

Or using Yarn:

```powershell
yarn create tauri-app
```

Follow the prompts to choose your preferred frontend framework and package manager.

---

# 6. Open the Project

Navigate to your project directory:

```powershell
cd your-project
```

Open it in Visual Studio Code:

```powershell
code .
```

Install project dependencies:

```powershell
npm install
```

---

# 7. Run the Application

Start the development server:

```powershell
npm run tauri dev
```

This launches both the frontend development server and the native desktop application.

---

# 8. Build a Release

Create an optimized production build:

```powershell
npm run tauri build
```

The generated executable and installer can be found in:

```text
src-tauri/target/release/bundle/
```

---

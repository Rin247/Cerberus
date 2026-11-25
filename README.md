# Cerberus — Local Password & Secret Vault

Cerberus is an offline-first, zero-knowledge password manager, 2FA authenticator, and encrypted secret vault for Android. Built with Kotlin, Jetpack Compose, and native C++ Argon2id / AES-256-GCM cryptography, Cerberus keeps your credentials 100% private on your device with zero cloud dependency and zero network permissions.

---

## 🔑 Key Features & Subsystem Breakdown

### 🛡️ Encryption & Key Derivation (`vault-crypto`)
- **Current**: AES-256-GCM authenticated encryption at rest, Argon2id key derivation via NDK, hardware-backed Android KeyStore master key protection, and biometric unlock.
- **Planned / Roadmap**: YubiKey / FIDO2 hardware security key support, duress password wiping, and memory-clearing secure buffers.

### 🔑 Credentials & Autofill Framework (`autofill`)
- **Current**: Native Android Autofill Framework integration for seamless login filling in apps and browsers, password generator, and strength analyzer.
- **Planned / Roadmap**: Passkey (WebAuthn) passwordless credential manager, credit card & identity vault, and customizable breach detector (offline lookup).

### ⏳ 2FA Authenticator & TOTP (`totp`)
- **Current**: Built-in 2FA TOTP/HOTP code generator with 30-second progress ring, QR code scanner, and secret key import.
- **Planned / Roadmap**: Steam Guard and custom 2FA algorithm support, backup codes generator, and encrypted TOTP export.

### 🔄 Import & Export Engine (`importer`)
- **Current**: Password import from Bitwarden, KeePass (.kdbx), CSV, and Chrome exports; encrypted JSON backup export.
- **Planned / Roadmap**: WebDAV / local folder automatic encrypted backup sync, 1Password / LastPass import format parsers, and vault merger.

---

## 🏗️ Architecture & Technology Stack

- **Platform**: Android 13+ (minSdk 33, targetSdk 37).
- **UI & Autofill**: Kotlin, Jetpack Compose, Material 3, Android Autofill Service.
- **Crypto Engine**: Native C++ Argon2id (NDK) + Java Cryptography Architecture (JCA) AES-256-GCM.
- **Privacy Guarantee**: Zero `INTERNET` permission in `AndroidManifest.xml`.
- **Licensing**: AGPL-3.0.

---

## 🛠️ Building & Running

```bash
./gradlew assembleDebug
./gradlew installDebug
```

---

## 📜 License

Cerberus is released under the **GNU Affero General Public License v3.0** (AGPL-3.0). See [`LICENSE`](LICENSE) for details.

# AEGIS Web Privacy Vault

Standalone browser-based companion for the AEGIS project. It is independent of PEX, Cloudflare, and the native iOS repository.

## Features
- Browser Web Crypto API: PBKDF2-SHA-256 (310,000 iterations) derives an AES-256-GCM key.
- File bytes and file metadata (name, MIME type, size) are encrypted before being stored in IndexedDB.
- Encrypted JSON backup and restore.
- Manual lock, lock on page backgrounding, and five-minute timeout.
- Static offline shell through a service worker.

## Deploy
This repository is intended for GitHub Pages. The workflow in `.github/workflows/pages.yml` publishes the repository root. Use HTTPS; Web Crypto is unavailable on ordinary insecure origins.

## iPhone
Open the deployed HTTPS address in Safari. Use Share → Add to Home Screen if you want an app-like shortcut.

## Security limitations
- This is a personal-use browser tool, not an independently audited security product. It cannot protect against a compromised device, malicious browser extensions, keyloggers, or malicious code already running in the browser.
- Passwords are not stored. A forgotten password cannot be recovered.
- Clearing Safari website data may permanently delete the local IndexedDB vault. Keep encrypted backups in a separate safe location.
- Individual file export produces plaintext. Treat exported files as sensitive.
- The browser version does not provide the same security boundary as native iOS Keychain and Face ID.
- Public repository contains application source only. Never commit passwords, keys, personal files, or backups.

# 🔐 Text Encryptor & Decryptor

A lightweight browser-based text encryption and decryption tool built with vanilla JavaScript. It uses a **Vigenère cipher** to encrypt and decrypt messages using a user-provided key.

---

## 📸 Features

- Encrypt any message using a custom key
- Decrypt any previously encrypted message using the same key
- Supports a wide character set including letters, numbers, and special characters
- Runs entirely in the browser — no backend or server required

---

## 🚀 Getting Started

### 1. Clone or Download the Project

```bash
git clone https://github.com/your-username/text-encryptor.git
cd text-encryptor
```

Or simply download the files and open `index.html` in your browser.

### 2. Open in Browser

Just open `index.html` directly — no build tools or dependencies needed.

```bash
open index.html
```

---

## 📁 Project Structure

```
text-encryptor/
├── index.html       # Main HTML page with input fields and buttons
├── style.css        # Styling for the UI
└── script.js        # Core encryption/decryption logic
```

---

## 🧠 How It Works

This tool uses a **Vigenère cipher** — a classical key-based substitution cipher.

### The Alphabet (Character Set)

```
ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789.,?!'_-&@#$%*()/:<>|+= 
```

Every character in this set has a positional index (0–89). Only characters within this set are encrypted — anything outside it is passed through unchanged.

### Encryption

Each character in the message is shifted **forward** in the alphabet by the index of the corresponding key character.

```
newIndex = (messageCharIndex + keyCharIndex) % alphabetLength
```

### Decryption

Each character is shifted **backward** by the key character index — the exact reverse of encryption.

```
newIndex = (encryptedCharIndex - keyCharIndex + alphabetLength) % alphabetLength
```

### Key Looping

If the message is longer than the key, the key **repeats**. For example, a key of `"AB"` on a 6-character message uses `A B A B A B`.

---

## 🖥️ Usage

1. Type your **message** in the message input field
2. Enter a **key** (any string of characters from the supported alphabet)
3. Click **Encrypt** to encrypt your message
4. Click **Decrypt** to decrypt a previously encrypted message using the same key

> ⚠️ The same key must be used for both encryption and decryption. Using a different key will produce incorrect output.

---

## ✅ Supported Characters

| Category | Characters |
|---|---|
| Uppercase Letters | `A–Z` |
| Lowercase Letters | `a–z` |
| Digits | `0–9` |
| Punctuation & Symbols | `. , ? ! ' _ - & @ # $ % * ( ) / : < > \| + =` |
| Space | ` ` |

---

## ⚠️ Known Limitations

- Characters **outside** the supported alphabet are passed through without encryption
- The cipher is **symmetric** — the same key encrypts and decrypts
- This is a classical cipher and is **not suitable for real security or cryptographic purposes**
- Key length affects security — longer, more random keys are harder to crack

---

## 🛠️ Built With

- HTML
- CSS
- Vanilla JavaScript (no libraries or frameworks)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

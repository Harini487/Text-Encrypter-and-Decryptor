# 🔐 Text Encryptor & Decryptor

A lightweight browser-based text encryption and decryption tool built with vanilla JavaScript. It uses a **Vigenère cipher** to encrypt and decrypt messages using a user-provided key.

---

## 📸 Features

- Encrypt any message using a custom key
- Decrypt any previously encrypted message using the same key
- Supports a wide character set including letters, numbers, and special characters
- Runs entirely in the browser — no backend or server required

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

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

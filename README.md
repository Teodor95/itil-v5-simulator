# 🎓 ITIL® v5 Foundation — Secure Practice Portal

A lightweight, serverless, and highly secure web portal designed to help professionals train for the **ITIL® Foundation Version 5** certification. 

Built entirely with static HTML, CSS (Tailwind), and vanilla JavaScript, this portal can be hosted for free on **GitHub Pages** or **Cloudflare Pages** without needing a backend server—while keeping the entire question database cryptographically locked.

---

## ✨ Features

* ⏱️ **Exam Simulation Mode**: A 60-minute countdown timer with 40 randomized questions.
* 📚 **Full Practice Mode**: Access to the entire 77-question study pool.
* 💡 **Instant Feedback & Rationales**: Immediate correction with detailed study guide rationales for every question.
* 📊 **Final Recap**: End-of-session scoring and a filtered review of incorrect answers.
* 📱 **Fully Responsive**: Modern dark-mode UI optimized for desktop, tablet, and mobile browsers.

## 🔐 Zero-Backend Cryptographic Security

To prevent cheating by inspecting the source code, this portal uses a state-of-the-art **Web Crypto API** architecture:
* **Zero Plaintext Questions**: The `index.html` file contains no exam questions.
* **Per-User AES-256-GCM Encryption**: The 77 questions are stored inside `users.json`, encrypted individually for each user.
* **PBKDF2 Key Derivation**: Decryption keys are derived on the fly using `PBKDF2-HMAC-SHA256` (100,000 iterations) and a 128-bit random salt based on the user's personal password.
* **In-Memory Execution**: The database is decrypted directly into RAM upon a successful login. It is never saved to `localStorage` or `sessionStorage` and is wiped entirely on logout.

---

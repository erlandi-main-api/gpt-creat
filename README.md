# ChatGPT Account Creator

![Screenshot Tampilan Program](screenshot.png)

[🇷🇸 Bahasa Indonesia](#indonesian) | [🇬🇧 English](#english)

---

<a id="indonesian"></a>
## 🇮🇩 Bahasa Indonesia

Sebuah skrip otomatisasi berbasis Node.js yang menggunakan Playwright untuk membuat akun ChatGPT secara otomatis. Skrip ini secara mandiri menghasilkan email sementara, nama acak, tanggal lahir, dan menyelesaikan proses pendaftaran di ChatGPT, termasuk melakukan konfirmasi kode verifikasi otp.

### 🌟 Fitur Utama

- **Otomatisasi Penuh**: Mengisi seluruh form pendaftaran ChatGPT secara otomatis.
- **Email Sementara Acak**: Menggunakan API/scraping khusus dari `generator.email` untuk menghasilkan email dan mengambil kode OTP.
- **Bypass & Stealth**: Dilengkapi skrip *stealth* untuk Firefox guna menghindari deteksi webdriver/bot.
- **Data Acak (Faker)**: Menggunakan `@faker-js/faker` untuk penamaan akun yang realistis berdasarkan letak geografis atau acak.
- **Penyimpanan Praktis**: Semua akun yang sukses register otomatis terdata dengan rapi di dalam file `accounts.txt`.
- **Custom Config**: Mendukung pengaturan yang dapat disesuaikan `config.json` untuk *password* default, mode eksekusi (headless), dll.

### 📋 Persyaratan Sistem

Pastikan Anda sudah menginstal:
- **Node.js**: Versi 18.0.0 atau yang lebih baru.
- **NPM**: Biasanya sudah termasuk bersama instalasi Node.js.

### 🚀 Instalasi

1. Pastikan Anda berada di direktori proyek ini.
2. Buka terminal atau Command Prompt.
3. Instal semua paket/library NPM yang dibutuhkan dengan perintah:
   ```bash
   npm install
   ```
4. Instal *binary browser* Firefox untuk Playwright:
   ```bash
   npm run install-browsers
   ```
   *(Catatan: Anda juga bisa menjalankan secara manual `npx playwright install firefox`)*

### ⚙️ Konfigurasi (`config.json`)

Agar skrip dapat berjalan dengan baik, Anda wajib mengatur kata sandi (password). 
Jika `config.json` belum ada, jalankan skrip sekali agar file terbuat secara otomatis. Buka file tersebut dan atur konfigurasinya:

```json
{
  "max_workers": 3,
  "headless": false,
  "slow_mo": 1000,
  "timeout": 30000,
  "password": "MemeK92928338@"
}
```

* **`password`** (Wajib): Ganti dengan kata sandi yang ingin Anda tetapkan (OpenAI mewajibkan **minimal 12 karakter**).
* **`headless`**: Ubah ke `true` jika Anda tidak ingin memunculkan jendela browser saat proses instalasi berjalan (jalan di latar belakang).

### 💻 Cara Penggunaan

1. Buka terminal dan pastikan ada di dalam direktori proyek.
2. Jalankan skrip dengan mengetik:
   ```bash
   npm start
   ```
   *(Atau secara langsung: `node chatgpt_account_creator.js`)*
3. Anda akan ditanya perihal jumlah akun:
   ```text
   📝 How many accounts do you want to create?
   ```
4. Masukkan angka (misal: `5`) dan tekan `Enter`.
5. Skrip akan membuka Firefox (jika mode headless `false`) dan memulai pembuatan akun satu per satu secara berurutan.
6. Pantau prosesnya! Akun yang berhasil dibuat akan disimpan di `accounts.txt` dalam format `email|password`.

### ⚠️ Disclaimer (Perhatian)

1. **Penggunaan Bebersama** Skrip ini ditujukan murni untuk sekadar alat bantu pembelajaran (*automations web testing*). 
2. Membuat akun dalam jumlah besar secara terus-menerus bisa menyebabkan pemblokiran akses koneksi IP oleh provider situs (Cloudflare / OpenAI). 
3. Gunakan dengan tanggung jawab sendiri. Risiko pemblokiran akun berada di tangan pengguna.

---

<a id="english"></a>
## 🇬🇧 English

An automated Node.js script utilizing Playwright to automatically create ChatGPT accounts. This tool independently generates temporary emails, random names, and birthdays, completing the entire ChatGPT registration process including OTP verification.

### 🌟 Key Features

- **Full Automation**: Seamlessly fills out all ChatGPT registration forms.
- **Temporary Email Generation**: Leverages API/scraping from `generator.email` for email creation and OTP retrieval.
- **Bypass & Stealth**: Integrated Firefox stealth scripts to evade webdriver/bot detection mechanisms.
- **Randomized Data (Faker)**: Employs `@faker-js/faker` for generating realistic, geographically randomized user names.
- **Convenient Storage**: All successfully registered accounts are neatly logged in the `accounts.txt` file.
- **Custom Configuration**: Supports customizable settings via `config.json` for default passwords, execution mode (headless), and more.

### 📋 System Requirements

Ensure you have the following installed:
- **Node.js**: Version 18.0.0 or newer.
- **NPM**: Typically bundled with your Node.js installation.

### 🚀 Installation

1. Navigate to the project directory in your terminal or Command Prompt.
2. Install all required NPM dependencies using:
   ```bash
   npm install
   ```
4. Install the Firefox browser binary for Playwright:
   ```bash
   npm run install-browsers
   ```
   *(Note: You can also manually run `npx playwright install firefox`)*

### ⚙️ Configuration (`config.json`)

To run the script correctly, configuring a secure password is mandatory.
If `config.json` doesn't exist, run the script once to generate it. Open the file and adjust your settings:

```json
{
  "max_workers": 3,
  "headless": false,
  "slow_mo": 1000,
  "timeout": 30000,
  "password": "ChangeYourPassword123!"
}
```

* **`password`** (Required): Change this to your desired password (OpenAI mandates a **minimum of 12 characters**).
* **`headless`**: Change to `true` if you prefer the browser window not to appear during the creation process (runs silently in the background).

### 💻 Usage

1. Open your terminal and verify you are in the project directory.
2. Run the script by typing:
   ```bash
   npm start
   ```
   *(Alternatively: `node chatgpt_account_creator.js`)*
3. You will be prompted regarding the number of accounts you wish to create:
   ```text
   📝 How many accounts do you want to create?
   ```
4. Input your desired number (e.g., `5`) and press `Enter`.
5. The script will initialize Firefox (if headless mode is `false`) and sequentially process account creation.
6. Monitor the progress! Successfully created accounts are saved directly to `accounts.txt` in the `email|password` format.

### ⚠️ Disclaimer

1. **Educational Use Only** This script is intended purely as an educational tool for learning automation and web testing techniques.
2. Continually creating accounts on a massive scale may lead to IP access blockades by site providers (e.g., Cloudflare / OpenAI).
3. Use responsibly and at your own risk. The developer is not liable for any account suspensions or repercussions.

---

## 📜 License / Lisensi

Proyek ini menggunakan lisensi **MIT License**. Anda bebas menggunakan, memodifikasi, dan mendistribusikan kode ini, baik untuk tujuan komersial maupun non-komersial, dengan syarat mencantumkan pemberitahuan hak cipta asli dan penafian (disclaimer).

This project is licensed under the **MIT License**. You are free to use, modify, and distribute this code for both commercial and non-commercial purposes, provided you include the original copyright notice and disclaimer.

*Perangkat lunak ini disediakan "sebagaimana adanya", tanpa jaminan apa pun. / This software is provided "as is", without warranty of any kind.*

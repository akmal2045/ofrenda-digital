# Ofrenda Digital - Ghost in the Machine 🕯️🌼

> **Hacktoberfest 2026 · Week 4 DEV Challenge — Ghost in the Machine**
>
> Build something spooky, or something that honors the past in the spirit of Día de los Muertos, with open-weight models or open-source AI.

[![Hacktoberfest 2026](https://img.shields.io/badge/Hacktoberfest-2026-%23ff8c00?style=for-the-badge)](https://hacktoberfest.com)
[![DEV Challenge](https://img.shields.io/badge/DEV%20Challenge-%23hf26challenge-black?style=for-the-badge)](https://dev.to/challenges/hacktoberfest-week4-2026-10-26)
[![Gemma 2 2B](https://img.shields.io/badge/Model-Gemma%202%202B-blue?style=flat)](https://ai.google.dev/gemma)
[![Local First](https://img.shields.io/badge/Privacy-100%25%20Local-green?style=flat)](https://ollama.com)

**Live Demo:** https://akmal2045.github.io/ofrenda-digital/  
**Repository:** https://github.com/akmal2045/ofrenda-digital  
**DEV Post:** *Coming soon*

---

## 🕯️ About the Project

### Bukan horor. Ini altar kecil di laptopmu.

**Ofrenda Digital** adalah altar digital untuk mengenang orang-orang terkasih yang telah berpulang — Nenek Lia, Kakek, Ibu, Ayah, sahabat, atau siapa pun yang ingin tetap dikenang.

Terinspirasi dari tradisi **Día de los Muertos**, proyek ini membawa konsep *ofrenda* ke dalam konteks Indonesia dengan pendekatan **private, local-first, dan offline-capable**.

Tidak perlu akun. Tidak perlu mengunggah foto keluarga ke server. Tidak perlu internet untuk membuka altar.

> **Kenangan tetap milik keluarga.**

---

## ✨ Features

### 🖼️ Personal Memories
- Upload foto orang yang dikenang
- Foto hanya diproses dan disimpan secara lokal di browser
- Mendukung JPG, PNG, dan WebP
- Ukuran foto maksimal 5 MB
- Masukkan nama, hubungan, makanan favorit, lagu favorit, dan kenangan

### 🕯️ Digital Ofrenda
- Visual altar dengan lilin dan bunga marigold
- Menampilkan foto dan informasi kenangan secara personal
- Dirancang agar terasa hangat dan sederhana, bukan seperti aplikasi memorial yang formal

### 🤖 Local AI
- Generate teks kenangan menggunakan AI lokal
- **Gemma 2 2B** sebagai open-weight model
- **Ollama** digunakan untuk menjalankan model secara lokal
- Tidak membutuhkan API key atau layanan AI cloud

### 🔒 Privacy First
- Data disimpan menggunakan `localStorage`
- Foto tidak diunggah ke server
- Tidak membutuhkan login
- Dapat digunakan secara lokal tanpa backend

### ✅ Input Validation
- Field wajib tidak boleh kosong
- Nama minimal 3 karakter
- Kenangan minimal 10 karakter dan maksimal 200 karakter
- Validasi hubungan dengan nama
- Validasi tipe dan ukuran file foto
- Error ditampilkan langsung pada form dan melalui toast notification

---

## 👻 Ghost in the Machine

> **The ghost is the memory.  
> The machine is the laptop.**

Halloween dan Día de los Muertos sama-sama berbicara tentang hubungan manusia dengan masa lalu — tetapi Ofrenda Digital memilih sisi yang hangat daripada menakutkan.

Ofrenda tradisional biasanya berisi:

- 📷 Foto orang yang telah berpulang
- 🌼 Bunga marigold
- 🕯️ Lilin
- 🍲 Makanan favorit
- 💭 Kenangan dan cerita

Ofrenda Digital membawa elemen tersebut ke laptop.

Dengan begitu, sebuah altar tidak harus selalu berada di rumah. Ia dapat dibawa ke makam, dibuka kembali bertahun-tahun kemudian, dan tetap menyimpan cerita keluarga secara lokal.

---

# 💡 Why Open Innovation Matters

Penggunaan open-weight AI bukan sekadar pilihan teknologi. Untuk proyek seperti ini, **local AI memiliki nilai langsung terhadap privasi, aksesibilitas, dan keberlanjutan kenangan.**

### 1. 🔒 Private Family Memories

Foto dan cerita keluarga adalah data yang sangat personal.

Dengan AI berbasis cloud, data harus dikirim ke server pihak ketiga. Dengan **Gemma 2 2B + Ollama**, inference dapat dilakukan secara lokal.

> **Your family's memories stay on your machine.**

### 2. 📶 Works Without Internet

Banyak lokasi pemakaman di Indonesia memiliki koneksi internet yang buruk atau bahkan tidak memiliki sinyal.

Ofrenda Digital dirancang dengan pendekatan **local-first**, sehingga altar tetap dapat dibuka tanpa koneksi internet.

AI lokal juga dapat dijalankan menggunakan Ollama setelah model tersedia di perangkat.

### 3. 🧬 A Digital Heirloom

Layanan online dapat berubah, berhenti beroperasi, atau membutuhkan subscription.

File lokal dan open-weight model memberikan kontrol yang lebih besar kepada pengguna.

Sebuah altar yang dibuat hari ini dapat disimpan, dipindahkan, dan dibuka kembali bertahun-tahun kemudian.

> **A digital heirloom, not a subscription.**

### 4. 💰 No Per-Request AI Cost

Tidak ada biaya token untuk inference lokal.

Setelah model di-download, pengguna dapat menjalankan generation secara lokal tanpa membayar API request untuk setiap kenangan.

---

## 🛠️ Tech Stack

### 🤖 AI

| Technology | Purpose |
|---|---|
| **Gemma 2 2B** | Open-weight language model |
| **Ollama** | Local AI inference |

### 🌐 Frontend

| Technology | Purpose |
|---|---|
| **HTML** | Application structure |
| **CSS** | Styling and visual design |
| **Vanilla JavaScript** | Application logic |
| **FileReader API** | Local image preview |
| **localStorage** | Local persistence |

### 🚀 Deployment

- GitHub Pages
- No build process
- No Node.js required for the basic demo
- No backend required

---

## 🧠 AI Architecture

The application is designed to support local inference through Ollama:

```text
User Input
    │
    ├── Name
    ├── Relationship
    ├── Favorite Food
    ├── Favorite Song
    └── Memory
         │
         ▼
   Local Browser
         │
         ▼
      Ollama
         │
         ▼
    Gemma 2 2B
         │
         ▼
Generated Remembrance
         │
         ▼
    Digital Ofrenda
```

The current GitHub Pages demo uses a **local template/mock generation** so that the project can be demonstrated immediately without requiring an Ollama installation.

The actual Ollama integration is already prepared in `index.html` and can be enabled when running the project locally.

---

# 🚀 Getting Started

## Option 1 — Quick Demo

No installation is required.

```bash
git clone https://github.com/akmal2045/ofrenda-digital.git
cd ofrenda-digital
```

Then open:

```text
index.html
```

directly in your browser.

You can also try the deployed version:

**https://akmal2045.github.io/ofrenda-digital/**

---

## Option 2 — Local AI with Ollama

For actual local AI generation, install Ollama first.

### 1. Install Ollama

Download Ollama from:

**https://ollama.com**

### 2. Download Gemma 2 2B

```bash
ollama pull gemma2:2b
```

Then start the Ollama server:

```bash
ollama serve
```

The local API will be available at:

```text
http://localhost:11434
```

### 3. Enable the Local AI Integration

Inside `index.html`, locate:

```javascript
function nyalakanKenangan()
```

Replace the mock `remembrance` generation with:

```javascript
const response = await fetch(
  'http://localhost:11434/api/generate',
  {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      model: 'gemma2:2b',
      prompt: `Kamu adalah penulis kenangan yang hangat dan puitis.

Nama: ${data.nama}
Hubungan: ${data.hubungan}
Makanan favorit: ${data.makanan}
Lagu favorit: ${data.lagu}
Kenangan: ${data.kenangan}

Tulis teks ofrenda dalam Bahasa Indonesia.
Gunakan 3 paragraf pendek dengan nada hangat,
personal, dan penuh penghormatan.`,
      stream: false
    })
  }
);

const result = await response.json();
const remembrance = result.response;
```

---

# ✅ Validation

The application includes client-side validation for the main input fields.

| Validation | Status |
|---|---|
| Required fields | ✅ |
| Name minimum length | ✅ |
| Memory minimum length | ✅ |
| Memory maximum length | ✅ |
| Relationship consistency | ✅ |
| JPG / PNG / WebP validation | ✅ |
| Maximum file size: 5 MB | ✅ |
| Inline error messages | ✅ |
| Toast notification | ✅ |
| Auto-focus on invalid field | ✅ |

### Example

The application prevents inconsistent relationships such as:

```text
Name: Kakek Anwar
Relationship: Nenek
```

and asks the user to correct the input.

---

# 📂 Project Structure

The project intentionally keeps its architecture simple so it can run without a build system.

```text
ofrenda-digital/
│
├── index.html
└── README.md
```

Everything required for the basic application is contained in `index.html`.

---

# 🏆 Hacktoberfest Submission

### DEV Challenge — Ghost in the Machine

- [x] Honors the past
- [x] Inspired by Día de los Muertos
- [x] Uses open-weight AI
- [x] Gemma 2 2B integration prepared
- [x] Local-first architecture
- [x] Offline-capable
- [x] Privacy-focused
- [x] Public GitHub repository
- [x] Live demo available
- [x] Write-up explains open vs. closed AI
- [x] `#devchallenge`
- [x] `#hf26challenge`

### Prize Category

**Best Use of Gemma**

Gemma 2 2B is used as the local language model for generating personalized remembrance text.

---

# 📜 License

This project is licensed under the **MIT License**.

You are free to use, modify, and build upon it.

---

# 🙏 For Nenek Lia

> *Tak pernah padam.*

Bukan horor.

Ini altar kecil di laptopku — untuk **Nenek Lia**, yang suka rendang, klepon, kopi tubruk, dan lagu *Bengawan Solo*.

Dibuat dengan cinta untuk **Hacktoberfest 2026 — Week 4: Ghost in the Machine**.

---

**Submission deadline:** Sunday, November 1, 2026 · 1:59 PM WIB (Asia/Jakarta)

**Live Demo:** https://akmal2045.github.io/ofrenda-digital/  
**Repository:** https://github.com/akmal2045/ofrenda-digital

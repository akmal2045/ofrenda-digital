# Ofrenda Digital - Ghost in the Machine 🕯️🌼

> **Hacktoberfest 2026 - Week 4 DEV Challenge: Ghost in the Machine**
> Build something spooky, or something that honors the past in the spirit of Día de los Muertos, with open-weight models or open-source AI.

[[Hacktoberfest](https://img.shields.io/badge/Hacktoberfest-2026-%23ff8c00?style=for-the-badge)](https://hacktoberfest.com)
[[DEV Challenge](https://img.shields.io/badge/DEV%20Challenge-%23hf26challenge-black?style=for-the-badge)](https://dev.to/challenges/hacktoberfest-week4-2026-10-26)
[[Open Weight](https://img.shields.io/badge/Model-Gemma%202%202B-blue?style=flat)](https://ai.google.dev/gemma)
[[Local First](https://img.shields.io/badge/Privacy-100%25%20Local-green?style=flat)](https://ollama.com)

**Live Demo:** [ofrenda-digital.tech](https://ofrenda-digital.tech) | **DEV Post:** [Link to your DEV post]

### Bukan horor. Ini altar kecil di laptopmu.

Ofrenda Digital adalah altar digital untuk mengenang Nenek Lia, Kakek, Ibu, Ayah, sahabat yang sudah berpulang. Offline, privat, bisa dibawa ke makam tanpa sinyal.

Inspired by Día de los Muertos ofrenda tradition, but built with Indonesian context - for those who want to keep family stories private and alive.

---

### ✨ Demo

[Ofrenda Preview](./screenshot.png)
*Isi form di kiri, lihat altar menyala di kanan*

**Fitur:**
- Upload foto almarhum (preview lokal, tidak pernah di-upload)
- Input: Nama, Hubungan, Makanan Favorit, Lagu Favorit, Satu Kenangan
- Generate teks kenangan dengan AI lokal
- Visual ofrenda dengan lilin dan bunga marigold
- 100% disimpan di localStorage browser
- Multiple ofrenda bisa disimpan

---

### 👻 Interpretasi Tema: Ghost in the Machine

Halloween dan Día de los Muertos adalah momen dimana batas antara masa lalu dan sekarang menipis. Aku memilih sisi yang menghangatkan - bukan menakutkan.

Ofrenda biasanya fisik: foto, marigold, lilin, makanan favorit. Ofrenda Digital membuatnya bisa dibawa kemana-mana, bahkan ke makam yang tidak ada sinyal.

Ghost-nya adalah kenangan. Machine-nya adalah laptop tua yang tetap bisa menjalankan AI tanpa internet.

---

### 💡 Why Open Innovation Matters

Ini bagian paling penting untuk juri.

**1. Privasi Keluarga Tetap di Rumah**
Foto Nenek Lia dan cerita keluarga tidak pernah keluar dari laptop. Dengan model closed-source API, semua data harus dikirim ke server orang lain. Dengan Gemma 2B via Ollama, inference jalan 100% lokal. Tidak ada yang bisa melihat ofrenda keluargaku kecuali aku.

**2. Jalan Tanpa Internet (dan Listrik Stabil)**
Di banyak makam di Indonesia, sinyal hilang. Layanan AI closed butuh internet. Ofrenda Digital jalan dengan `ollama serve` offline. Bisa dibuka di laptop saat nyekar, bahkan saat lampu mati dengan baterai laptop.

**3. Tidak Terkunci, Bisa Diwariskan**
Layanan startup bisa tutup besok. Model open-weight bisa di-download dan disimpan selamanya. Ofrenda yang aku buat untuk Nenek Lia hari ini, bisa dibuka lagi 20 tahun lagi oleh cucuku, dengan model yang sama. Ini digital heirloom, bukan subscription.

**4. Biaya Nol untuk Kenangan**
Tidak ada token cost. Sekali download Gemma 2B (~1.6GB), bisa generate ribuan kenangan gratis. Penting untuk keluarga yang tidak punya budget untuk API.

> Open innovation worked better than closed because it let me build something intimate that respects privacy, works offline, and lasts longer than any company.

---

### 🛠️ Tech Stack

**Open-Source AI Core:**
- **Gemma 2 2B** by Google - Open-weight model, 2B params, optimized for local
- **Ollama** - Run inference locally, no API key needed
- **Prompt:** `Tulis kenangan hangat untuk Nenek Lia...` (Indonesian native)

**Frontend:**
- React + Tailwind CSS (Vite)
- localStorage for persistence
- FileReader API for local photo preview

**Optional Partner Tech for Prize Categories:**
- **Best Use of Gemma** - Core model
- **Best Use of a .tech Domain** - Deployed at ofrenda-digital.tech
- **Best Use of Render** - Hosting frontend

---

### 🚀 Cara Menjalankan Lokal

#### 1. Install Ollama
Download di https://ollama.com

#### 2. Pull Gemma 2B
```bash
ollama pull gemma2:2b
ollama serve
# Model akan jalan di http://localhost:11434
```

#### 3. Jalankan App
```bash
git clone https://github.com/username/ofrenda-digital
cd ofrenda-digital
npm install
npm run dev
```

#### 4. Integrasi Real Model (ganti mock)
Di `src/utils/generate.js`:
```javascript
// Ganti fungsi mock dengan ini:
const response = await fetch('http://localhost:11434/api/generate', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    model: 'gemma2:2b',
    prompt: `Kamu adalah penulis kenangan. Tulis ofrenda text untuk Nenek Lia.
    Nama: ${data.nama}
    Hubungan: ${data.hubungan}
    Makanan: ${data.makanan}
    Lagu: ${data.lagu}
    Kenangan: ${data.kenangan}
    Tulis dalam Bahasa Indonesia yang hangat dan puitis, 3 paragraf.`,
    stream: false
  })
})
const result = await response.json()
return result.response
```

---

### 📖 Submission Checklist (DEV Challenge)

- [x] Built with open-weight model (Gemma 2B)
- [x] Runs locally / offline capable
- [x] Theme: Ghost in the Machine + honors past
- [x] Write-up explains why open > closed
- [x] Demo link + GitHub link
- [x] Tags: #devchallenge #hf26challenge
- [x] Prize Categories listed in post: Best Use of Gemma, Best Use of a .tech Domain

---

### 📜 License

MIT - Bebas dipakai untuk mengenang siapa saja.

---

### 🙏 Untuk Nenek Lia

> Tak pernah padam. Bukan horor. Ini altar kecil di laptopku - untuk Nenek Lia yang suka rendang, klepon, kopi tubruk, dan lagu Bengawan Solo.

Dibuat dengan cinta untuk Hacktoberfest 2026 Week 4 - Ghost in the Machine.
Submission closes: Sun 1 Nov, 1:59 PM WIB (Asia/Jakarta)


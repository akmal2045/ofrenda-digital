# Ofrenda Digital - Ghost in the Machine 🕯️🌼

> **Hacktoberfest 2026 - Week 4 DEV Challenge: Ghost in the Machine**
> Build something spooky, or something that honors the past in the spirit of Día de los Muertos, with open-weight models or open-source AI.

[[Hacktoberfest](https://img.shields.io/badge/Hacktoberfest-2026-%23ff8c00?style=for-the-badge)](https://hacktoberfest.com)
[[DEV Challenge](https://img.shields.io/badge/DEV%20Challenge-%23hf26challenge-black?style=for-the-badge)](https://dev.to/challenges/hacktoberfest-week4-2026-10-26)
[[Open Weight](https://img.shields.io/badge/Model-Gemma%202%202B-blue?style=flat)](https://ai.google.dev/gemma)
[[Local First](https://img.shields.io/badge/Privacy-100%25%20Local-green?style=flat)](https://ollama.com)

**Live Demo:** https://akmal2045.github.io/ofrenda-digital/ | **DEV Post:** *(isi setelah publish di dev.to)* | **Repo:** https://github.com/akmal2045/ofrenda-digital

### Bukan horor. Ini altar kecil di laptopmu.

Ofrenda Digital adalah altar digital untuk mengenang Nenek Lia, Kakek, Ibu, Ayah, dan sahabat yang sudah berpulang. Offline, privat, bisa dibuka di makam tanpa sinyal.

Inspired by Día de los Muertos ofrenda tradition, but built with Indonesian context — for families who want to keep stories private and alive.

---

### ✨ Demo

*Isi form di kiri, lihat altar menyala di kanan — dengan validasi lengkap*

**Fitur:**
- ✅ Upload foto almarhum (preview lokal, tidak pernah di-upload ke server, max 5MB, JPG/PNG/WebP)
- ✅ Validasi wajib isi: Nama (min 3 karakter), Hubungan, Kenangan (min 10 karakter)
- ✅ Validasi tidak sesuai: Nama `Kakek Anwar` tidak bisa dipasangkan dengan Hubungan `Nenek`
- ✅ Input: Nama, Hubungan, Makanan Favorit, Lagu Favorit, Satu Kenangan
- ✅ Generate teks kenangan dengan AI lokal (mock + siap pakai Ollama)
- ✅ Visual ofrenda dengan lilin dan bunga marigold
- ✅ 100% disimpan di localStorage browser, offline-first

---

### 👻 Interpretasi Tema: Ghost in the Machine

Halloween dan Día de los Muertos adalah momen dimana batas antara masa lalu dan sekarang menipis. Aku memilih sisi yang menghangatkan — bukan menakutkan.

Ofrenda biasanya fisik: foto, marigold, lilin, makanan favorit. Ofrenda Digital membuatnya bisa dibawa kemana-mana, bahkan ke makam yang tidak ada sinyal.

Ghost-nya adalah kenangan. Machine-nya adalah laptop tua yang tetap bisa menjalankan AI tanpa internet.

---

### 💡 Why Open Innovation Matters

Ini bagian paling penting untuk juri DEV.

**1. Privasi Keluarga Tetap di Rumah**
Foto Nenek Lia dan cerita keluarga tidak pernah keluar dari laptop. Dengan model closed-source API, semua data harus dikirim ke server orang lain. Dengan Gemma 2B via Ollama, inference jalan 100% lokal.

**2. Jalan Tanpa Internet**
Di banyak makam di Indonesia, sinyal hilang. Layanan AI closed butuh internet. Ofrenda Digital jalan dengan `ollama serve` offline. Bisa dibuka saat nyekar, bahkan saat lampu mati dengan baterai laptop.

**3. Tidak Terkunci, Bisa Diwariskan**
Layanan startup bisa tutup besok. Model open-weight bisa di-download dan disimpan selamanya. Ofrenda untuk Nenek Lia hari ini bisa dibuka lagi 20 tahun lagi oleh cucuku. Ini digital heirloom, bukan subscription.

**4. Biaya Nol untuk Kenangan**
Tidak ada token cost. Sekali download Gemma 2B (~1.6GB), bisa generate ribuan kenangan gratis.

> Open innovation worked better than closed because it let me build something intimate that respects privacy, works offline, and lasts longer than any company.

---

### 🛠️ Tech Stack

**Open-Source AI Core (Siap Integrasi):**
- **Gemma 2 2B** by Google — Open-weight model, 2B params, optimized for local
- **Ollama** — Run inference locally di `http://localhost:11434`, no API key

**Frontend (Saat Ini - No Build):**
- Vanilla HTML + CSS + JavaScript (single `index.html`, tanpa `npm`)
- FileReader API untuk preview foto lokal
- localStorage untuk persistence
- Validasi form client-side (required, min length, cross-field validation)

> Catatan juri: Versi saat ini pakai template generator agar bisa langsung demo di GitHub Pages tanpa backend. Kode integrasi Ollama asli sudah ada di dalam file dan siap di-uncomment.

**Partner Tech untuk Prize Categories:**
- **Best Use of Gemma** — Core model
- **Best Use of a .tech Domain** — Bisa diklaim di hacktoberfest.com/my/promos

---

### 🚀 Cara Menjalankan Lokal

#### Opsi 1: Paling Cepat (Tanpa Install)
```bash
# Cukup double-click index.html atau:
git clone https://github.com/akmal2045/ofrenda-digital.git
cd ofrenda-digital
# buka index.html di browser
```

#### Opsi 2: Dengan Ollama + Gemma (AI Beneran)

**1. Install Ollama**
Download di https://ollama.com

**2. Pull Gemma 2B**
```bash
ollama pull gemma2:2b
ollama serve
# Model jalan di http://localhost:11434
```

**3. Aktifkan Real Model di index.html**
Cari fungsi `nyalakanKenangan()` dan ganti bagian `const remembrance = ...` dengan:

```javascript
const response = await fetch('http://localhost:11434/api/generate', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    model: 'gemma2:2b',
    prompt: `Kamu adalah penulis kenangan hangat. Tulis teks ofrenda untuk:
    Nama: ${data.nama}
    Hubungan: ${data.hubungan}
    Makanan favorit: ${data.makanan}
    Lagu favorit: ${data.lagu}
    Kenangan: ${data.kenangan}
    Tulis dalam Bahasa Indonesia yang hangat dan puitis, 3 paragraf pendek.`,
    stream: false
  })
});
const result = await response.json();
const remembrance = result.response;
```

---

### ✅ Validasi yang Sudah Ada

Projek ini sudah divalidasi sesuai feedback:
- [x] Field kosong dicegah (Nama, Hubungan, Kenangan wajib)
- [x] Format tidak sesuai dicegah (Nama min 3, Kenangan min 10 max 200)
- [x] Cross-validation: Kakek vs Nenek mismatch
- [x] Foto: tipe JPG/PNG/WebP dan max 5MB
- [x] Pesan error merah + toast + auto-focus ke field pertama yang salah

---

### 📖 Submission Checklist (DEV Challenge)

- [x] Built with open-weight model (Gemma 2B - ready)
- [x] Runs locally / offline capable
- [x] Theme: Ghost in the Machine + honors past (Nenek Lia)
- [x] Write-up explains why open > closed
- [x] Demo link: https://akmal2045.github.io/ofrenda-digital/
- [x] GitHub link: https://github.com/akmal2045/ofrenda-digital
- [x] Tags: #devchallenge #hf26challenge
- [x] Prize Categories: Best Use of Gemma

---

### 📜 License

MIT - Bebas dipakai untuk mengenang siapa saja.

---

### 🙏 Untuk Nenek Lia

> Tak pernah padam. Bukan horor. Ini altar kecil di laptopku — untuk Nenek Lia yang suka rendang, klepon, kopi tubruk, dan lagu Bengawan Solo.

Dibuat dengan cinta untuk Hacktoberfest 2026 Week 4 - Ghost in the Machine.  
Submission closes: Sun 1 Nov, 1:59 PM WIB (Asia/Jakarta)

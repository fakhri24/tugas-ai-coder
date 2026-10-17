# Panduan Tugas Ekskul AI Coder: Membangun Game 2D Arcade dengan Hermes Agent

Repositori ini berisi materi penugasan mandiri terstruktur untuk siswa ekskul **AI Coder**. Dirancang khusus agar siswa dapat belajar dan berpraktik secara mandiri tanpa kehadiran guru (*autonomous self-directed learning*).

---

## 📂 Struktur Berkas
- **`index.html`**: Slide web presentasi interaktif 10 slide mandiri (Tailwind CSS, Zero-Cache, navigasi keyboard/sentuh, tombol salin instan, lightbox zoom gambar, dan siap cetak ke PDF).
- **`AGENTS.md`**: Berkas aturan sistem (*System Rulebook*) yang wajib disalin siswa ke folder proyek lokal mereka agar dipatuhi oleh **Hermes Agent**.
- **`assets/`**: Berkas visual pendukung (tangkapan layar portal, situs unduh, dan panduan pemilihan model Step 5 Preview).

---

## 🚀 Cara Menjalankan Slide Presentasi

### 1. Membuka di Browser
Cukup klik ganda pada berkas **`index.html`** untuk membukanya di Google Chrome, Microsoft Edge, atau Safari.

### 2. Fitur Interaktif pada Slide
- **Navigasi Keyboard**:
  - `[ → ]` atau `[ Spasi ]`: Menuju slide berikutnya.
  - `[ ← ]`: Kembali ke slide sebelumnya.
  - `[ F ]`: Mengaktifkan / menonaktifkan mode layar penuh (*Fullscreen*).
  - `[ Home ]` / `[ End ]`: Langsung ke slide pertama / terakhir.
  - `[ Esc ]`: Menutup pratinjau gambar zoom (lightbox) atau menu daftar slide.
- **Tombol Salin Instan**:
  - Salin perintah instalasi Windows & macOS.
  - Salin seluruh isi berkas `AGENTS.md` dengan satu klik.
  - Salin template prompt instruksi ke Hermes Agent.
- **Zoom Tangkapan Layar**: Klik gambar tangkapan layar mana pun untuk memperbesar (*high-definition lightbox*).
- **Ekspor / Cetak ke PDF**: Tekan tombol **🖨️ Cetak PDF** di bilah atas atau tekan `Ctrl + P` (Windows) / `Cmd + P` (Mac). Tampilan telah dioptimalkan khusus cetak menjadi dokumen panduan handout.

---

## 🎮 Batasan Game yang Dibangun Siswa
1. **Teknologi**: Pure Vanilla HTML5, CSS3, dan JavaScript (Zero-Build / tanpa bundler).
2. **Penyimpanan Rekor**: Wajib menggunakan browser `localStorage` agar High Score tetap tersimpan saat halaman dimuat ulang.
3. **State Mesin Game**: Layar Awal (Start Screen) -> Area Main (HUD skor aktif) -> Layar Game Over (dengan tombol Main Lagi).
4. **Efek Suara Mandiri**: Synthesizer frekuensi audio bawaan via Web Audio API (`window.AudioContext`), dilengkapi tombol toggle Mute/Unmute.
5. **Model AI**: Model `Step 5 Preview:Free` dengan *Effort* `High` pada aplikasi **Hermes Desktop**.

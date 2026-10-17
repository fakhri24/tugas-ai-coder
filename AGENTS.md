# PANDUAN PENGEMBANGAN GAME ARCADIA (AGENTS.md)
> Dokumen aturan baku untuk AI Agent (Hermes Agent). AI Agent WAJIB membaca dan mematuhi seluruh batasan teknis di bawah ini saat menyusun atau memodifikasi kode game.

---

## 1. Standar Arsitektur & Teknologi
- **Bahasa**: Pure Vanilla Web (**HTML5**, **CSS3**, dan **JavaScript ES6+** murni).
- **Portabilitas & Kompatibilitas GitHub Pages**:
  - Wajib berjalan mandiri (*zero-build*).
  - Gunakan *relative path* (`./style.css`, `./game.js`) agar game dapat langsung dimainkan secara lokal (`file://`) maupun setelah di-hosting di **GitHub Pages** (`https://<username>.github.io/<repo>/`).
- **Struktur Berkas Proyek**:
  ```text
  game-arcade-ai/
  ├── AGENTS.md        # Panduan aturan sistem untuk agen AI (berkas ini)
  ├── index.html       # Struktur antarmuka (Start screen, Canvas HUD, Game Over modal)
  ├── style.css        # Desain visual arcade retro-modern yang rapi dan responsif
  └── game.js          # Seluruh logika permainan, loop animasi, audio synth, dan skor
  ```

---

## 2. Fitur Wajib (Core Requirements)

### A. Penyimpanan Skor Tertinggi (LocalStorage High Score)
1. Gunakan API browser `localStorage` untuk menyimpan dan membaca nilai rekor tertinggi siswa.
2. Tampilkan nilai rekor tertinggi (*High Score*) di Layar Awal dan HUD saat bermain.
3. Saat permainan berakhir (*Game Over*):
   - Jika skor saat ini melebihi rekor sebelumnya, simpan skor baru ke `localStorage`.
   - Munculkan efek visual atau lencana *"NEW HIGH SCORE!"*.
4. Pastikan rekor tetap tersimpan utuh meskipun halaman browser di-refresh atau ditutup.

### B. Alur Siklus Permainan (Game State Machine)
Game wajib memiliki transisi 3 kondisi layar yang jelas dan tidak bertumpuk:
1. **Layar Awal (Start Screen)**:
   - Judul game yang menarik dan tema visual yang konsisten.
   - Nilai High Score saat ini.
   - Ringkasan kontrol tombol (Keyboard: Panah / WASD / Spasi).
   - Tombol interaktif **"Mulai Main"** (*Play Game*).
2. **Layar Bermain (Active Game Play)**:
   - Area permainan utama (Canvas 2D atau Grid DOM animasi) yang mulus (target 60 FPS).
   - HUD di bagian atas: Skor Berjalan (*Current Score*), Rekor (*High Score*), Level / Kecepatan / Nyawa.
   - Tombol jeda (*Pause*) atau kontrol suara (*Mute/Unmute*).
3. **Layar Akhir (Game Over Screen)**:
   - Menampilkan skor akhir yang diperoleh pemain.
   - Menampilkan perbandingan dengan rekor tertinggi.
   - Tombol **"Main Lagi"** (*Restart / Play Again*) yang langsung mengulang permainan tanpa perlu refresh halaman.

### C. Efek Suara Mandiri (Web Audio API Synthesizer)
- **DILARANG** mengimpor berkas audio eksternal (`.mp3`, `.wav`) yang berpotensi gagal muat (*404 Not Found*).
- **WAJIB** membuat synthesizer nada sederhana menggunakan native browser `window.AudioContext` (gelombang sinus/persegi/segitiga):
  - Suara aksi (lompat / tangkap item / bergerak).
  - Suara keberhasilan (dapat poin / naik level).
  - Suara tabrakan / game over.
- Sediakan tombol **Mute / Unmute** di sudut antarmuka agar suara dapat diaktifkan atau dimatikan oleh pemain.

### D. Kontrol & Responsivitas Tampilan
- Kontrol keyboard utama: Tombol Panah (Arrow Keys), Spasi (Space), dan WASD.
- Berikan tombol virtual di layar (D-Pad / Tombol aksi) opsional agar permainan tetap dapat dikendalikan dengan kursor mouse atau sentuhan layar sentuh.
- Game harus terpusat (*centered layout*), tidak menimbulkan *scroll bar* yang mengganggu saat tombol panah ditekan (`event.preventDefault()` pada tombol game).

---

## 3. Batasan Kreativitas Siswa
- Siswa bebas menentukan gameplay 2D Arcade (contoh: Petualangan Ular Klasik, Menghindari Meteor Luar Angkasa, Menangkap Buah Jatuh, Lompat Rintangan Flappy, atau Balap Mobil Retro).
- Segala penambahan fitur unik (misal: power-up, penggantian warna tema karakter, atau tingkat kesulitan dinamis) sangat dianjurkan selama tetap mematuhi batasan teknis di atas.

# Kalkulator Transformasi Lauf 2D

Kalkulator web (single-file, HTML + CSS + JS murni, tanpa dependensi build) untuk
menyelesaikan Tugas Transformasi Konform Non-Linier 2D (Lauf) — menghitung 6 parameter
transformasi, ketelitian parameter, RMS titik sekutu, dan koordinat baru titik 7–10,
berdasarkan data resmi `Tabel.png` (Slide 18) dan variabel NIM (XX, YY).

Semua perhitungan (pembentukan matriks desain A, matriks normal AᵀA, invers Gauss–Jordan,
parameter, residu, RMS) berjalan langsung di peramban — tidak butuh server atau backend.

## Menjalankan secara lokal

Buka `index.html` langsung di peramban (klik dua kali), atau jalankan server statis
sederhana:

```bash
python3 -m http.server 8000
# lalu buka http://localhost:8000
```

## Deploy ke GitHub Pages

1. Buat repository baru di GitHub, misalnya `kalkulator-lauf`.
2. Push isi folder ini (minimal `index.html`) ke branch `main`:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Kalkulator Transformasi Lauf 2D"
   git branch -M main
   git remote add origin https://github.com/<username>/kalkulator-lauf.git
   git push -u origin main
   ```
3. Di GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   pilih branch `main` dan folder `/ (root)`, lalu **Save**.
4. Situs akan tersedia di `https://<username>.github.io/kalkulator-lauf/` setelah 1–2 menit.

## Mengganti NIM

Ubah nilai **XX** dan **YY** di panel bagian atas halaman — koordinat Titik 1
(`x₁ = 90.XX`, `y₁ = 90.YY`) dan seluruh hasil hitungan akan otomatis diperbarui.

## Verifikasi

Untuk NIM 67/72, hasil kalkulator ini cocok persis dengan hitungan manual pada laporan tugas:
a = 28.811243, b = −4.520086, c = −0.054360, d = 0.023261, c₁ = −710.687174, c₂ = −343.495801,
σ₀ = ±412.6793 m, RMSE₂D = 412.6793 m.

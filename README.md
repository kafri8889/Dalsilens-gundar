# Template LaTeX PI – Informatika Universitas Gunadarma
Berdasarkan Buku Pedoman Penulisan Ilmiah Prodi Informatika 2025

## Struktur Folder

```
pi-gunadarma/
├── main.tex                  ← File utama (compile dari sini)
├── halaman/
│   ├── judul.tex             ← Halaman sampul/judul
│   ├── orisinalitas.tex      ← Pernyataan orisinalitas & publikasi
│   ├── pengesahan.tex        ← Lembar pengesahan
│   ├── abstrak.tex           ← Abstrak (Indonesia + Inggris)
│   ├── katapengantar.tex     ← Kata pengantar
│   ├── daftarlampiran.tex    ← Daftar lampiran
│   ├── daftarpustaka.tex     ← Daftar pustaka
│   └── lampiran.tex          ← Isi lampiran
├── bagian/
│   ├── bab1-pendahuluan.tex
│   ├── bab2-tinjauanpustaka.tex
│   ├── bab3-pembahasan.tex
│   └── bab4-penutup.tex
└── gambar/                   ← Letakkan semua gambar/foto di sini
    ├── logo-gunadarma.png    ← Logo UG (diameter 6cm)
    ├── foto-mahasiswa.jpg    ← Foto 3x4 hitam putih
    ├── diagram-alur.png      ← Gambar-gambar lainnya
    └── ...
```

## Langkah Pertama

1. **Isi data diri** di bagian atas `main.tex`:
   ```latex
   \newcommand{\NamaMahasiswa}{Nama Lengkap Kamu}
   \newcommand{\NPM}{10XXXXXXXX}
   \newcommand{\JudulPI}{Judul PI Kamu}
   % ... dst
   ```

2. **Letakkan file gambar** di folder `gambar/`:
   - `logo-gunadarma.png` – logo UG diameter 6cm
   - `foto-mahasiswa.jpg` – foto 3x4 hitam putih untuk halaman orisinalitas

3. **Compile** menggunakan `pdflatex` (jalankan 2x agar TOC update):
   ```bash
   pdflatex main.tex
   pdflatex main.tex
   ```
   Atau gunakan Overleaf (upload semua file dengan struktur folder yang sama).

## Ketentuan Format (Ringkasan)

| Elemen             | Format                                      |
|--------------------|---------------------------------------------|
| Font               | Times New Roman (mathptmx)                  |
| Ukuran isi         | 12pt                                        |
| Judul Bab          | 14pt, Bold, KAPITAL, Tengah                 |
| Judul Subbab       | 12pt, Bold, Kapital Awal Kata, Kiri         |
| Spasi isi          | 1.5                                         |
| Spasi abstrak      | Single (1)                                  |
| Margin             | Atas 4cm, Bawah 3cm, Kiri 4cm, Kanan 3cm   |
| Nomor hal. awal    | Romawi kecil (i, ii, iii…), tengah bawah    |
| Nomor hal. isi     | Arab (1, 2, 3…), pojok kanan atas           |
| Nomor hal. lampiran| L-1, L-2…, tengah bawah                    |
| Gambar             | Caption di bawah, tengah                   |
| Tabel              | Caption di atas, tengah                    |
| Sitasi             | (Pengarang, Tahun)                          |

## Tips

- Untuk **gambar**: selalu referensikan dengan `Gambar~\ref{fig:label}`, 
  bukan "gambar di atas/bawah".
- **Subbagian** minimal harus ada 2, tidak boleh tunggal.
- **Daftar Pustaka** minimal 10 referensi, diurutkan alfabetik.
- Istilah asing ditulis `\textit{miring}`.
- Tidak boleh ada kata ganti orang (Anda, Saya, Kita).

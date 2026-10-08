# Dalsilens - Penulisan Ilmiah Informatika Universitas Gunadarma

Naskah Penulisan Ilmiah (PI) beserta manual book dan paper untuk aplikasi **Dalsilens**, alat bantu mobile *real-time* bagi penderita dikromasi. Seluruh dokumen ditulis dengan LaTeX dan disusun mengikuti Buku Pedoman Penulisan Ilmiah Prodi Informatika 2025.

| Keterangan     | Isi |
|----------------|-----|
| Judul          | Dalsilens: Alat Bantu Mobile Real-Time untuk Penderita Dikromasi Menggunakan Daltonisasi LMS dan Identifikasi Warna Berbasis HSV |
| Penulis        | Anaf Naufalian (50423155) |
| Pembimbing     | Dr. Bonang Waspadadi Ligar, S.Si., MMSI |
| Program Studi  | Informatika, Fakultas Teknologi Industri, Universitas Gunadarma |
| Tanggal Sidang | 19 Agustus 2026 |
| Tanggal Lulus  | 9 September 2026 |

## Isi repositori

Satu repositori ini memuat tiga dokumen terpisah, dan ketiganya bersumber dari LaTeX:

| Dokumen         | Sumber                | Hasil                 | Keterangan |
|-----------------|-----------------------|-----------------------|------------|
| Penulisan Ilmiah| `main.tex`            | `main.pdf`            | Naskah PI lengkap: bagian awal, empat bagian isi, daftar pustaka, dan lampiran |
| Manual book     | `manual-book/manual.tex` | `manual-book/manual.pdf` | Petunjuk penggunaan aplikasi, margin sama dengan PI |
| Paper           | `paper/paper.tex`     | `paper/paper.pdf`     | Jurnal ringkas, tersedia dalam Bahasa Indonesia dan Bahasa Inggris |

Berkas DOCX dan PDF siap kumpul ada di `doc/`. Berkas DOCX dihasilkan dari sumber LaTeX yang sama (antara lain lewat pandoc), terutama untuk keperluan revisi dan pemeriksaan format.

## Struktur folder

```
Dalsilens-gundar/
├── main.tex                  ← Berkas utama PI (compile dari sini)
├── main.pdf                  ← Hasil render PI
├── .latexmkrc                ← Konfigurasi latexmk (pdflatex + biber)
├── bib/
│   └── main.bib              ← Basis data pustaka (biblatex + biber)
├── halaman/                  ← Bagian awal PI
│   ├── judul.tex             ← Halaman sampul/judul
│   ├── orisinalitas.tex      ← Pernyataan orisinalitas dan publikasi
│   ├── pengesahan.tex        ← Lembar pengesahan
│   ├── abstrak.tex           ← Abstrak (Indonesia)
│   ├── katapengantar.tex     ← Kata pengantar
│   ├── daftarlampiran.tex    ← Daftar lampiran
│   ├── daftarpustaka.tex     ← Daftar pustaka
│   └── lampiran.tex          ← Isi lampiran (listing dan output program)
├── bagian/                   ← Empat bagian isi PI
│   ├── bab1-pendahuluan.tex
│   ├── bab2-tinjauanpustaka.tex
│   ├── bab3-pembahasan.tex
│   └── bab4-penutup.tex
├── gambar/                   ← Gambar, diagram, dan tangkapan layar
├── manual-book/              ← Dokumen manual book (LaTeX mandiri)
│   ├── manual.tex
│   └── image/
├── paper/                    ← Dokumen paper/jurnal
│   ├── paper.tex
│   ├── content-id.tex        ← Isi Bahasa Indonesia
│   └── content-en.tex        ← Isi Bahasa Inggris
├── doc/                      ← Keluaran DOCX/PDF untuk revisi dan pengumpulan
├── references/               ← PDF artikel rujukan
└── temp/                     ← Cadangan revisi
```

## Cara compile

Konfigurasi `.latexmkrc` memakai `pdflatex` dengan `biber` untuk daftar pustaka. Setiap dokumen di-compile dari berkas utamanya masing-masing:

```bash
# Penulisan Ilmiah
latexmk -pdf main.tex

# Manual book
cd manual-book && latexmk -pdf manual.tex

# Paper (Bahasa Indonesia aktif secara bawaan)
cd paper && latexmk -pdf paper.tex
```

Untuk paper, pilih bahasa dengan mengaktifkan salah satu baris di bagian bawah `paper/paper.tex`: `\input{content-id}` untuk Bahasa Indonesia atau `\input{content-en}` untuk Bahasa Inggris. Kedua berkas memakai pustaka, rumus, gambar, dan tabel yang identik; hanya prosa, judul, abstrak, dan caption yang berbeda.

Proyek ini juga menyertakan konfigurasi *run* IntelliJ IDEA di `.idea/runConfigurations/` (`main`, `manual-book`, `paper`). Semua dokumen juga dapat di-compile di Overleaf dengan struktur folder yang sama.

## Ketentuan format yang diikuti (ringkasan)

| Elemen              | Format |
|---------------------|--------|
| Font                | Times New Roman (`mathptmx`) |
| Ukuran isi          | 12pt |
| Judul bagian        | 14pt, Bold, KAPITAL, tengah |
| Judul subbagian     | 12pt, Bold, Kapital Awal Kata, kiri |
| Spasi isi           | 1,5 |
| Spasi abstrak       | Tunggal (1) |
| Margin              | Atas 4cm, Bawah 3cm, Kiri 4cm, Kanan 3cm |
| Nomor halaman awal  | Romawi kecil (i, ii, iii...), tengah bawah |
| Nomor halaman isi   | Arab (1, 2, 3...), pojok kanan atas |
| Nomor halaman lampiran | L-1, L-2..., tengah bawah |
| Gambar              | Caption di bawah, tengah |
| Tabel               | Caption di atas, tengah |
| Sitasi              | (Pengarang, Tahun) |

## Ringkasan hasil

Hasil pengujian pada paper, sebagai gambaran keluaran penelitian:

- *Black Box Testing* 15 skenario fungsional: seluruhnya berhasil.
- Akurasi klasifikasi nama warna: 90% pada pencahayaan normal dan 50% pada pencahayaan redup.
- Performa *real-time*: rata-rata 57,2 FPS dengan latensi 17,5 ms per *frame*.
- Penggunaan RAM rata-rata 218,54 MB tanpa indikasi *memory leak*, utilisasi CPU relatif 19,21%.
- Kebergunaan (*System Usability Scale*) terhadap 18 responden: skor rata-rata 68,33 (kategori B/*Good*).

## Tips penulisan

- Untuk gambar, selalu rujuk dengan `Gambar~\ref{fig:label}`, bukan "gambar di atas/bawah".
- Tiap subbagian minimal berisi dua butir, tidak boleh tunggal.
- Daftar pustaka memuat minimal 10 referensi dan diurutkan alfabetik.
- Istilah asing ditulis `\textit{miring}`.
- Hindari kata ganti orang (Anda, Saya, Kita) pada naskah PI.

## Rujukan

- Buku Pedoman Penulisan Ilmiah Prodi Informatika 2025, Universitas Gunadarma.
- [Skill PI Informatika Gunadarma](https://github.com/kafri8889/skill-pi-informatika-gunadarma) untuk audit format dan isi naskah PI berdasarkan pedoman 2025.

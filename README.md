# Intramedika — Landing Page

Landing page statis (HTML + CSS) yang dibangun langsung dari export CSS desain Figma, canvas desktop **1440 × 12398 px**. Tidak memakai framework atau proses build.

## Struktur

```
intramedika-landing/
├── index.html
├── css/
│   └── styles.css
├── assets/
│   └── images/          ← taruh hasil export gambar dari Figma di sini
├── .gitignore
└── README.md
```

## Langkah wajib: export gambar dari Figma

Export Figma hanya berisi CSS, jadi **file gambarnya harus Anda export sendiri**: pilih layer di Figma → panel *Export* di kanan → PNG (2x disarankan) → simpan dengan nama file di bawah ke `assets/images/`.

| Nama file | Layer / nama fill di Figma | Ukuran frame |
|---|---|---|
| `hero-konsultasi-kesehatan.png` | Konsultasi Kesehatan Hangat di Klinik Modern (background hero) | 1440 × 900 |
| `logo-bpjs-kesehatan.png` | Logo BPJS Kesehatan Minimalis | 24 × 24 |
| `section-masalah-fragmentasi.png` | `image` (image 4) | 1440 × 962 |
| `solusi-digital-kesehatan-terhubung.png` | Solusi Digital Kesehatan Terhubung | 1440 × 960 |
| `interoperabilitas-ekosistem-healthcare.png` | Interoperabilitas Ekosistem Healthcare Indonesia (1) | 1440 × 900 |
| `ekosistem-kesehatan-digital-terintegrasi.png` | Ekosistem Kesehatan Digital Terintegrasi (Rectangle 24) | 1396 × 423 |
| `infografik-ai-layanan-kesehatan.png` | Infografik AI untuk Layanan Kesehatan Cerdas | 1440 × 811 |
| `infografis-portofolio-produk.png` | Infografis Portofolio Produk Kesehatan Terintegrasi | 1440 × 811 |
| `infografik-perjalanan-pasien.png` | Infografik Digital Perjalanan Pasien (1) | 1440 × 811 |
| `transformasi-ekosistem-rumah-sakit.png` | Transformasi Ekosistem Rumah Sakit Terpadu | 1440 × 811 |
| `transformasi-digital-kesehatan-nasional.png` | Transformasi Digital Kesehatan Nasional (1) | 1440 × 811 |
| `platform-kesehatan-terintegrasi.png` | Platform Kesehatan Terintegrasi Modern | 1440 × 811 |
| `masa-depan-layanan-kesehatan-digital.png` | Masa Depan Layanan Kesehatan Digital | 1440 × 811 |
| `mengapa-organisasi-memilih-intramedika.png` | Mengapa Organisasi Memilih Intramedika | 1440 × 811 |

Jika Anda memakai nama file lain, cukup sesuaikan atribut `src` di `index.html` dan `url(...)` hero di `css/styles.css`.

## Menjalankan lokal

Buka `index.html` di browser, atau:

```bash
npx serve .
# atau
python3 -m http.server 8080
```

## Push ke GitHub

```bash
cd intramedika-landing
git init
git add .
git commit -m "Initial commit: Intramedika landing page"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

Untuk hosting gratis, aktifkan **GitHub Pages** (Settings → Pages → Branch `main` / root).

## Catatan kesetiaan terhadap desain

Sesuai permintaan, tidak ada perubahan pada desain. Semua nilai dibawa apa adanya dari Figma, termasuk hal-hal yang mungkin ingin Anda rapikan nanti:

- Menu "Beranda" muncul dua kali di navbar.
- Enam kartu FAQ memakai teks yang sama (placeholder).
- Empat badge "BPJS Kesehatan" identik.
- Link "Enterprise Solutions" dan "About Us" berulang di footer.
- Ukuran font kecil (9–10px) di FAQ dan footer.
- Layer duplikat "image 3" (Platform Kesehatan Terintegrasi) tidak dirender dua kali karena posisinya identik dengan "image 2".

## TODO — teks yang tidak ada di export Figma

Dua teks di footer kolom kiri hanya tampil sebagai nama layer "IntraHospital" di export, jadi isinya belum diketahui. Saya isi sementara, mohon samakan dengan desain (cari komentar `TODO` di `index.html`):

1. Tagline di bawah logo footer (`top: 90px`).
2. Teks di `top: 134px` (sementara "Jakarta, Indonesia").

Logo (ikon di antara "INTRAMEDI" dan "KA") digambar ulang dari dua kotak vektor di export. Jika bentuk aslinya berbeda, export logo sebagai SVG dari Figma dan ganti elemen `<svg class="logo-mark">`.

## Catatan teknis

- Layout memakai posisi absolut di kanvas 1440px agar sama persis dengan Figma. Di layar lebih kecil dari 1440px halaman akan bisa di-scroll horizontal.
- Font **Inter** dan **Lora** dimuat dari Google Fonts.
- Sebagian besar section adalah gambar utuh (seperti di Figma), jadi teks di dalamnya tidak bisa dipilih atau dicari mesin pencari. Gambar sudah diberi atribut `alt`.

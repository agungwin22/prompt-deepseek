# 🧠 Panduan Prompt Efektif untuk DeepSeek
## Membuat Static Website Template Siap Jual di Marketplace

> **Untuk:** Penjual template website di platform seperti projects.co.id
> **Tujuan:** Menghasilkan kode HTML/CSS/JS berkualitas premium menggunakan AI DeepSeek
> **Pendekatan:** Iterative Prompting — mulai dari fondasi, sempurnakan bertahap

---

## 💡 Mengapa Prompt yang Baik Itu Penting?

DeepSeek bekerja paling optimal ketika kamu memberikan **konteks yang kaya, ekspektasi yang spesifik, dan batasan yang jelas**. Semakin ambigu instruksimu, semakin generik hasilnya — dan template yang generik sangat sulit bersaing di marketplace.

Prompt yang efektif terdiri dari **5 lapisan utama:**

| Lapisan | Fungsi | Contoh |
|---|---|---|
| **Role Assignment** | Beri DeepSeek identitas sebagai ahli | "Kamu adalah senior frontend developer..." |
| **Project Context** | Jelaskan tujuan bisnis secara jelas | "Template ini akan dijual di projects.co.id..." |
| **Technical Spec** | Stack, struktur file, batasan teknis | "HTML5, CSS3, Vanilla JS, mobile-first..." |
| **Design Directive** | Estetika, tone visual, target industri | "Modern minimalist, palet navy + gold..." |
| **Output Instruction** | Format jawaban yang diinginkan | "Tampilkan kode lengkap dengan komentar..." |

---

## 🗂️ Pilih Mode Pengerjaan

Sebelum mulai, tentukan dulu mode mana yang ingin kamu gunakan:

| Mode | Cocok Untuk | Kelebihan |
|---|---|---|
| **Mode A: Single File** | Template sederhana, cepat rilis | Mudah dibagikan, 1 file langsung jalan |
| **Mode B: Modular** | Template premium, multi-halaman | Terstruktur, mudah dikustomisasi pembeli |

> Panduan ini mencakup **keduanya**. Ikuti bagian yang sesuai pilihanmu.

---

## 📋 Alur Kerja Lengkap

```
[1] Tetapkan Peran
      ↓
[2] Tentukan Niche & Konsep
      ↓
[3] Pilih Mode (Single File atau Modular)
      ↓
[4A] Spesifikasi Teknis Single File     [4B] Spesifikasi Teknis Modular
      ↓                                        ↓
[5] Bangun Section per Section
      ↓
[6] Review & Quality Check
      ↓
[7] Minta Dokumentasi Pembeli
      ↓
[8] Iterative Refinement (opsional)
```

---

## FASE 1 — PERSIAPAN

---

### Langkah 1 — Penetapan Peran (Role Assignment)

Kirim prompt ini **selalu di awal sesi baru**, sebelum instruksi apapun:

```
Kamu adalah senior frontend developer dan UI/UX designer yang berspesialisasi dalam membuat static website template berkualitas premium untuk dijual secara komersial.

Standar kode yang kamu hasilkan:
- Bersih, modular, dan mudah dibaca
- Diberi komentar deskriptif di setiap section dan fungsi penting
- Mengikuti best practice HTML5 semantik, CSS modern, dan Vanilla JavaScript
- Siap produksi dan layak dijual di marketplace seperti projects.co.id

Dalam setiap respons yang mengandung kode, kamu WAJIB:
1. Memberi komentar pembuka yang menjelaskan tujuan file/section tersebut
2. Mengelompokkan properti CSS secara alfabetis dalam setiap selector
3. Menggunakan penamaan class yang deskriptif (BEM convention lebih diutamakan)
4. Menandai setiap bagian yang perlu dikustomisasi pembeli dengan komentar: /* TODO: Sesuaikan dengan kebutuhan */

Konfirmasi pemahamanmu dengan singkat, lalu tunggu instruksi selanjutnya.
```

> **💡 Mengapa ini penting?** Tambahan instruksi standar kode di sini membuat DeepSeek menghasilkan kode yang jauh lebih konsisten dan profesional sejak baris pertama, bukan hanya di akhir ketika kamu minta review.

---

### Langkah 2 — Tentukan Niche dan Konsep

```
Aku ingin membuat template website statis untuk niche: [NAMA INDUSTRI]
Contoh: Restoran / Real Estate / SaaS Landing Page / Portfolio Freelancer / Klinik Kesehatan

Sebelum menulis kode apapun, lakukan riset singkat dan sarankan:

1. KONSEP DESAIN — Berikan 3 konsep berbeda dengan format:
   - Nama konsep
   - Target audiens yang paling cocok
   - Deskripsi gaya visual (2–3 kalimat)
   - Mood/tone yang ingin disampaikan

2. TIPOGRAFI — Untuk setiap konsep, rekomendasikan:
   - 1 font display/heading (dari Google Fonts)
   - 1 font body (dari Google Fonts)
   - Alasan pemilihan pasangan font tersebut

3. PALET WARNA — Untuk setiap konsep, berikan 7 variabel ini:
   - --color-primary
   - --color-primary-dark
   - --color-secondary
   - --color-accent
   - --color-bg
   - --color-text
   - --color-text-muted
   (semua dalam format hex)

Presentasikan dalam format tabel yang rapi dan mudah dibandingkan.
```

> **💡 Mengapa ini penting?** Meminta nama variabel CSS langsung dari sini membuat DeepSeek menggunakan nama yang sama di seluruh kode nanti — konsistensi terjaga sejak awal, bukan setelah kamu minta review.

---

## FASE 2A — MODE SINGLE FILE

*Gunakan mode ini untuk template sederhana dalam satu file `index.html`.*

---

### Langkah 3A — Spesifikasi Teknis Single File

```
Bagus. Aku memilih konsep: [NAMA KONSEP YANG DIPILIH]
Mode pengerjaan: SINGLE FILE (semua kode dalam satu index.html)

Bangun template dengan spesifikasi berikut:

═══ TEKNOLOGI ═══
- Murni HTML5, CSS3, Vanilla JavaScript — TANPA framework atau build tools
- Struktur: SATU file index.html dengan <style> internal dan <script> internal
- CSS Custom Properties WAJIB digunakan untuk SEMUA nilai warna, font, dan spacing utama
- Letakkan semua variabel CSS di :root di bagian paling atas tag <style>

═══ RESPONSIVITAS ═══
- Pendekatan mobile-first (tulis CSS untuk mobile dulu, gunakan min-width untuk breakpoint lebih besar)
- Breakpoint wajib: 480px / 768px / 1024px / 1280px
- Tidak boleh ada elemen yang overflow secara horizontal di layar 320px

═══ PERFORMA ═══
- Semua gambar menggunakan https://placehold.co/ dengan dimensi realistis dan alt text deskriptif
- Hindari base64 inline image dan inline SVG lebih dari 30 baris
- Lazy loading pada semua gambar below fold: loading="lazy"
- Tidak boleh menggunakan JavaScript library eksternal (jQuery, dll.)

═══ AKSESIBILITAS ═══
- Gunakan tag HTML semantik: <header>, <nav>, <main>, <section>, <article>, <footer>
- Setiap gambar WAJIB memiliki atribut alt yang bermakna
- Setiap elemen interaktif dapat diakses via keyboard (tampilkan focus outline yang jelas)
- Kontras warna minimum 4.5:1 untuk teks body (standar WCAG AA)

═══ ANIMASI ═══
- Hover effects: CSS transition 200–300ms ease-in-out
- Scroll animation: Intersection Observer API (bukan scroll event listener)
- Wajib ada fallback untuk prefers-reduced-motion:
  @media (prefers-reduced-motion: reduce) { * { animation: none !important; transition: none !important; } }

Konfirmasi spesifikasi ini, lalu tunggu instruksi section.
```

---

## FASE 2B — MODE MODULAR

*Gunakan mode ini untuk template premium dengan struktur file yang rapi dan profesional.*

---

### Langkah 3B — Spesifikasi Teknis Modular

```
Bagus. Aku memilih konsep: [NAMA KONSEP YANG DIPILIH]
Mode pengerjaan: MODULAR (file terpisah untuk HTML, CSS, dan JS)

═══ STRUKTUR FOLDER YANG DIINGINKAN ═══

[nama-template]/
│
├── index.html                  ← Halaman utama
├── README.md                   ← Dokumentasi untuk pembeli
│
├── assets/
│   ├── css/
│   │   ├── variables.css       ← HANYA :root dengan semua CSS Custom Properties
│   │   ├── reset.css           ← CSS reset/normalize
│   │   ├── typography.css      ← Semua aturan font, heading, paragraph
│   │   ├── components.css      ← Style komponen reusable (button, card, badge, form)
│   │   ├── layout.css          ← Grid, flexbox, container, spacing system
│   │   ├── sections.css        ← Style spesifik per section halaman
│   │   ├── animations.css      ← Semua @keyframes dan kelas animasi
│   │   └── responsive.css      ← Semua media query (mobile-first)
│   │
│   ├── js/
│   │   ├── main.js             ← Entry point, inisialisasi semua modul
│   │   ├── navigation.js       ← Logic hamburger menu, sticky nav, scroll spy
│   │   ├── animations.js       ← Intersection Observer scroll animations
│   │   ├── accordion.js        ← Logic FAQ accordion
│   │   └── theme.js            ← Dark/light mode toggle
│   │
│   └── images/
│       └── .gitkeep

═══ ATURAN PENULISAN KODE ═══

HTML:
- Tag semantik wajib: <header>, <nav>, <main>, <section>, <article>, <footer>
- Setiap section diberi id deskriptif: id="features", id="pricing", dst.
- Urutan <link> CSS di <head>:
  variables.css → reset.css → typography.css → components.css → layout.css → sections.css → animations.css → responsive.css

CSS:
- Nilai warna dan spacing HANYA boleh ada di variables.css, file lain WAJIB merujuk ke variabel
- Gunakan BEM naming convention: .block__element--modifier
- Kelompokkan properti CSS: positioning → box model → typography → visual → animation
- Buka setiap file dengan komentar header:
  /* ================================================
     NAMA FILE — Deskripsi singkat isi file ini
     ================================================ */

JavaScript:
- Gunakan ES6+ (const/let, arrow functions, template literals, destructuring)
- Setiap file JS dibungkus IIFE untuk menghindari polusi global scope
- Beri JSDoc comment pada setiap fungsi:
  /**
   * @description Fungsi toggle hamburger menu
   * @param {HTMLElement} button - Tombol hamburger
   * @param {HTMLElement} menu - Elemen navigation menu
   * @returns {void}
   */

═══ SPESIFIKASI TEKNIS ═══
- Mobile-first, breakpoint: 480px / 768px / 1024px / 1280px
- Semua gambar: https://placehold.co/ dengan alt text deskriptif
- Lazy loading pada gambar below fold: loading="lazy"
- prefers-reduced-motion wajib diimplementasi di responsive.css
- Kontras warna minimum WCAG AA (4.5:1)

═══ CARA PENGERJAAN ═══
Kerjakan file per file, satu per satu. Mulai dari:
1. variables.css — sebagai acuan semua file lain
2. reset.css
Setelah aku konfirmasi kedua file ini, lanjutkan ke file berikutnya.

Tampilkan nama file lengkap beserta path sebagai judul kode block:
// assets/css/variables.css
```

> **💡 Mengapa mulai dari `variables.css`?** Begitu variabel warna, font, dan spacing sudah terdefinisi, semua file berikutnya tinggal merujuk ke sana — tidak akan ada inkonsistensi warna atau ukuran antar file.

---

## FASE 3 — BANGUN KONTEN

*Fase ini sama untuk Single File maupun Modular.*

---

### Langkah 4 — Bangun Section Secara Bertahap

```
Sekarang bangun section-section halaman. Kerjakan dalam BATCH — tunggu konfirmasiku setelah setiap batch sebelum lanjut.

BATCH 1 — Navigasi & Hero:
- Sticky navigation bar: logo placeholder (teks), menu link, tombol CTA, hamburger button mobile
- Hero section: H1 headline, subheadline, 2 tombol CTA (primary + ghost), elemen visual dekoratif

BATCH 2 — Konten Utama:
- Features/Layanan: grid 3 kolom desktop / 1 kolom mobile, setiap kartu ada ikon SVG inline + judul + deskripsi
- About/Tentang Kami: layout 2 kolom — teks & statistik angka di kiri, gambar placeholder di kanan
- Testimonials: 3 kartu dengan nama, jabatan, avatar placeholder, teks ulasan, rating bintang (★)

BATCH 3 — Konversi & Penutup:
- Pricing: 3 tier (Gratis / Pro / Enterprise), kartu tengah ada badge "Paling Populer" + border highlight
- FAQ: minimal 5 pertanyaan, exclusive accordion (buka satu, tutup yang lain)
- Contact/CTA: form (nama, email, pesan, tombol submit) + info kontak di sebelahnya
- Footer: logo, deskripsi singkat, quick links 2 kolom, ikon sosmed SVG, copyright

ATURAN UNTUK SETIAP SECTION:
- Tandai dengan komentar: <!-- ===== NAMA SECTION ===== -->
- Tandai semua teks yang perlu diganti pembeli: <!-- TODO: Ganti teks ini -->
- JANGAN gunakan "Lorem ipsum" — gunakan konten placeholder yang realistis sesuai niche [NAMA INDUSTRI]

Mulai dengan BATCH 1. Tampilkan hasilnya dan tunggu konfirmasiku.
```

> **💡 Mengapa konten placeholder realistis?** Screenshot template dengan konten nyata jauh lebih menarik di marketplace — pembeli lebih mudah membayangkan template dipakai untuk bisnis mereka, dan conversion rate listing kamu akan naik.

---

## FASE 4 — REVIEW & FINALISASI

---

### Langkah 5 — Quality Check Menyeluruh

```
Semua section selesai. Sekarang lakukan QA (Quality Assurance) menyeluruh dan laporkan hasilnya:

[ ] VISUAL CONSISTENCY
    - Apakah spacing antar section konsisten? (harus menggunakan var(--section-padding))
    - Apakah typography scale harmonis? (H1 > H2 > H3 > body dengan rasio yang jelas)
    - Apakah ada warna hardcoded yang seharusnya pakai variabel CSS?

[ ] RESPONSIVITAS
    - Di 320px: adakah horizontal overflow?
    - Di 768px: apakah transisi grid/flexbox sudah benar?
    - Hamburger menu: bisa dibuka DAN ditutup kembali?

[ ] FUNGSIONALITAS JS
    - Accordion FAQ: exclusive (buka satu menutup yang lain)?
    - Sticky nav: berubah style saat scroll melewati 80px?
    - Scroll animation: elemen fade-in saat masuk viewport?
    - Form: validasi field kosong dengan pesan error yang informatif?

[ ] AKSESIBILITAS
    - Semua gambar ada alt text yang bermakna?
    - Semua link punya teks deskriptif (bukan "klik di sini")?
    - Tab order logis dan focus state terlihat jelas?
    - aria-label ada pada tombol hamburger dan ikon-only links?

[ ] KODE BERSIH
    - CSS selector yang tidak terpakai sudah dihapus?
    - Tidak ada console.log yang tertinggal?
    - Tidak ada duplikasi style antar section?

Laporkan temuan per kategori, lalu tampilkan kode final yang sudah diperbaiki secara lengkap.
```

---

### Langkah 6 — Dokumentasi untuk Pembeli

```
Terakhir, buatkan file README.md profesional untuk disertakan bersama template ini.

Struktur README:

# [NAMA TEMPLATE]
Deskripsi singkat template (2–3 kalimat, tonjolkan fitur unggulan)

## 📦 Isi Paket
Daftar semua file yang disertakan

## 🚀 Cara Menggunakan
Langkah 1-2-3 yang sangat mudah dipahami non-developer

## 🎨 Kustomisasi Warna
Cara edit variabel CSS di :root / variables.css — sertakan contoh SEBELUM dan SESUDAH

## 🔤 Kustomisasi Font
Cara mengganti Google Fonts — link yang perlu diubah dan nama variabel CSS yang relevan

## 📐 Menambah atau Menghapus Section
Instruksi singkat dengan referensi ke komentar section di kode HTML

## 💡 5 Kustomisasi Populer
Lima modifikasi yang paling sering dilakukan pembeli, dengan instruksi spesifik masing-masing

## 🌐 Kompatibilitas Browser
Daftar browser yang didukung (Chrome, Firefox, Safari, Edge — versi berapa ke atas)

## 📄 Lisensi
Template ini dilisensikan untuk penggunaan komersial oleh pembeli tunggal.

Tulis dalam Bahasa Indonesia yang ramah, profesional, dan mudah dipahami pembeli non-teknis.
```

---

## FASE 5 — PENYEMPURNAAN LANJUTAN

---

### Langkah 7 — Iterative Refinement (Opsional)

Gunakan prompt-prompt ini setelah template dasar selesai untuk meningkatkan nilai jual:

**Tingkatkan visual Hero Section:**
```
Hero section masih terlihat flat. Tingkatkan dengan:
1. Animasi CSS keyframes pada elemen dekoratif (floating, pulse, atau rotate lambat)
2. Gradient overlay yang subtle pada background
3. Efek parallax ringan saat scroll menggunakan Vanilla JS (max translateY 30px)
Jangan ubah struktur HTML yang sudah ada — hanya tambah CSS dan JS.
```

**Efek glassmorphism:**
```
Terapkan efek glassmorphism pada [NAMA KOMPONEN, contoh: pricing cards / navbar saat scroll].
Spesifikasi: background: rgba(255,255,255,0.1); backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,0.2).
Sertakan fallback untuk browser yang tidak mendukung backdrop-filter.
```

**Tambah dark mode:**
```
Implementasikan dark/light mode toggle dengan ketentuan:
1. Override CSS Custom Properties di :root[data-theme="dark"] (JANGAN duplikasi selector)
2. Toggle button di navbar — gunakan ikon matahari/bulan sebagai SVG inline
3. Simpan preferensi ke localStorage dengan key: "color-theme"
4. Deteksi preferensi sistem dengan prefers-color-scheme sebagai nilai default awal
5. Transisi antar mode: transition: background-color 300ms ease, color 300ms ease pada body dan card
```

**Perbaiki bug spesifik:**
```
[DESKRIPSIKAN BUG SECARA SPESIFIK]
Contoh: "Accordion FAQ tidak menutup item yang sebelumnya terbuka ketika item lain diklik"

Tolong:
1. Jelaskan penyebab bug ini
2. Tampilkan HANYA bagian kode yang perlu diubah (format: sebelum vs sesudah)
3. Jelaskan mengapa solusimu lebih baik dari kode sebelumnya
```

**Optimasi performa:**
```
Lakukan audit performa pada kode yang sudah dibuat:
1. Identifikasi CSS yang menyebabkan layout reflow/repaint tidak perlu
2. Pastikan semua animasi menggunakan transform dan opacity (bukan top/left/width/height)
3. Cek apakah ada event listener yang perlu di-debounce (scroll, resize)
4. Berikan rekomendasi untuk meningkatkan Lighthouse Performance Score
Tampilkan semua perbaikan dalam format diff (sebelum → sesudah).
```

---

## ⚠️ Kesalahan Umum & Cara Menghindarinya

| Kesalahan | Dampak | Solusi |
|---|---|---|
| Mengirim semua instruksi sekaligus | Output tidak konsisten, banyak bagian dikorbankan | Gunakan pendekatan batch per fase |
| Langsung coding tanpa pilih konsep | Banyak revisi desain di tengah jalan | Selalu mulai dari Langkah 2 |
| Skip quality check | Bug lolos, pembeli kasih rating buruk | Wajib jalankan Langkah 5 |
| Tidak minta dokumentasi | Template susah dikustomisasi, rating turun | Selalu sertakan README |
| Konten placeholder "Lorem ipsum" | Screenshot tidak menarik pembeli | Minta konten sesuai niche |
| Warna hardcoded di CSS | Pembeli kesulitan rebranding | Paksa variabel CSS dari awal |
| Minta semua JS dalam satu file | Kode sulit dibaca dan di-maintain pembeli | Gunakan Mode Modular |

---

## 📌 Quick Reference — Template Variabel `:root` Wajib

Salin template ini dan berikan ke DeepSeek di Langkah 3 sebagai acuan standar:

```css
:root {
  /* === WARNA UTAMA === */
  --color-primary:        #[HEX];   /* TODO: Warna brand utama */
  --color-primary-dark:   #[HEX];   /* Hover state primary */
  --color-secondary:      #[HEX];
  --color-accent:         #[HEX];   /* TODO: Highlight, badge, CTA sekunder */

  /* === BACKGROUND === */
  --color-bg:             #[HEX];   /* Background halaman utama */
  --color-bg-alt:         #[HEX];   /* Section berganti-ganti */
  --color-bg-card:        #[HEX];   /* Kartu dan komponen */

  /* === TEKS === */
  --color-text:           #[HEX];   /* Body text */
  --color-text-muted:     #[HEX];   /* Caption, label kecil */
  --color-text-inverse:   #[HEX];   /* Teks di atas background gelap */

  /* === TIPOGRAFI === */
  --font-heading:         '[NAMA FONT]', serif;
  --font-body:            '[NAMA FONT]', sans-serif;
  --font-size-base:       1rem;
  --line-height-base:     1.6;

  /* === SPACING SYSTEM === */
  --space-xs:   0.25rem;   /*  4px */
  --space-sm:   0.5rem;    /*  8px */
  --space-md:   1rem;      /* 16px */
  --space-lg:   1.5rem;    /* 24px */
  --space-xl:   2rem;      /* 32px */
  --space-2xl:  3rem;      /* 48px */
  --space-3xl:  4rem;      /* 64px */
  --section-padding: 5rem 0;

  /* === LAYOUT === */
  --container-max:    1200px;
  --container-pad:    1.5rem;
  --border-radius:    0.5rem;
  --border-radius-lg: 1rem;

  /* === SHADOW === */
  --shadow-sm: 0 1px 3px rgba(0,0,0,.08);
  --shadow-md: 0 4px 16px rgba(0,0,0,.10);
  --shadow-lg: 0 8px 32px rgba(0,0,0,.12);

  /* === TRANSISI === */
  --transition:      250ms ease-in-out;
  --transition-slow: 400ms ease-in-out;
}
```

---

*Ganti semua teks dalam tanda kurung kotak `[...]` sesuai kebutuhan proyekmu sebelum mengirim ke DeepSeek.*
*Panduan ini dirancang untuk menghasilkan template yang tidak hanya fungsional, tetapi benar-benar layak jual dan kompetitif di marketplace.*

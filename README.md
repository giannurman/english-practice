# 🗣️ English Practice

Modul latihan percakapan bahasa Inggris untuk keluarga (rumah) dan kantor (tech lead).
Web statis — tanpa instalasi, tanpa server, tanpa internet.

## Cara pakai

1. Buka `index.html` di **Chrome, Edge, atau Safari** (klik dua kali file-nya).
   Di HP: salin folder ini ke HP lalu buka `index.html` dengan browser, atau host di GitHub Pages.
2. Pilih tab, lalu kategori. Kolom pencarian di beranda mencari di semua kategori.
   - **🏠 Rumah** (`#/rumah`): **Keluarga** dan **Untuk Anak**.
   - **💼 Kerja** (`#/kerja`): **Kantor — Tech Lead**, **Kantor — Santai** (small talk: pantry,
     makan siang, hobi, ulang tahun, farewell), **Sales — Tech B2B** (cold call sampai renewal; latih
     dari sisi sales maupun pelanggan), **Project Manager — IT** (kickoff, status update, risiko,
     change request, go-live), **Product Manager** (riset pengguna, roadmap, prioritas, A/B test),
     **UI/UX Designer** (usability test, design critique, handoff, design QA, revisi klien), dan
     **IT Security** (SOC, temuan kerentanan, threat modeling, pentest, audit, laporan risiko ke direksi),
     **PMO / Portfolio** (prioritas & pendanaan proyek, kapasitas, stage-gate, menghentikan proyek),
     **Business Operations** (KPI, perbaikan proses, SOP, vendor, anggaran, koordinasi antar divisi),
     **Staff Engineer** (RFC, review arsitektur lintas tim, strategi teknis, tech debt, mentoring),
     **CEO / Eksekutif** (town hall, board & investor, tim C-level, restrukturisasi, krisis), dan
     **Director of Engineering** (headcount, planning lintas tim, kalibrasi, eskalasi, re-org).

   Link tab bisa dibagikan langsung, misalnya `…/index.html#/kerja` untuk rekan kantor.
3. Di setiap percakapan:
   - **🔊** dengarkan satu kalimat · **▶ Play all** dengarkan seluruh dialog.
   - **Tombol kecepatan** (kanan atas) → 🐢 0.7x untuk anak / latihan pelafalan.
   - **Terjemahan** (kanan atas) → tampil/sembunyi semua. Klik satu bubble untuk intip terjemahan kalimat itu saja.
   - **🎭 Role-play** → pilih peranmu. Kalimatmu disembunyikan (hanya terjemahan sebagai petunjuk),
     peran lain dibacakan. Saat giliranmu: ucapkan kalimatnya → tekan **Next** → dengarkan versi yang benar.
   - **Kosakata, Pola kalimat, Kesalahan umum**, dan **Mini quiz** di bawah dialog.
   - **✅ Tandai sudah dilatih** → progres tersimpan di browser.

### Ide latihan keluarga
- Satu tema per minggu. Senin–Rabu baca & dengar, Kamis–Minggu role-play tanpa terjemahan.
- Pakai kalimatnya di momen nyata: tema *Breakfast* saat sarapan, *Bedtime* sebelum tidur.
- Tukar peran: Ayah jadi Kakak, Kakak jadi Ayah — anak biasanya senang sekali.

### Ide latihan kantor
- Baca percakapan *Daily Stand-up* dengan suara keras sebelum stand-up sungguhan.
- Kerjakan mini quiz *Kesalahan umum* — lalu perhatikan apakah kamu masih melakukannya saat meeting.

## Menambah percakapan

Tambahkan objek baru di `data/family.js`, `data/kids.js`, `data/office.js`, `data/casual.js`, `data/sales.js`, `data/pm.js`, `data/product.js`, `data/design.js`, `data/security.js`, `data/pmo.js`, `data/bizops.js`, `data/staff.js`, `data/ceo.js`, atau `data/director.js`:

```js
{
  id: "at-the-doctor",            // unik, huruf kecil, pakai tanda -
  category: "family",             // family | kids | office | casual | sales | pm | product | design | security | pmo | bizops | staff | ceo | director
  emoji: "🩺",                    // hindari emoji gabungan (mis. 👩‍⚕️) — tidak tampil benar di Windows 10
  title: "At the Doctor",
  titleId: "Di Dokter",
  level: "medium",                // easy | medium
  roles: ["Mom", "Kakak"],        // urutan menentukan posisi bubble (kiri/kanan bergantian)
  lines: [
    { role: "Mom", en: "How are you feeling?", id: "Bagaimana perasaanmu?" },
  ],
  vocab:    [{ en: "fever", id: "demam" }],
  phrases:  ["How are you feeling?"],
  mistakes: [{ wrong: "I'm fever.", right: "I have a fever.", note: "Sakit pakai 'have': have a fever, have a cold." }],
  parentTips: [],                 // khusus kategori kids (pengganti mistakes)
}
```

Nama peran baru (mis. "Doctor") akan memakai avatar default 🙂. Untuk avatar & warna khusus,
tambahkan di `ROLE_META` pada `js/app.js`.

**Kategori baru:** buat file `data/<nama>.js`, tambahkan `<script>`-nya di `index.html`, lalu daftarkan
di `CATEGORIES` pada `js/app.js` dengan field `group: "rumah"` atau `group: "kerja"` untuk menentukan
tab-nya. Tambahkan juga warna `--<nama>` dan kelas `.cat-<nama>` di `css/style.css`.

## Struktur

```
index.html        halaman utama
css/style.css     tampilan (mobile-first, mendukung dark mode)
js/app.js         navigasi, suara (Web Speech API), role-play, quiz, progres
data/*.js         isi percakapan
```

Catatan: suara memakai Text-to-Speech bawaan browser/OS. Kualitas suara terbaik biasanya di Edge
("Microsoft … Online (Natural)") dan Chrome di Android.

## Tentang konten

Percakapan dan penjelasan dibuat dengan bantuan AI dan sudah ditinjau, tetapi mungkin masih ada
kesalahan. Menemukan yang keliru? Silakan buka [issue](https://github.com/giannurman/english-practices/issues).

## Lisensi

[MIT](LICENSE) — bebas dipakai, disalin, dan dimodifikasi (termasuk isi percakapan), asalkan
menyertakan pemberitahuan hak cipta dan lisensi.

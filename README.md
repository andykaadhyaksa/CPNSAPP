# Siap CPNS · Latihan SKD

Aplikasi latihan SKD CPNS (TWK, TIU, TKP) dalam satu berkas HTML, tanpa build. Bisa dipasang di HP (PWA) dan tetap jalan offline setelah dibuka sekali.

## Fitur
- Latihan per subtes/topik dengan pembahasan langsung
- Simulasi SKD: 110 soal, 100 menit, penilaian resmi (TWK/TIU 5-0, TKP 1-5) dan cek passing grade (65 / 80 / 166)
- Progres: akurasi per subtes dan topik, riwayat, soal yang perlu diulang
- Info CPNS 2026: status seleksi, format SKD, materi, strategi
- Cadangan data (ekspor/impor JSON), mode gelap

## Mengisi bank soal
Isi array `BANK_REAL` di `index.html`. Selama kosong, aplikasi memakai 12 soal contoh. Skema satu soal ada di komentar di atas `BANK_REAL`.

## Publikasi (GitHub Pages)
Unggah semua isi folder ke repositori, lalu Settings → Pages → Deploy from a branch → `main` / root.
Setiap kali `index.html` berubah, naikkan angka versi di `sw.js` (`const V='cpns-v1'`).


## Versi 3
- Beranda dengan estimasi skor, rekomendasi cerdas, target harian, streak.
- Belajar: 15 materi + trik cepat + jebakan + contoh interaktif; kartu hafalan (Leitner).
- Pembahasan, trik, dan tautan materi tampil setelah tiap soal; waktu per soal; simpan soal (bintang); buku kesalahan.
- Panduan: akademik, mental (napas 4-4-6, cek diri), rencana 4 minggu/7 hari, daftar Hari-H, info CPNS.
- Progres: tren simulasi, prioritas belajar, pencapaian.

## Versi 3.1
- Panduan → Kurikulum: tugas harian adaptif (4 fase), target jelas, tercentang otomatis.
- Panduan → Analisis: radar kekuatan, jarak ke batas lolos, kelebihan, minus, strategi, akurasi per topik, kecepatan, tren, konsistensi.

## Versi 3.2
- Tata letak lebar penuh (multi-kolom di desktop), tema dipindah ke sidebar.
- Tab baru di Panduan: Program (6 program), Strategi, Rumus, Seleksi (alur, syarat, dokumen, FAQ); tab Tips di Belajar.
- Latihan: paket latihan, peta topik, soal per tahun; Progres: cakupan bank soal.

## Versi 3.3
- Pembahasan rinci: alasan kunci, analisis tiap opsi, dan playbook cara menghadapi soal serupa (31 jenis soal).

## Versi 4 (rombak UI + materi rinci)
- Navigasi baru: Beranda, Belajar, Latihan, Tes, Program, Progres, Panduan (di HP: bar bawah 6 menu, sisanya di "Lainnya").
- Belajar: 22 materi dengan ringkasan, langkah menjawab, trik kunci, cara menghafal, contoh berlangkah, jebakan, dan soal coba sendiri.
- Pembahasan soal: pola deret dan rumus numerik dijelaskan langkah demi langkah (hanya tampil bila cocok dengan kunci), materi TWK terkait, aturan logika, dan analisis tiap opsi.
- Setelah mengubah file, naikkan versi cache di `sw.js`.

## Versi 4.1 — Soal tambahan format terbaru
- +243 soal orisinal (bank sekarang 1.601): deret kotak/selang-seling/huruf/tiga angka (90), numerik cerita (92), TWK (32), logika & analogi (19), TKP (17 dengan skor 1–5).
- Bukan soal asli SKD 2026 (belum ada yang dirilis resmi); dibuat mengikuti pola dan format terbaru. Soal numerik/deret jawabannya diverifikasi kode; TWK/TKP ditulis manual — mohon dicek bila ragu.
- Soal "own": penjelasan langkah demi langkah + analisis tiap opsi; angka dalam kotak tampil sebagai kotak.

## Versi 4.2 — Program lebih jelas
- Tab Program: kartu "Posisi kamu" (Hari X dari N, sisa hari, deretan hari: ✓ tuntas / merah terlewat / biru hari ini).
- Tab baru "Jadwal lengkap": semua hari lengkap dengan tanggal, fase, target, dan daftar tugas per hari (ketuk untuk membuka).
- "Hari-hari berikutnya": 7 hari ke depan dengan rincian tugas.

## Versi 4.3 — Sinkronisasi antar perangkat
Memakai metode yang sama dengan PAPs Siap 500 (Supabase, tabel `paps_sync`, kode sinkron). Tombol "Sinkron" di pojok kanan atas (semua layar), Progres → Data & sinkron, atau Lainnya → Sinkronisasi: ketik kode sinkron (min. 6 karakter), lalu ketik kode yang sama di perangkat lain. Data dipisahkan dari PAPs otomatis (id `cpns:<kode>`). Sinkron otomatis 2 detik setelah perubahan, saat app dibuka, dan tiap ±45 detik; bila dua perangkat sama-sama berubah, data digabung.

## Versi 4.4 — Perbaikan kualitas
- Soal: dipulihkan teks bacaan/informasi yang hilang (12+ soal TWK & logika), rumus yang rusak direkonstruksi (7 soal), 10 soal yang tidak dapat dipulihkan disembunyikan (bank kini 1.591). ID soal tidak berubah, progres aman.
- Rumus tampil seperti formula (pecahan bertumpuk, akar, pangkat) pada soal TIU, pembahasan, dan materi.
- Pengerjaan soal: opsi di bawah soal, panel "Daftar soal dan selesai" di kanan (desktop).
- Pembahasan: materi/cara mengingat hanya tampil bila sesuai kunci; analisis opsi lebih spesifik (kemungkinan kesalahan pada soal hitungan).
- Riwayat: sesi dan semua soal yang pernah dikerjakan dapat dibuka kembali (jawaban + pembahasan) tanpa mengubah progres.
- Belajar → Hafalan: teknik menghafal ditulis ulang dengan langkah dan contoh nyata.
- Nomor sumber soal ditampilkan agar mudah dilaporkan bila ada yang janggal.

## Versi 4.6 — Cek ulang menyeluruh (soal, opsi, kunci, rumus)
- Seluruh TIU dan TWK dibaca satu per satu; TKP: semua soal tanpa pembahasan dibaca dan 357 soal berpembahasan dicocokkan dengan skornya.
- 21 kunci jawaban yang salah di naskah sumber dikoreksi (mis. TWK: bom atom Hiroshima–Nagasaki, MA vs MK, Hari Kesaktian Pancasila 1 Oktober, asas ius sanguinis, Maklumat 14 November 1945; TIU: 3 soal hitungan) dan pembahasannya ditulis ulang. 23 soal TKP dinilai ulang skornya karena skor sumber bertentangan dengan logikanya atau dengan soal kembarannya.
- Soal yang tidak dapat dipulihkan disembunyikan (soal tanpa kunci yang sahih, soal bergabung, kunci bertentangan dengan premis). Bank aktif: 1.544 soal (TWK 494 · TIU 495 · TKP 555). ID tidak berubah, jadi progres, riwayat, dan sinkron tetap aman.
- Opsi yang rusak diperbaiki: teks soal lain yang menempel di opsi dipotong, opsi kembar diganti, ±215 salah ketik pada soal hasil PDF dibetulkan (mis. "dibwjudkan", "persenjetaan", "Postdam"). Soal buatan sendiri tidak disentuh.
- 13 pembahasan TIU lain (silogisme, hitungan waktu, persen, pola) ditulis ulang bertahap; pecahan dengan koefisien huruf (mis. 2y/3) kini ikut ditulis atas-bawah.
- Analisis tiap opsi pada TWK/TKP tidak lagi memakai kalimat hitungan; untuk soal "kecuali/bukan" kalimatnya disesuaikan.
- Cache offline naik ke cpns-v10.
- Catatan jujur: skor TKP dan beberapa kunci TWK dari PDF sumber bersifat penilaian; yang terlihat bertentangan sudah saya putuskan sendiri dan ditandai di atas, tetapi sisanya mengikuti naskah sumber.

## Versi 4.5 — Pembahasan ditulis ulang
- 134 pembahasan yang rusak akibat ekstraksi PDF (pecahan/pangkat/tabel terurai menjadi deretan angka) ditulis ulang menjadi langkah bernomor ("Langkah 1 — … Jawaban: X") dengan pecahan atas-bawah. Semua hasil hitung diperiksa terhadap kunci jawaban.
- Soal yang teksnya cacat diperbaiki (pecahan/pangkat hilang, soal cerita yang kontradiktif, opsi yang salah cetak) dan diberi catatan di pembahasan bila naskah asli janggal.
- 11 soal tambahan disembunyikan karena kunci/gambar/soalnya tidak dapat dipulihkan (logika duduk melingkar 2 soal, soal dengan kunci yang bertentangan dengan soalnya, dsb.). Bank kini 1.580 (soal "pernyataan berikut" tanpa pernyataannya ikut disembunyikan; 8 pembahasan hitungan tambahan dirapikan). ID soal tidak berubah; progres, riwayat, dan sinkron aman.
- Analisis tiap opsi pada soal hitungan kini menyebut hasil yang benar vs opsi itu.

## Versi 4.7 — Soal figural (gambar)
- Bank bertambah 77 soal figural bergambar (tahun 2026), sehingga bank aktif menjadi 1.621 soal (TWK 494 · TIU 572 · TKP 555). ID soal lama tidak berubah; progres, riwayat, dan sinkron aman.
- Empat jenis: **deret gambar** (23 soal: rotasi, pergeseran, siklus, sisi/jumlah bertambah, kotak terisi, cermin bergantian, jarum jam), **ketidaksamaan** (20: putar vs cermin, sisi titik, jumlah, warna/bentuk sepusat, simetri), **analogi gambar** (18: rotasi, cermin, warna dibalik, jumlah/sisi bertambah, luar–dalam bertukar, bergeser, dua perubahan sekaligus), **matriks 3×3** (16: kotak latin, jumlah titik, operasi gabung/beda/kurang, rotasi baris-kolom).
- Terintegrasi seperti tipe soal lain: opsi berupa gambar (A–E), pembahasan bernomor dengan atribut J-P-A-W-B, alasan tiap opsi salah, kartu "Materi yang diuji" dan "Cara mengingat", trik cepat, "Cara menghadapi soal serupa", empat materi baru (deret, ketidaksamaan, analogi, matriks) lengkap dengan langkah, trik kunci, contoh, dan "Coba sendiri" bergambar, kartu hafalan "Aturan figural", latihan per topik, statistik/akurasi per topik, rekomendasi materi, buku kesalahan, tinjauan, dan simulasi.
- Simulasi memuat paling banyak 6 soal figural (dari 35 TIU) dan tes diagnostik 1, agar komposisinya mirip ujian.
- Kurikulum: tugas figural ditambahkan pada rencana 4 minggu dan mode kilat 7 hari; program remedial TIU menyebut figural.
- Perbaikan lain: teks "Trik cepat" dan "Cara menghadapi soal serupa" yang memuat huruf tebal sebelumnya tampil dengan tanda `<b>` mentah; kini tampil benar.
- Cache offline naik ke cpns-v11.
- Catatan jujur: semua soal figural adalah soal orisinal buatan sendiri (gambar dibangkitkan dengan kode), bukan soal resmi BKN. Kunci ditentukan oleh aturan pembangkitnya dan setiap opsi dipastikan tidak kembar secara visual; saya memeriksa tampilan contoh tiap pola, tetapi belum diuji oleh orang lain. Matriks 3×3 adalah tipe klasik yang umum di bimbel; kisi-kisi SKD terbaru terutama menyebut deret, ketidaksamaan, dan analogi.

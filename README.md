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

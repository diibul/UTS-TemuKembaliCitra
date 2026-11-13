# Dataset Putusan Pengadilan Perkara Narkotika dan Psikotropika

Repositori ini memuat dataset dokumen putusan pengadilan yang dikumpulkan dan dikelola sebagai bagian dari penugasan Ujian Tengah Semester (UTS) mata kuliah Temu Kembali Informasi pada Program Studi Informatika, Fakultas Teknik, Universitas Muhammadiyah Malang.

Dataset ini berfokus pada putusan perkara Pidana Khusus dengan klasifikasi Narkotika dan Psikotropika dari Pengadilan Negeri Batam. Tujuan utama penyusunan dataset adalah menyediakan korpus dokumen hukum terbuka yang representatif untuk pengujian konsep temu kembali informasi, mencakup tahapan akuisisi dokumen, ekstraksi teks dan metadata, prapemrosesan teks hukum, pembobotan istilah, serta pengindeksan dokumen.

## Informasi Akademik

| Komponen | Keterangan |
|---|---|
| Perguruan Tinggi | Universitas Muhammadiyah Malang |
| Fakultas | Fakultas Teknik |
| Program Studi | Informatika |
| Mata Kuliah | Temu Kembali Informasi |
| Semester | Ganjil 2026/2027 |
| Dosen Pengampu | Ir. Galih Wasis Wicaksono, S.Kom., M.Cs. |

## Identitas Kelompok

Pengembangan repositori dan pengelolaan dataset dilakukan oleh kelompok mahasiswa:

| No. | Nama Mahasiswa | NIM |
|---|---|---|
| 1. | Muhammad Iqbal Fadel | 202310370311268 |
| 2. | Achmad Rizqy Nur | 202310370311430 |

### Kontribusi Anggota

* Muhammad Iqbal Fadel: Pengembangan skrip web crawler berbasis Python, penelusuran halaman direktori putusan, otomasi pengunduhan berkas PDF, serta ekstraksi teks dan metadata menggunakan ekspresi reguler.
* Achmad Rizqy Nur: Pengumpulan dokumen putusan secara manual melalui direktori putusan, pencatatan metadata manual, serta verifikasi kelengkapan berkas.

## Tujuan dan Ruang Lingkup Dataset

Pengumpulan dataset putusan pengadilan ditujukan untuk memberikan bahan pembelajaran yang kontekstual dalam bidang Information Retrieval, khususnya pada domain hukum yang memiliki karakteristik bahasa formal dan struktur dokumen yang kompleks.

Ruang lingkup dokumen yang dihimpun:
* Jenis Dokumen: Putusan perkara pidana tingkat pertama dalam format Portable Document Format (PDF).
* Kategori Perkara: Pidana Khusus.
* Klasifikasi Perkara: Narkotika dan Psikotropika.
* Lembaga Peradilan: Pengadilan Negeri Batam.
* Sumber Dokumen: Direktori Putusan Mahkamah Agung Republik Indonesia.
* Kriteria Pemilihan: Seluruh dokumen berasal dari satu pengadilan negeri yang sama, tidak menggunakan perkara yang berstatus berkekuatan hukum tetap saat diunduh, dan didominasi oleh perkara dalam rentang tahun 2023 sampai dengan 2025.

## Komposisi Dataset

Dataset final berjumlah tepat 55 dokumen putusan PDF yang bersifat unik tanpa duplikasi:

| Metode Pengumpulan | Jumlah Dokumen | Keterangan |
|---|---:|---|
| Pengumpulan Manual (Tugas 2) | 5 | Diunduh langsung untuk memahami struktur naskah putusan dan komponen metadata awal. |
| Web Crawling (Tugas 3) | 50 | Diunduh secara terotomasi menggunakan crawler untuk memperluas korpus dokumen. |
| Total | 55 | Seluruh dokumen telah divalidasi keunikan nomor perkaranya. |

Perbedaan mendasar dari kedua metode pengumpulan terletak pada perannya: lima dokumen manual digunakan sebagai dasar perancangan pola ekstraksi teks, sedangkan lima puluh dokumen hasil crawling menjadi korpus utama untuk pemrosesan teks berskala lebih besar.

## Metode Pengumpulan Data

Akuisisi dataset dilakukan melalui dua tahapan pengerjaan:

### 1. Pengumpulan Manual (Tugas 2)

Tahap ini dilakukan dengan mengakses Direktori Putusan Mahkamah Agung RI secara langsung melalui peramban web. Pencarian difokuskan pada Pengadilan Negeri Batam dengan klasifikasi Narkotika dan Psikotropika. Sebanyak 5 dokumen putusan diunduh dalam format PDF. Berdasarkan naskah tersebut, dilakukan pembacaan langsung untuk mencatat informasi pokok perkara, meliputi nomor putusan, nama lembaga peradilan, rincian barang bukti, serta amar putusan majelis hakim.

### 2. Web Crawling Terotomasi (Tugas 3)

Pengumpulan lanjutan sebanyak 50 dokumen putusan dilakukan menggunakan skrip web crawler berbasis Python. Alur kerja pengumpulan terotomasi mencakup:
* Penelusuran Halaman: Crawler menelusuri katalog perkara pada direktori putusan Mahkamah Agung secara berurutan untuk menemukan tautan perkara yang sesuai dengan filter Pengadilan Negeri Batam dan klasifikasi Narkotika.
* Akuisisi Berkas: Tautan unduhan diakses secara terprogram untuk mengunduh 50 file PDF putusan secara berurutan dan menyimpannya ke penyimpanan lokal.
* Ekstraksi Teks: Naskah PDF dikonversi menjadi format teks mentah (TXT) guna mempermudah pemrosesan komputasi.
* Ekstraksi Metadata: Skrip memanfaatkan pencocokan pola teks menggunakan regular expression (regex) untuk mengekstrak nomor perkara, lembaga peradilan, barang bukti, amar putusan, nama terdakwa, dan tuntutan hukum.

## Struktur Repository

Struktur direktori repositori disusun sesuai petunjuk penugasan sebagai berikut:

```text
UTS-TemuKembaliCitra/
├── Dataset/
│   └── Narkotika.zip
├── Overview/
│   └── Overview.xlsx
└── README.md
```

### Penjelasan Berkas

* **Dataset/Narkotika.zip**: Berkas arsip terkompresi yang memuat seluruh 55 file PDF putusan pengadilan. Seluruh berkas PDF disimpan langsung di dalam arsip tanpa subfolder tambahan agar mudah diekstrak ke dalam sistem pengindeksan dokumen.
* **Overview/Overview.xlsx**: Berkas spreadsheet yang berisi ringkasan metadata terstruktur dari ke-55 putusan pengadilan yang ada di dalam dataset.
* **README.md**: Dokumentasi komprehensif mengenai identitas akademik, latar belakang, metodologi, komposisi data, serta petunjuk penggunaan repositori.

## Penjelasan Metadata Overview.xlsx

File `Overview.xlsx` menyajikan rekapitulasi informasi dari seluruh 55 dokumen putusan. Informasi disusun secara rapi dengan struktur kolom berikut:

* **No**: Nomor urut dokumen putusan, berurutan dari 1 sampai dengan 55.
* **No Putusan**: Nomor register perkara resmi yang dikeluarkan oleh pengadilan (contoh: 474/Pid.Sus/2023/PN Btm).
* **Lembaga Peradilan**: Nama instansi pengadilan yang memutus perkara, yaitu Pengadilan Negeri Batam.
* **Barang Bukti**: Uraian rincian barang bukti yang disita dalam persidangan, mencakup jenis zat narkotika, berat bruto/netto, telepon genggam, timbangan digital, atau kendaraan.
* **Amar Putusan**: Putusan resmi majelis hakim terhadap terdakwa, meliputi pernyataan bersalah, durasi hukuman pidana penjara, besaran denda subsider, penetapan masa tahanan, serta penetapan status barang bukti (dirampas untuk dimusnahkan atau dirampas untuk negara).

## Validasi dan Integritas Dataset

Seluruh berkas dalam dataset telah melalui serangkaian proses verifikasi teknis untuk menjamin kualitas data sebelum dipublikasikan:

* **Kuantitas Berkas**: Arsip `Narkotika.zip` diverifikasi memuat tepat 55 file dokumen PDF.
* **Integritas Berkas**: Seluruh berkas PDF diperiksa dan dipastikan memiliki header file valid (`%PDF-`), dapat dibuka secara normal, dan tidak mengalami kerusakan berkas.
* **Keunikan Data**: Pengujian irisan nomor perkara antara 5 putusan manual dan 50 putusan crawling menunjukkan tingkat duplikasi 0% (zero overlap). Seluruh 55 perkara merupakan kasus hukum yang berbeda.
* **Konsistensi Data**: Seluruh nomor putusan yang tercatat dalam `Overview.xlsx` berkorespondensi 1 banding 1 dengan naskah PDF padanannya di dalam arsip `Narkotika.zip`.
* **Kelengkapan Metadata**: Seluruh baris data pada `Overview.xlsx` terisi lengkap tanpa nilai kosong pada kolom nomor perkara, lembaga peradilan, barang bukti, dan amar putusan.

## Cara Menggunakan Dataset

Untuk memanfaatkan dataset ini dalam riset atau praktikum temu kembali informasi, ikuti langkah berikut:

1. Buka folder `Dataset` pada repositori ini.
2. Unduh berkas `Narkotika.zip`.
3. Ekstrak arsip ZIP tersebut ke folder kerja lokal komputer Anda.
4. Gunakan dokumen PDF hasil ekstraksi sebagai korpus teks untuk kebutuhan pemrosesan (seperti ekstraksi teks, segmentasi dokumen, tokenisasi, filtering stopword, pembobotan TF-IDF/BM25, dan pengindeksan).
5. Buka berkas `Overview/Overview.xlsx` pada folder `Overview` untuk melihat rekapitulasi metadata perkara sebagai acuan evaluasi pencarian atau filter query.

## Sumber Data dan Referensi

Dataset ini dihimpun secara sah dari sumber resmi:
* Direktori Putusan Mahkamah Agung Republik Indonesia: https://putusan3.mahkamahagung.go.id/direktori.html

Seluruh dokumen yang disertakan merupakan dokumen hukum terbuka yang dipublikasikan oleh Mahkamah Agung untuk transparansi peradilan dan digunakan dalam repositori ini semata-mata untuk tujuan pendidikan dan riset akademik.

## Catatan Akhir

Repositori ini disusun untuk memenuhi evaluasi Ujian Tengah Semester mata kuliah Temu Kembali Informasi di lingkungan Universitas Muhammadiyah Malang. Dataset dan dokumentasi yang disajikan diharapkan dapat menjadi rujukan praktis dalam implementasi temu kembali informasi pada naskah hukum berbahasa Indonesia.

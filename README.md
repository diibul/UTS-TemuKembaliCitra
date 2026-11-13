# Dataset Putusan Pengadilan Kasus Narkotika dan Psikotropika

Repository ini memuat dataset dokumen putusan pengadilan yang dikumpulkan dan dikelola untuk Ujian Tengah Semester (UTS) mata kuliah Temu Kembali Informasi pada Program Studi Informatika, Fakultas Teknik, Universitas Muhammadiyah Malang.

Dataset berfokus pada perkara Pidana Khusus dengan klasifikasi Narkotika dan Psikotropika dari Pengadilan Negeri Batam. Pengumpulan data dilakukan melalui dua pendekatan, yaitu pengunduhan manual dan penelusuran terotomasi menggunakan web crawler pada Direktori Putusan Mahkamah Agung Republik Indonesia.

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

Penyusunan dataset dan repositori ini dilakukan oleh kelompok mahasiswa berikut:

| No. | Nama Mahasiswa | NIM |
|---|---|---|
| 1. | Muhammad Iqbal Fadel | 202310370311268 |
| 2. | Achmad Rizqy Nur | 202310370311430 |

### Kontribusi Anggota

* Muhammad Iqbal Fadel: Perancangan dan implementasi web crawler, pengunduhan terotomasi dokumen putusan, ekstraksi teks serta metadata dari dokumen PDF hasil crawling.
* Achmad Rizqy Nur: Pengumpulan dokumen putusan secara manual melalui direktori putusan, pencatatan metadata manual, dan verifikasi kelengkapan berkas.

## Deskripsi dan Sumber Dataset

Dataset terdiri atas 55 dokumen putusan pengadilan tingkat pertama dalam format PDF. Seluruh dokumen berasal dari lembaga peradilan yang sama, yaitu Pengadilan Negeri Batam, pada klasifikasi perkara Narkotika dan Psikotropika.

Sumber data resmi:
* Direktori Putusan Mahkamah Agung Republik Indonesia: https://putusan3.mahkamahagung.go.id/direktori.html
* Kategori Perkara: Pidana Khusus
* Klasifikasi: Narkotika dan Psikotropika
* Pengadilan: Pengadilan Negeri Batam

### Komposisi Dokumen

Total dokumen yang dihimpun berjumlah 55 berkas putusan yang bersifat unik tanpa duplikasi:

| Metode Pengumpulan | Jumlah Dokumen | Format Berkas | Keterangan |
|---|---:|---|---|
| Pengunduhan Manual | 5 | PDF | Dokumen putusan yang diunduh langsung untuk pengenalan struktur metadata awal. |
| Web Crawling | 50 | PDF | Dokumen putusan yang diperoleh secara terotomasi menggunakan crawler berbasis Python. |
| Total | 55 | PDF | Seluruh dokumen telah melalui verifikasi nomor perkara dan integritas berkas. |

## Struktur Repository

Struktur direktori pada repository ini disusun sesuai format penugasan sebagai berikut:

```text
UTS-TemuKembaliCitra/
├── Dataset/
│   └── Narkotika.zip
├── Overview/
│   └── Overview.xlsx
└── README.md
```

### Penjelasan Komponen

1. **Dataset/Narkotika.zip**  
   Arsip terkompresi yang berisi seluruh 55 file dokumen putusan pengadilan dalam format PDF. Berkas mencakup 5 file dari pengunduhan manual dan 50 file dari hasil web crawling. Seluruh file berada langsung di dalam arsip tanpa subdirektori tambahan untuk memudahkan proses ekstraksi pada sistem temu kembali informasi.

2. **Overview/Overview.xlsx**  
   Buku kerja spreadsheet yang memuat rekapitulasi informasi dan metadata dokumen dari seluruh 55 dokumen putusan. Informasi disusun secara berurutan dan mencakup kolom-kolom berikut:
   * **No**: Nomor urut dokumen (1 sampai dengan 55).
   * **No Putusan**: Nomor register resmi perkara pada pengadilan negeri.
   * **Lembaga Peradilan**: Nama instansi pengadilan yang memutus perkara (Pengadilan Negeri Batam).
   * **Barang Bukti**: Uraian rincian barang bukti yang disita dalam persidangan.
   * **Amar Putusan**: Putusan akhir majelis hakim terhadap terdakwa, meliputi vonis pidana, denda, serta status barang bukti.

3. **README.md**  
   Dokumentasi teknis yang menjelaskan latar belakang proyek, identitas pengelola, komposisi dataset, struktur berkas, dan metodologi pengumpulan data.

## Metode Pengumpulan Data

Proses akuisisi data dilaksanakan melalui dua tahapan berurutan:

1. **Pengunduhan Manual (Tugas 2)**  
   Pengunduhan manual dilakukan terhadap 5 dokumen putusan dari laman Direktori Putusan Mahkamah Agung RI dengan filter Pengadilan Negeri Batam pada klasifikasi Narkotika dan Psikotropika. Tahapan ini bertujuan untuk mengidentifikasi tata letak naskah putusan, struktur bagian pertimbangan hukum, format pencatatan barang bukti, serta pola amar putusan hakim.

2. **Web Crawling Terotomasi (Tugas 3)**  
   Pengumpulan lanjutan dilakukan menggunakan skrip web crawler berbasis Python. Crawler menelusuri halaman daftar perkara pada direktori putusan, mengekstrak tautan berkas unduhan, dan menyimpan 50 dokumen PDF secara berurutan. Setelah dokumen terunduh, proses dilanjutkan dengan ekstraksi teks dan parsing pola teks menggunakan regular expression untuk mengambil data nomor putusan, lembaga peradilan, barang bukti, dan amar putusan secara terstruktur.

## Catatan Integritas Data

Dataset ini disusun untuk kepentingan akademik pada mata kuliah Temu Kembali Informasi. Seluruh dokumen putusan yang digunakan merupakan dokumen hukum terbuka yang dipublikasikan oleh Mahkamah Agung Republik Indonesia. Informasi dalam file Overview.xlsx disusun dengan merujuk pada dokumen putusan PDF dalam dataset.


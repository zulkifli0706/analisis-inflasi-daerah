# Analisis Inflasi 150 Daerah di Indonesia (Januari sampai November 2025)

Analisis pola indeks inflasi bulanan di 150 kota dan kabupaten di Indonesia, dibuat dengan Python di Jupyter Notebook.

## Tujuan Analisis

1. Apakah rata-rata 150 daerah bergerak searah dengan indeks nasional?
2. Seberapa banyak daerah yang mengikuti pola nasional, dan siapa yang menyimpang?
3. Daerah mana yang paling naik turun dan paling tenang?
4. Apakah kabupaten dan kota berbeda?
5. Mana yang lebih berpengaruh: waktu atau tempat?
6. Seberapa sering muncul angka yang sangat tidak biasa?

## Isi Repositori

- `analisis_inflasi_perkab.ipynb`: notebook analisis
- `InflasiUmum.xlsx`: data
- `gambar/`: grafik hasil analisis

## Sumber Data dan Alat

- **Sumber data:** Badan Pusat Statistik (BPS)
- **Cakupan:** 150 kota dan kabupaten, Januari sampai November 2025 (1.650 pengamatan)
- **Alat:** Python, Jupyter Notebook, pandas, matplotlib

## Langkah Pengerjaan

Notebook disusun dalam 7 tahap (0 sampai 6):

0. **Persiapan:** impor `pandas` dan `matplotlib`, atur tampilan grafik, lalu siapkan nama bulan singkat dan fungsi untuk memendekkan nama daerah di grafik.
1. **Memasukkan data:** baca `InflasiUmum.xlsx` (kolom `periode`, `kota`, `index`) apa adanya.
2. **EDA (mengenali data mentah):**
   - Cek struktur kolom, jumlah daerah, jumlah bulan, dan rentang bulan.
   - Cek baris dobel per daerah dan bulan.
   - Cek format angka: kolom `index` memakai koma desimal.
   - Cek nilai kosong: daerah **Dili** kosong di seluruh 11 bulan.
   - Cek baris bernama **INDONESIA**, yang ternyata angka nasional, bukan kota.
3. **Cleaning (memperbaiki 3 masalah dari EDA):**
   - Pilih kolom yang dipakai dan ganti nama (`daerah`, `indeks`).
   - Ganti koma dengan titik, ubah `indeks` ke angka dan `periode` ke tanggal.
   - Pisahkan baris INDONESIA sebagai deret nasional per bulan.
   - Buang Dili (tidak diisi, supaya tidak ada angka karangan) dan baris INDONESIA dari data daerah.
   - Validasi hasil: 150 daerah, 11 bulan, 1.650 baris, tanpa nilai kosong dan tanpa baris dobel.
4. **Preparation (menghitung angka untuk grafik):**
   - Susun tabel lebar (baris = bulan, kolom = daerah).
   - Buat tabel per bulan: indeks nasional, rata-rata dan median daerah, serta jumlah daerah dengan indeks negatif.
   - Buat tabel per daerah: rata-rata, simpangan baku (fluktuasi), jumlah indeks, korelasi dengan nasional, penyimpangan dari nasional, dan jenis daerah.
   - Bandingkan selisih antar bulan dengan selisih antar daerah.
   - Susun peringkat daerah (rata-rata tertinggi/terendah, paling berfluktuasi/stabil).
   - Hitung skor-z per bulan untuk mencari nilai ekstrem (skor-z di atas 3 atau di bawah -3).
   - Ringkas per jenis daerah. Jenis ditentukan dari awalan nama: `KAB` = Kabupaten, `KOTA` = Kota, sisanya = Lainnya.
5. **Visualization (6 kelompok grafik):**
   - Indeks nasional vs rata-rata daerah, dan jumlah daerah negatif per bulan.
   - Histogram korelasi daerah dengan pola nasional (garis batas 0,7).
   - 10 daerah paling menyimpang dari nasional.
   - Sebaran rata-rata vs fluktuasi tiap daerah.
   - Peta panas 15 daerah paling berfluktuasi.
   - Diagram kotak: sebaran antar daerah per bulan, dan fluktuasi menurut jenis daerah.
6. **Kesimpulan:** 5 kesimpulan, implikasi untuk pemantauan, keterbatasan, dan langkah lanjut.

## Hasil, Insight, dan Rekomendasi

### 1. Rata-rata Daerah vs Indeks Nasional
<img width="697" height="442" alt="image" src="https://github.com/user-attachments/assets/75a42a0c-d9f3-4e2f-956e-b9245458a4b3" />

- **Insight:** Rata-rata 150 daerah bergerak hampir sama dengan indeks nasional. Indeks nasional negatif pada Januari, Februari, Mei, dan Agustus. Tertinggi pada Maret (1,65), lalu April (1,17).
- **Rekomendasi:** Indeks nasional bisa dipakai sebagai gambaran awal kondisi mayoritas daerah. Beri perhatian ekstra pada bulan-bulan puncak seperti Maret dan April.

### 2. Korelasi Daerah dengan Pola Nasional
<img width="1007" height="455" alt="image" src="https://github.com/user-attachments/assets/c98f81be-0ef7-4147-aa51-38d6420d8599" />

*Garis putus-putus menunjukkan batas 0,7.*

- **Insight:** 117 dari 150 daerah polanya mirip dengan nasional. Hanya dua yang berlawanan arah: Kab. Jayawijaya dan Kota Batam.
- **Rekomendasi:** Untuk daerah yang mengikuti pola nasional, perubahan nasional bisa jadi peringatan dini. Daerah yang menyimpang, terutama Jayawijaya, perlu dipantau tersendiri.

### 3. Pergerakan Serentak antar Daerah
- **Insight:** Pada Januari, Februari, dan Mei, lebih dari 125 dari 150 daerah ikut turun. Pada Maret, tidak ada satu pun yang turun.
- **Rekomendasi:** Saat indeks nasional berbalik arah, siapkan pemantauan di hampir semua daerah sekaligus, bukan satu per satu.

### 4. Daerah Paling Berfluktuasi dan Paling Tenang
- **Insight:** Paling naik turun: Kab. Gorontalo, Kab. Toli-Toli, dan Kab. Nabire. Paling tenang: Kota Batam. Daerah yang paling berbeda dari nasional: Kab. Jayawijaya.
- **Rekomendasi:** Daerah dengan fluktuasi tinggi dan korelasi rendah (seperti Jayawijaya dan Maluku Tengah) dipantau lebih ketat. Untuk Gorontalo, Toli-Toli, dan Nabire, lihat nilai bulanannya satu per satu karena rata-rata kurang bisa diandalkan.

### 5. Kabupaten vs Kota
- **Insight:** Kabupaten lebih naik turun daripada kota, walaupun rata-rata indeksnya sama.
- **Rekomendasi:** Bedakan cara pemantauan: kabupaten butuh batas toleransi yang lebih lebar dan pengecekan lebih sering.

### 6. Waktu vs Tempat
- **Insight:** Waktu lebih berpengaruh daripada tempat. Indeks nasional berayun 2,41 poin antar bulan, sedangkan rata-rata antar daerah hanya berbeda 0,65 poin.
- **Rekomendasi:** Dahulukan analisis tren waktu sebelum membandingkan antar daerah. Perbedaan antar daerah hanya perlu didalami setelah pengaruh bulan dipisahkan.

### 7. Nilai Ekstrem
- **Insight:** Angka yang sangat tidak biasa jarang, hanya 20 dari 1.650 data. Yang paling mencolok: Kab. Jayawijaya pada Februari (2,78).
- **Rekomendasi:** Cek nilai ekstrem ke sumber lapangan sebelum dipakai untuk kesimpulan.

> Analisis ini menunjukkan pola, bukan penyebabnya.

## Keterbatasan

- Data hanya 11 bulan di tahun 2025, jadi pola musiman belum bisa dipastikan.
- Data tidak memuat kelompok pengeluaran (pangan, energi, dan lainnya), jadi penyebab pola tidak bisa diuji.
- Definisi "indeks" perlu dipastikan dari sumber data. Analisis ini menganggapnya perubahan bulanan.
- Pengelompokan kota dan kabupaten hanya dari awalan nama daerah. Nama tanpa awalan (misalnya Cilacap dan Maumere) masuk kelompok "Lainnya", jadi kelompok ini tidak pasti.
- Daerah Dili dibuang karena tidak punya satu pun data.
- Korelasi dihitung dari 11 titik, jadi hanya ukuran kasar.
- Analisis bersifat deskriptif, tidak ada klaim sebab-akibat.

## Langkah Lanjut

- Tambah data beberapa tahun untuk melihat pola musiman.
- Tambah data kelompok pengeluaran untuk menguji penyebab.
- Tambah data provinsi untuk membandingkan wilayah.

## Cara Menjalankan

1. Simpan file notebook dan data di folder yang sama.
2. Buka Jupyter Notebook, lalu masuk ke folder tadi.
3. Klik `analisis_inflasi_perkab.ipynb`.
4. Pilih menu **Run > Run All Cells**.

Kalau muncul tulisan merah soal file tidak ditemukan, pastikan kedua file ada di folder yang sama.

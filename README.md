Analisis Inflasi 150 Daerah di Indonesia (Januari sampai November 2025)

Analisis pola indeks inflasi bulanan di 150 kota dan kabupaten di Indonesia, dibuat dengan Python di Jupyter Notebook.

Isi
analisis_inflasi_perkab.ipynb: notebook analisis
InflasiUmum.xlsx: data
gambar/: grafik hasil analisis
Sumber data dan alat
Sumber data: Badan Pusat Statistik (BPS), [isi nama tabel atau publikasi], [isi tautan jika ada], diakses [isi bulan dan tahun].
Cakupan: 150 kota dan kabupaten, Januari sampai November 2025 (1.650 pengamatan).
Alat: Python, Jupyter Notebook, [isi pustaka yang dipakai, misalnya pandas dan matplotlib].
Visualisasi

<img width="697" height="442" alt="image" src="https://github.com/user-attachments/assets/75a42a0c-d9f3-4e2f-956e-b9245458a4b3" />

Rata-rata 150 daerah bergerak hampir sama dengan indeks nasional.

<img width="1007" height="455" alt="image" src="https://github.com/user-attachments/assets/c98f81be-0ef7-4147-aa51-38d6420d8599" />

Sebagian besar daerah punya korelasi tinggi dengan pola nasional. Garis putus-putus menunjukkan batas 0,7.

Hasil
Inflasi naik turun bersamaan. Indeks nasional turun (negatif) pada Januari, Februari, Mei, dan Agustus. Indeks tertinggi pada Maret (1,65), lalu April (1,17).
Daerah bergerak kompak. Pada Januari, Februari, dan Mei, lebih dari 125 dari 150 daerah ikut turun. Pada Maret, tidak ada satu pun yang turun.
Sebagian besar daerah mengikuti pola nasional. 117 dari 150 daerah polanya mirip. Hanya dua yang berlawanan arah: Kab. Jayawijaya dan Kota Batam.
Daerah yang paling berbeda dari nasional: Kab. Jayawijaya.
Daerah yang paling naik turun: Kab. Gorontalo, Kab. Toli-Toli, dan Kab. Nabire. Yang paling tenang: Kota Batam.
Kabupaten lebih naik turun daripada kota, walaupun rata-rata indeksnya sama.
Waktu lebih berpengaruh daripada tempat. Perbedaan antar bulan jauh lebih besar daripada perbedaan antar daerah.
Angka yang sangat tidak biasa jarang. Hanya 20 dari 1.650 data. Yang paling mencolok: Kab. Jayawijaya pada Februari (2,78).

Analisis ini menunjukkan pola, bukan penyebabnya.

Kesimpulan
Waktu lebih menentukan daripada lokasi. Indeks nasional berayun 2,41 poin antar bulan, sedangkan rata-rata antar daerah hanya berbeda 0,65 poin.
Polanya serentak. Empat bulan negatif pada tingkat nasional. Pada tiga di antaranya, sedikitnya 125 daerah ikut negatif. Pada Maret, tidak ada satu pun.
Sebagian kecil daerah bergerak sendiri. 117 dari 150 daerah mengikuti pola nasional. Kab. Jayawijaya menyimpang paling jauh, dan Kota Batam bergerak paling kecil dibanding daerah lain.
Fluktuasi lebih tinggi di kabupaten. Perbedaan kota dan kabupaten ada di fluktuasi, bukan di rata-rata.
Nilai ekstrem jarang tetapi nyata. 20 dari 1.650 pengamatan, dengan Jayawijaya (Februari) sebagai yang paling ekstrem.
Implikasi untuk pemantauan
Daerah dengan fluktuasi tinggi dan korelasi rendah, seperti Jayawijaya dan Maluku Tengah, perlu dipantau lebih ketat daripada daerah lain.
Daerah dengan fluktuasi tertinggi, seperti Gorontalo, Toli-Toli, dan Nabire, sulit dipantau dengan angka rata-rata. Nilai bulanannya perlu dilihat satu per satu.
Nilai ekstrem perlu dicek ke sumber lapangan sebelum dipakai untuk kesimpulan.
Karena pola nasional kuat, perubahan di tingkat nasional bisa dipakai sebagai peringatan dini untuk sebagian besar daerah.
Keterbatasan
Data hanya 11 bulan di tahun 2025, jadi pola musiman belum bisa dipastikan.
Data tidak memuat kelompok pengeluaran (pangan, energi, dan lainnya), jadi penyebab pola tidak bisa diuji.
Definisi "indeks" perlu dipastikan dari sumber data. Analisis ini menganggapnya perubahan bulanan.
Pengelompokan kota dan kabupaten hanya dari nama daerah.
Korelasi dihitung dari 11 titik, jadi hanya ukuran kasar.
Analisis bersifat deskriptif. Tidak ada klaim sebab-akibat.
Langkah lanjut

Tambah data beberapa tahun untuk melihat pola musiman, tambah data kelompok pengeluaran, dan tambah data provinsi untuk membandingkan wilayah.

Cara membuka
Simpan file notebook dan data di folder yang sama.
Buka Jupyter Notebook, lalu masuk ke folder tadi.
Klik analisis_inflasi_perkab.ipynb.
Pilih menu Run > Run All Cells.

Kalau muncul tulisan merah soal file tidak ditemukan, pastikan kedua file ada di folder yang sama.

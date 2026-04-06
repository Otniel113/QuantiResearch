# QuantiResearch
Beberapa olah dan analisis data penelitian pendekatan kuantitatif menggunakan statistika inferensial untuk uji hipotesis menggunakan Python.

## Direktori atau Folder
1. 01-Simple = Hanya untuk data 2 kolom saja (X dan Y), biasanya menggunakan data sekunder atau data dari internet.
2. 02-Advance = Menggunakan data banyak kolom, biasanya menggunakan data primer yang didapatkan dari sebar survei atau kuesioner.

## Uji yang Dilakukan dan Data
Kondisi data yang digunakan adalah kondisi data ideal yang mana lolos semua uji, mulai dari Uji Validitas dan Relibialitas (untuk data di 02-Advance), Uji Asumsi Klasik (seperti Uji Normalitas, Linearitas, dsb.), dan Uji Hipotesis (Signifikansi). Pada praktiknya, bisa saja ada kondisi uji tidak lolos sehingga perlu melakukan tindakan lebih lanjut (seperti membuang kolom, mengganti uji ke non-parametrik, dsb). Untuk mempermudah, semua data di sini adalah data ideal.

## Metode
Metode yang dilakukan untuk Uji Hipotesis antara lain:
1. Regresi Linear: Untuk mengetahui X mempengaruhi Y.
2. Korelasi: Untuk mengetahui hubungan X dan Y tanpa mementingkan sebab-akibat.
3. Paired T-Test: Untuk melihat perbedaan rata-rata 2 kelompok, bisa karena pre-test/post-test, atau eksperimen perlakuan ke dua kelompok berbeda.

Uji-uji tersebut adalah yang paling sering digunakan. Pemilihan uji tersebut tergantung dari jenis data yang dimiliki. Beberapa uji lain yang tidak ada di sini adalah:
1. ANOVA: Mirip Paired T-Test tapi untuk melihat perbedaan rata-rata 3 atau lebih kelompok.
2. Chi-Test: Untuk data kategorikal, misalkan apakah Jenis Kelamin (L/P) mempengaruhu pembelian merk HP tertentu.
3. Regresi Logistik: Jika Y bernilai kategorikal/nominal seperti Iya/1 atau Tidak/0.
4. Uji Non-Parametrik: Jika Uji Normalitas tidak lolos.
# QuantiResearch
Beberapa olah dan analisis data penelitian pendekatan kuantitatif menggunakan statistika inferensial untuk uji hipotesis dalam bahasa Python.

## Direktori atau Folder
1. 01-Simple = Hanya untuk data 2 kolom saja (X dan Y), biasanya menggunakan data sekunder atau data dari internet.
2. 02-Advanced = Menggunakan data banyak kolom, biasanya menggunakan data primer yang didapatkan dari sebar survei atau kuesioner.

## Uji Asumsi Klasik yang Dilakukan
Uji Asumsi Klasik dilakukan sebagai persyaratan sebelum melakukan Uji Hipotesis. Hal ini agar dapat memilih metode uji hipotesis yang tepat sesuai data dan juga hasil uji asumsi klasik. Uji Asumsi Klasik seperti Uji Normalitas, Uji Linearitas, dsb..

Pada data survei atau kuesioner, perlu dilakukan Uji Validitas dan Reliabilitas terlebih dahulu.

## Metode Uji Hipotesis
Metode yang dilakukan untuk Uji Hipotesis antara lain:
1. Regresi Linear: Untuk mengetahui X mempengaruhi Y.
2. Korelasi: Untuk mengetahui hubungan X dan Y tanpa mementingkan sebab-akibat.
3. Paired T-Test: Untuk melihat perbedaan rata-rata 1 kelompok tapi dalam 2 waktu berbeda, seperti before-after.

Uji-uji tersebut adalah yang paling sering digunakan. Pemilihan uji tersebut tergantung dari jenis data yang dimiliki. Beberapa uji lain yang tidak ada di sini adalah:
1. Independent T-Test: Untuk melihat perbedaan rata-rata 2 kelompok berbeda.
2. ANOVA: Mirip Independent T-Test tapi untuk melihat perbedaan rata-rata 3 atau lebih kelompok.
3. Chi-Test: Untuk data kategorikal, misalkan apakah Jenis Kelamin (L/P) mempengaruhu pembelian merk HP tertentu.
4. Regresi Logistik: Jika Y bernilai kategorikal/nominal seperti Iya/1 atau Tidak/0.
5. Uji Non-Parametrik: Jika Uji Normalitas tidak lolos.

## Penjelasan File
Direkomendasikan untuk lebih dahulu mempelajari dan melihat folder `01-Simple` sebelum ke `02-Advanced`

### 01-Simple
#### Simple-Korelasi
*   **Tujuan**: Mencari hubungan, arah, dan besar korelasi antara suhu rata-rata dengan kelembaban relatif.
*   **Hipotesis**: H0 (Tidak ada hubungan) vs H1 (Ada hubungan).
*   **Data**: Data sekunder dari BMKG Stasiun Halim Perdana Kusuma (Januari - Maret 2026).
*   **Jawaban**: Terdapat hubungan negatif yang kuat (koefisien -0.83) dan signifikan. Artinya, jika suhu naik, maka kelembaban cenderung turun secara signifikan.

#### Simple-Paired T Test
*   **Tujuan**: Mengukur efektivitas webinar dengan membandingkan rata-rata nilai pretest dan posttest peserta yang sama.
*   **Hipotesis**: H0 (Tidak ada perbedaan rata-rata) vs H1 (Ada perbedaan rata-rata).
*   **Data**: Data primer dari kuesioner sebelum dan sesudah kegiatan pengabdian masyarakat.
*   **Jawaban**: Terdapat peningkatan rata-rata nilai sebesar 10.12 (dari 70.83 ke 80.95) dengan p-value 0.0009. Hal ini menunjukkan webinar memberikan pengaruh signifikan terhadap pemahaman peserta.

#### Simple-Regresi Linear
*   **Tujuan**: Menganalisis apakah durasi (length) sebuah visual novel mempengaruhi rating yang diberikan pengguna.
*   **Hipotesis**: H0 (Tidak ada pengaruh) vs H1 (Ada pengaruh).
*   **Data**: Data hasil query SQL dari VNDB (visual novel database).
*   **Jawaban**: Durasi berpengaruh positif dan signifikan terhadap rating. Setiap kenaikan 1% durasi meningkatkan rating sebesar 0.0656%, dengan nilai R-Squared 0.404 (durasi menjelaskan 40.4% variasi rating).

### 02-Advanced
#### Advanced-Regresi Linear X dan Y
*   **Tujuan**: Menganalisis pengaruh variabel independen X (yang terdiri dari beberapa dimensi/sub-variabel X1, X2, X3) terhadap variabel dependen Y.
*   **Hipotesis**: H0 (Tidak ada pengaruh) vs H1 (Ada pengaruh).
*   **Data**: Data dummy (200 responden) dengan skala Likert 1-5, mencakup uji validitas dan reliabilitas instrumen survei.
*   **Jawaban**: Variabel X secara keseluruhan berpengaruh signifikan dan positif terhadap Y (Adj. R-Squared: 0.435). Dimensi X1 ditemukan memiliki pengaruh paling kuat dibandingkan X2 dan X3.

#### Advanced-Regresi Linear X, Xm, Y
*   **Tujuan**: Menguji pengaruh variabel X terhadap Y, pengaruh variabel moderasi Xm terhadap Y, serta apakah Xm memoderasi hubungan antara X dan Y (Moderated Regression Analysis).
*   **Hipotesis**: H0 (Tidak ada pengaruh/moderasi) vs H1, H2, H3 (Ada pengaruh/moderasi).
*   **Data**: Data dummy (131 responden) dengan skala Likert, menggunakan teknik *mean centering* untuk variabel moderasi.
*   **Jawaban**: Xm berpengaruh signifikan terhadap Y, namun interaksi (X*Xm) tidak signifikan (p-value 0.314). Artinya, Xm bertindak sebagai variabel independen tambahan, bukan sebagai pemoderasi hubungan X ke Y.

#### Advanced-Regresi Linear X1, X2, Y
*   **Tujuan**: Menganalisis pengaruh parsial X1 dan X2 terhadap Y, serta pengaruh keduanya secara simultan.
*   **Hipotesis**: H0 (Tidak ada pengaruh) vs H1 (X1->Y), H2 (X2->Y), H3 (X1,X2->Y).
*   **Data**: Data dummy (123 responden) dengan skala Likert.
*   **Jawaban**: Baik X1 maupun X2 berpengaruh signifikan dan positif terhadap Y secara parsial maupun simultan (Adj. R-Squared: 0.443). X1 memiliki konstribusi pengaruh yang lebih kuat dibandingkan X2.
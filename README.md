# loan_prediction
Classification Model for Loan Prediction to Decrease of Potential Loss
## Latar Belakang Masalah
 1. Sebuah Bank mengalami kerugian akibat 12.3% nasabah nya tidak dapat mengembalikan pinjaman
 2. Jika dirata-rata pinjaman di India ₹20.000, maka kerugian sekitar ₹620jt. Atau sekitar 119 Milyar Rupiah.
 3. Perlu adanya model yang dapat mempelajari ciri-ciri nasabah yang mengalami kredit macet.
## Tujuan
 1. Menurunkan kemungkinan kerugian perusahaan.
 2. Mem-filter nasabah yang berkemungkinan gagal bayar dan lancar.
 3. Mencari faktor-faktor yang menyebabkan orang bisa gagal bayar
## Gambaran Data
 1. Data memiliki 1 label Risk_Flag, dan 11 features yang terdiri dari 5 kolom numerik, dan 6 kolom bertipe data kategori.
 2. Data terdiri dari 252,000 baris.
 3. Data memuat data diri nasabah seperti keterangan pendapatan, umur, pekerjaan, status tempat tinggal dll.
## Analisis Data
 1. Debitur terbanyak terdapat di kategori usia aktif, yaitu young age, middle age dan eldery
 ![enter image description here](https://i.postimg.cc/yYNZPGHX/Untitled-design.png)
 2. Debitur dengan status single memiliki potensi gagal bayar yang lebih tinggi daripada status married
 ![enter image description here](https://i.postimg.cc/6pxJLksy/Untitled-design-1.png)
 3. Debitur yang masih berstatus tempat tinggal sewa memiliki resiko gagal bayar paling tinggi
 ![enter image description here](https://i.postimg.cc/d1nv14D4/Untitled-design-2.png)
## Pemrosesan Data
 1. Seluruh data numerik di standarisasi, tujuannya agar saat dimasukan kedalam model data memiliki besaran secara adil.
 2. Variable kategorikal Married/Single dan Car_Ownership dilakukan label encoding menggunakan fungsi map.
 3. Kolom House_Ownership kita lakukan One Hot Encoding
 4. Untuk variable yang high cardinal data, kami rubah menggunakan metode frekuensi. Agar tidak kehilangan informasi dari feature ini, maka feature ini tetap kami bawa untuk model.
 5. Mengatasi data imbalance, kami melakukan teknik SMOTE pada feature kategorikal. Ini bertujuan agar model tidak ‘diskriminatif’ dalam menentukan hasil prediksi nantinya.
 6. Data kita pisah menjadi train set dan test set dengan perbandingan 70:30.
## Pemodelan dan Evaluasi 
Kami mencoba 5 algoritma yaitu, Logistic Regression, Decision Tree, Random Forest, XGBoost dan CatBoost.
![enter image description here](https://i.postimg.cc/G35JNDjy/Untitled-design-3.png)
Pada percobaan ini CatBoost memiliki nilai evaluasi tertinggi dengan Precission dan AUC di 0.91 dan 0.96. Dengan angka ini kami mengambil model CatBoost untuk mendeteksi nasabah yang berkemungkinan gagal bayar.
## Wawasan Bisnis dan Rekomendasi
 1. Dari analisa feature importance dan EDA, dapat disimpulakan bahwa lokasi merupakan faktor yang menjadi risk flag pada debitur. Bank dapat membuat **produk khusus** yang disegmentasikan berdasarkan lokasi debitur (cth : limit rendan dan payback fleksibel untuk debitur yang berlokasi di kota-kota besar)
 2. Memberikan diskon pembayaran atau bonus limit untuk debitur yang membayar tepat waktu (**reward system**).
 3. Memberlakukan **sistem deposit** untuk pinjaman dengan nilai 10% dari pendapatan debitur
 4. **Mengidentifikasi dari awal** debitur-debitur yang mempunyai risk flag yang signifikan (berdasarkan feature importance : pendapatan, umur dan lokasi) , agar dapat diarahkan untuk mengambil produk pinjaman khusus.
 5. Selalu **stay in touch** dengan debitur yang telah mengambil pinjaman dengan memberikan info promosi dan reward pada produk pinjaman yang telah mereka ambil.





 


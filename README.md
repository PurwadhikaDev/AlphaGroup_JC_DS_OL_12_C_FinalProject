**Final Project**

- Angga Fernando Putra, Dewi Maharani Dyah Pitaloka, Rian Pratama Putra
- Theme : Ecommerce Customer Churn

# Business Problem Understanding
**Latar Belakang**


Sebuah perusahaan yang bergerak dibidang e-commerce menghadapi berbagai tantangan untuk tetap mempertahankan atau bahkan meningkatkan revenue. Tantangan tersebut diantaranya adalah **meningkatkan retensi pelanggan** karena ditemukannya sejumlah pelanggan yang berhenti bertransaksi. Maka dari itu perusahaan ingin mengetahui pelanggan mana sajakah yang terindikasi akan berhenti bertransaksi serta memahami karakteristik pelanggan dalam bertransaksi. Sehingga perusahaan dapat membuat kebijakan yang tepat dan efisien untuk mengatasi tantangan yang ada.


**Rumusan Masalah :**

Permasalahan yang perlu diatasi adalah **bagaimana upaya perusahaan dalam meningkatkan retensi pelanggan secara efektif dan efisien**. **Adapun untuk meningkatkan retensi pelanggan dapat dilakukan dengan mencegah pelanggan untuk churn**. Hal tersebut menjadi penting mengingat perbandingan biaya yang diperlukan untuk mendapatkan **pelanggan baru adalah 5 kali lebih besar dibanding biaya yang dibutuhkan untuk mempertahankan pelanggan yang ada**. Namun bila seluruh sumber daya digunakan untuk semua pelanggan tanpa membedakan pelanggan yang akan churn atau tidak, maka penggunaan sumber daya tidak akan efektif dan efisien. 

Target :

0 : Pelanggan yang masih bertransaksi/tidak churn

1 : Pelanggan yang berhenti bertransaksi/churn

**Goal :**

Untuk dapat menjawab permasalahan yang ada maka tujuan dari proyek ini yaitu : 

- Untuk **memahami karakteristik pelanggan yang berpotensi akan churn** sehingga kebijakan yang dibuat dapat lebih terarah. Adapun business questions atau pertanyaan bisnis yang perlu dijawab untuk dapat memahami karakteristik pelanggan tersebut diantaranya :

    1. Bagaimana karakteristik pelanggan berdasarkan **informasi personalnya** (jenis kota, status pernikahan, kelamin, jenis perangkat, jenis pembayaran, jenis produk favorit dan durasi penggunaan aplikasi/web aplikasi) ?

    2. Bagaimana karakteristik pelanggan berdasarkan **tingkat kepuasannya** (rating, keluhan) ?

    3. Bagaimana karakteristik pelanggan berdasarkan **riwayat transaksi & promosi** yang didapatkan (lamanya terdaftar, peningkatan jumlah pembelian, jumlah pembelian, penggunaan kupon, penerimaan cashback, jumlah hari setelah hari terakhir pembelian) ?

- Selain itu perusahaan juga ingin **memiliki kemampuan untuk memprediksi pelanggan yang akan churn** sehingga perusahaan khususnya tim marketing dapat membuat strategi untuk meningkatkan retensi pelanggan secara efektif dan efisien.


**Pendekatan Analisis :**

Melakukan analisis data untuk menemukan **karakteristik pelanggan yang berpotensi akan churn**. Selanjutnya adalah **membuat model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi** kemungkinan pelanggan akan churn atau tidak.


**Metrik Evaluasi :**

Sebelum menentukan metrik evaluasi yang akan digunakan, sebaiknya perlu memperhatikan jenis _erorr_ yang dapat timbul dari pemodelan prediksi yaitu :

**False Positive**  : Pelanggan yang diprediksi akan berhenti melakukan transaksi tetapi kenyataannya tetap bertransaksi. Konsekuensinya adalah alokasi sumber daya yang tidak efektif dan efisien (contoh = pemberian diskon tidak tepat sasaran mengakibatkan sumber daya terbuang sia-sia).

**False Negative**  : Pelanggan yang diprediksi akan tetap melakukan transaksi tetapi kenyataannya berhenti bertransaksi. Konsekuensinya adalah kehilangan jumlah pelanggan yang akan berdampak pada penurunan revenue.

Karena fokus perusahaan adalah mempertahankan pelanggan secara efektif dan efisien dimana **meminimalisir false positive dan false negative sekecil mungkin tetapi lebih difokuskan pada recall** maka metrik yang digunakan adalah **f2-score**.

untuk gambaran kuantitatifnya secara umum adalah :
- Costumer Acquisition Cost (CAC) berdasarkan referensi https://firstpagesage.com sebesar 65 USD per orang<sup>[1]</sup>,
- Costumer Retention Cost (CRC) berdasarkan https://www.forbes.com bisa berkisar 20% dari CAC<sup>[2]</sup>, maka simulasi untuk CRC adalah :   20% dari 65 USD (CAC) = 13 USD per pelanggan.

Adapun pengertian dari tiap-tiap metrik evaluasi model klasifikasi yaitu :
- **F1-Score** : ukuran yang menggabungkan Precision dan Recall menjadi satu angka tunggal. Ini memberikan gambaran keseluruhan tentang kinerja model dalam mengklasifikasikan kelas positif, dengan mempertimbangkan baik false positives maupun false negatives.
- **F2-Score** : ukuran yang menggabungkan Precision dan Recall menjadi satu angka tunggal tetapi lebih ditekankan pada Recall.
- **Recall** : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan data yang benar positif. Ini berguna ketika Anda ingin meminimalkan false negatives.
- **Precision** : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan data yang diprediksi positf. Ini berguna ketika Anda ingin meminimalkan false positives.

# Kesimpulan dan Rekomendasi

## Kesimpulan

**Berdasarkan data analisis yang telah dilakukan, maka didapatkan kesimpulan atas pertanyaan bisnis yang ada :**

1. Bagaimana karakteristik pelanggan berdasarkan **informasi personalnya** (jenis kota, status pernikahan, kelamin, jenis perangkat, jenis pembayaran, jenis produk favorit, durasi penggunaan aplikasi/web app) ? Pelanggan yang lebih cenderung churn adalah :

- Pelanggan yang berlokasi di city tier 3,
- Pelanggan yang berstatus sudah lajang,
- Pelanggan yang menggunakan perangkat Komputer,
- Pelanggan yang menggunakan COD,
- Pelanggan yang berbelanja produk berjenis Mobile Phone,
- Adapun hal yang tidak berpengaruh yaitu _gender_ dan durasi penggunaan aplikasi/web app.

2. Bagaimana karakteristik pelanggan berdasarkan **tingkat kepuasannya** (rating, keluhan) ? Pelanggan yang lebih cenderung churn adalah :

- Tidak ada pengaruh rating dalam keputusan pelanggan (indikasi fitur rating tidak berjalan dengan baik),
- Pelanggan yang pernah memberikan keluhan.

3. Bagaimana karakteristik pelanggan berdasarkan **riwayat transaksi & promosi yang didapatkan** (lamanya terdaftar, peningkatan jumlah pembelian, jumlah pembelian, penggunaan kupon, penerimaan cashback, jumlah hari setelah hari terakhir pembelian) ? Pelanggan yang lebih cenderung churn adalah :

- Pelanggan yang baru daftar,
- Pelanggan yang memiliki jumlah peningkatan pembelian dari tahun sebelumnnya rendah,
- Pelanggan yang mendapatkan cashback lebih rendah,
- Adapun hal yang tidak berpengaruh yaitu jumlah penggunaan kupon, jumlah pembelian dan jumlah hari setelah hari terakhir belanja.


**Berdasarkan hasil modeling didapatkan kesimpulan sebagai berikut :**

1. Model dengan performa terbaik dalam melakukan prediksi berdasarkan hasil uji coba dengan dataset ini adalah XGBoost.

2. Resampler terbaik pada pemodelan menggunakan dataset ini adalah dengan metode SMOTE dikarenakan menghasilkan rata-rata f2 score lebih baik dari metode Random Undersampling untuk semua model.

3. Model terpilih yaitu XGBoost yang mendapatkan peningkatan performa setelah dilakukan hyperparameter tuning. Parameter hasil tuning adalah sebagai berikut : subsample = 0.9686, n_estimators = 198, max_depth = 8, learning_rate = 0.10712.

4. Kita harus berhati-hati ketika melakukan interpretasi di luar interval independen variabel. Model ini hanya berlaku pada rentang data yang digunakan dengan limitasi Model adalah sebagai berikut :

| Feature | Data Type | Description |
| --- | --- | --- |
| Tenure | Float | Tenure pelanggan berkisar 0-31 bulan |
| PreferredLoginDevice | Text | Perangkat yang digunakan : Mobile Phone, Computer |
| CityTier | Int | City tier : 1,2,3 |
| WarehouseToHome | Float | Jarak tempuh pelanggan berkisar 5-36 KM |
| PreferredPaymentMode | Text | Tipe pembayaran pelanggan yaitu : Debit Card, UPI, Credit Card, Cash on Delivery, E wallet |
| NumberOfDeviceRegistered | Int | Jumlah perangkat yang didaftarkan berkisar 1-6 perangkat |
| PreferedOrderCat | Text | Jenis produk yang dijual terbatasi pada : Laptop & Accessory, Mobile Phone, Others, Fashion, Grocery |
| SatisfactionScore | Int | Rating dibatasi dari skor 1 - 5 |
| MaritalStatus | Text | Status pernikahan terdiri dari : Lajang, Cerai, Menikah |
| Complain | Int | Pernah melakukan complain [1] atau tidak [0] |
| OrderAmountHikeFromlastYear | Float | Persentase kenaikan jumlah pembeli berkisar 11-26 % |
| DaySinceLastOrder | Float | Pelanggan tidak melakukan belanja tidak lebih dari 46 hari |
| CashbackAmount | Float | rata-rata cashback yang diterima berkisar 0-300 USD |

## Rekomendasi

**Berdasarkan data analisis yang telah dilakukan, diberikan rekomendasi agar dapat meningkatkan retensi pelanggan :**

- Sebaiknya lebih difokuskan untuk approach kepada **pelanggan yang berada di lokasi city tier 3** karena merupakan wilayah dengan **pelanggan terbanyak urutan ke-2** tetapi churn rate-nya paling tinggi. Rekomendasi yang dapat diberikan adalah **menawarkan insentif khusus berupa memberikan voucher untuk setiap pembelian yang dapat ditukar dengan barang atau layanan khususnya pada produk yang cenderung diminati seperti produk Laptop & Accessory**. Selain itu dapat juga **menawarkan penggabungan promosi apabila menggunakan sistem pembayaran E-Wallet** mengingat sistem pembayaran ini adalah yang paling diminati pada City Tier 3.
- Sebaiknya lebih difokuskan untuk approach kepada pelanggan yang masih **berstatus lajang** karena merupakan **pelanggan terbanyak urutan ke-2** tetapi churn rate-nya paling tinggi. Adapun rekomendasi yang dapat diberikan seperti **membuat program 'single day' dimana diadakan bazzar dan promo besar-besar untuk hari tertentu apabila membeli produk tertentu secara satuan**.
- Sebaiknya dilakukan perbaikan terkait akses dan atau sistem web-aplikasi sehingga dapat meningkatkan minat pelanggan yang selama ini melakukan akses platform e-commerce menggunakan **PC/Computer yang memiliki churn rate tinggi**. Rekomendasi yang dapat diberikan yaitu **melakukan survey lebih lanjut untuk web-aplikasi apakah terdapat masalah** UI/UX seperti kemungkinan tampilan yang tidak ramah, kerumitan dalam penggunaan, akses yang sulit dibuka ataupun masalah lainnya yang membuat pelanggan kurang berminat. **Selanjutnya dilakukan perbaikan terkait akses dan atau sistem web-aplikasi sehingga dapat meningkatkan minat pelanggan**.
- Sebaiknya dilakukan perbaikan terkait sistem pembayaran menggunakan **sistem COD karna sistem COD memiliki churn rate tinggi**. Rekomendasi yang dapat diberikan yaitu **perlu diadakan survey lebih lanjut terkait pembayaran dengan metode ini untuk monitoring dan evaluasi lalu dilakukan tindaklanjut berupa perbaikan sistem.**
- Sebaiknya difokuskan terhadap jenis produk **Mobile Phone yang memiliki churn rate yang tinggi**. Rekomendasi yang dapat diberikan adalah **memberikan program khusus terkait produk Mobile Phone seperti penawaran diskon untuk produk aksesoris terkait atau program promosi berkelanjutan seperti program trade-in** yaitu pemberian diskon untuk produk tertentu ketika ingin melakukan upgrade produk untuk tahun-tahun yang akan datang.
- Perlu dilakukan **perbaikan/perubahan terhadap sistem rating/feedback/review** yang sedang digunakan lalu di lakukan testing untuk setiap jenisnya/perubahannya dan dicari hasil sistem yang terbaik.
- Perlu melakukan penanganan terhadap keluhan pelanggan yang telah disampaikan. Disarankan untuk **memulai perbaikan terkait keluhan tersebut, dengan mengkategorikan dan memberikan prioritas**. Selanjutnya, penting untuk **meninjau kembali SLA (Service Level Agreement)** terkait tingkat layanan yang diharapkan
- Apabila perusahaan menggunakan model maka biaya yang dapat **dihemat perusahaan sekitar 10348 USD per 1000 pelanggan atau sekitar 10.348 USD per pelanggan**, yang mana itu adalah **penghematan sebesar 78,5%** dibanding tidak menggunakan model.

**Berdasarkan Pemodelan yang sudah dilakukan, diberikan rekomendasi agar performa model dapat bekerja dengan lebih baik dan membantu perusahaan dalam mengatasi retensi pelanggan :**

1. Untuk kedepannya disarankan untuk mengembangkan model machine learning terkait segmentasi sehingga lebih memudahkan tim marketing dalam membuat program kampanye dan promosi. Selain itu perlu dilakukan pembuatan model klasifikasi terpisah berdasarkan data produk konsumsi harian dan produk konsumsi bukan harian agar lebih akurat dan logis.

2. Untuk efisien pemodelan ada baiknya menghapus fitur-fitur yang tidak terlalu berpengaruh berdasarkan hasil features importances terhadap model seperti fitur 'WarehouseToHome', 'Gender', 'HourSpendOnApp', 'OrderAmountHikeFromlastYear', 'CouponUsed' dan juga terdapat fitur yang sebenarnya tidak terlalu berpengaruh seperti 'DaySinceLastOrder'.

3. Memperbanyak jumlah data pelanggan sehingga model lebih baik dalam membedakan pelanggan churn atau tidak,

4. Memperbanyak jumlah fitur atau kolom baru yang berhubungan dengan potensi pelanggan untuk churn berdasarkan domain knowledge.

5. Menambah uji coba modelling seperti menggunakan metode resampling lainnya,

6. Menghindari data redundan dan data kosong pada tahap data acquisition sehingga lebih mudah ketika proses data cleaning.

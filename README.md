**Final Project**

- Angga Fernando Putra, Dewi Maharani Dyah Pitaloka, Rian Pratama Putra
- Theme : Ecommerce Customer Churn

# Business Problem Understanding
**Latar Belakang**


Sebuah perusahaan yang bergerak dibidang e-commerce menghadapi berbagai tantangan untuk tetap mempertahankan atau bahkan meningkatkan revenue. Tantangan tersebut diantaranya adalah **meningkatkan retensi pelanggan** karena ditemukannya sejumlah pelanggan yang berhenti berlangganan. Maka dari itu perusahaan ingin mengetahui pelanggan mana sajakah yang terindikasi akan berhenti berlangganan serta memahami karakteristik pelanggan dalam bertransaksi. Sehingga perusahaan dapat membuat kebijakan yang tepat dan efisien untuk mengatasi tantangan yang ada.


Target :

0 : Pelanggan yang masih berlangganan/tidak churn

1 : Pelanggan yang berhenti berlangganan/churn

**Rumusan Masalah :**

Permasalahan yang perlu diatasi adalah **bagaimana upaya perusahaan dalam meningkatkan retensi pelanggan secara efisien dan efektif**. Apabila seluruh sumber daya digunakan untuk semua pelanggan tanpa membedakan pelanggan yang akan churn atau tidak maka penggunaan sumber daya tidak akan efisien dan efektif.


**Goal :**

Untuk dapat menjawab permasalahan yang ada maka tujuan dari proyek ini yaitu : 

- Untuk **memahami karakteristik pelanggan yang berpotensi akan churn** sehingga kebijakan yang dibuat dapat lebih terarah. Adapun business questions atau pertanyaan bisnis yang perlu dijawab untuk dapat memahami karakteristik pelanggan tersebut diantaranya :

    1. Bagaimana karakteristik pelanggan berdasarkan **informasi personalnya** (jenis kota, status pernikahan, kelamin, jenis perangkat, jenis pembayaran, jenis produk favorit dan durasi penggunaan aplikasi/web aplikasi) ?

    2. Bagaimana karakteristik pelanggan berdasarkan **tingkat kepuasannya** (rating, keluhan) ?

    3. Bagaimana karakteristik pelanggan berdasarkan **riwayat transaksi & promosi** yang didapatkan (lamanya berlangganan, peningkatan jumlah pembelian, jumlah pembelian, penggunaan kupon, penerimaan cashback, jumlah hari setelah hari terakhir pembelian) ?

- Selain itu perusahaan juga ingin **memiliki kemampuan untuk memprediksi pelanggan yang akan churn** sehingga perusahaan dapat membuat kebijakan untuk meningkatkan retensi pelanggan secara efisien dan efektif.


**Pendekatan Analisis :**

Melakukan analisis data untuk menemukan **karakteristik pelanggan yang berpotensi akan churn**. Selanjutnya adalah **membuat model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi** kemungkinan pelanggan akan churn atau tidak.


**Metrik Evaluasi :**

Sebelum menentukan metrik evaluasi yang akan digunakan, sebaiknya perlu memperhatikan jenis eror yang dapat timbul dari pemodelan prediksi yaitu :

**False Positive**  : Pelanggan yang diprediksi akan berhenti melakukan transaksi tetapi kenyataannya tetap bertransaksi. Konsekuensinya adalah alokasi sumber daya yang tidak efektif dan efisien (contoh = pemberian diskon tidak tepat sasaran mengakibatkan sumber daya terbuang sia-sia).

**False Negative**  : Pelanggan yang diprediksi akan tetap melakukan transaksi tetapi kenyataannya berhenti bertransaksi. Konsekuensinya adalah kehilangan jumlah pelanggan yang akan berdampak pada penurunan revenue.

Karena fokus perusahaan adalah mempertahankan pelanggan secara efisien dan efektif dimana **meminimalisir false positive dan false negative sekecil mungkin dan tetap seimbang** maka metrik yang digunakan adalah **f1-score**.

untuk gambaran kuantitatifnya secara umum adalah :
- Costumer Acquisition Cost (CAC) berdasarkan referensi https://firstpagesage.com sebesar 65 USD per orang<sup>[1]</sup>,
- Costumer Retention Cost (CRC) berdasarkan https://www.forbes.com bisa berkisar 20% dari CAC<sup>[2]</sup>, maka simulasi untuk CRC adalah :   20% dari 65 USD (CAC) = 13 USD per pelanggan, maka perkiraan kerugian perusahaan untuk pelanggan churn sebesar : 13 USD per pelanggan.


Adapun pengertian dari tiap-tiap metrik evaluasi model klasifikasi yaitu :
- **F1-Score** : ukuran yang menggabungkan Precision dan Recall menjadi satu angka tunggal. Ini memberikan gambaran keseluruhan tentang kinerja model dalam mengklasifikasikan kelas positif, dengan mempertimbangkan baik false positives maupun false negatives.
- **Recall** : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan data yang benar positif. Ini berguna ketika Anda ingin meminimalkan false negatives.
- **Precision** : merupakan rasio prediksi benar positif dibandingkan dengan keseluruhan data yang diprediksi positf. Ini berguna ketika Anda ingin meminimalkan false positives.

# Kesimpulan dan Rekomendasi

## Kesimpulan

**Berdasarkan data analisis yang telah dilakukan, maka didapatkan kesimpulan atas pertanyaan bisnis yang ada :**

1. Bagaimana karakteristik pelanggan berdasarkan **informasi personalnya** (jenis kota, status pernikahan, kelamin, jenis perangkat, jenis pembayaran, jenis produk favorit, durasi penggunaan aplikasi/web app) ? Pelanggan yang lebih cenderung tidak churn adalah :

- Pelanggan yang berlokasi di city tier 1,
- Pelanggan yang berstatus sudah menikah,
- Pelanggan yang menggunakan perangkat mobile phone,
- Pelanggan yang menggunakan sistem pembayaran credit card & debit card,
- Pelanggan yang berbelanja produk berjenis gorcery & others,
- Adapun hal yang tidak berpengaruh yaitu jenis kelamin dan durasi penggunaan aplikasi/web app.

2. Bagaimana karakteristik pelanggan berdasarkan **tingkat kepuasannya** (rating, keluhan) ? Pelanggan yang lebih cenderung tidak churn adalah :

- Tidak ada pengaruh rating dalam keputusan pelanggan (indikasi fitur rating tidak berjalan dengan baik),
- Pelanggan yang belum pernah memberikan keluhan.

3. Bagaimana karakteristik pelanggan berdasarkan **riwayat transaksi & promosi yang didapatkan** (lamanya berlangganan, peningkatan jumlah pembelian, jumlah pembelian, penggunaan kupon, penerimaan cashback, jumlah hari setelah hari terakhir pembelian) ? Pelanggan yang lebih cenderung tidak churn adalah :

- Pelanggan yang telah lama berlangganan,
- Pelanggan yang memiliki jumlah peningkatan pembelian dari tahun sebelumnnya,
- Pelanggan yang mendapatkan cashback lebih tinggi,
- Pelanggan yang sering melakukan belanja (dilihat dari jumlah hari terakhir belanja)
- Adapun hal yang tidak berpengaruh yaitu jumlah penggunaan kupon dan jumlah pembelian.


**Berdasarkan hasil modeling didapatkan kesimpulan sebagai berikut :**

1. Model dengan performa terbaik dalam melakukan prediksi berdasarkan hasil uji coba dengan dataset ini adalah XGBoost.

2. Resampler terbaik pada pemodelan menggunakan dataset ini adalah dengan metode SMOTE dikarenakan menghasilkan rata-rata f1 score lebih baik dari metode Random Undersampling untuk semua model.

3. Model terpilih yaitu XGBoost mendapatkan peningkatan performa setelah dilakukan hyperparameter tuning dengan nilai f1 score sebelum tuning sebesar 0.89 dan setelah tuning sebesar 0.90. Parameter hasil tuning adalah sebagai berikut : subsample = 0.9686, n_estimators = 198, max_depth = 8, learning_rate = 0.10712.

4. Fitur yang paling berpengaruh terhadap model adalah 'Tenure', 'Complain', 'PreferedOrderCat', 'CityTier', 'PreferredPaymentMode' dan 'MaritalStatus'.

5. Limitasi Model adalah sebagai berikut :

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

- Sebaiknya lebih difokuskan untuk approach kepada **pelanggan yang berada di lokasi city tier 3** karena merupakan wilayah dengan **pelanggan terbanyak urutan ke-2** tetapi churn rate-nya paling tinggi. Salah satunya adalah dengan cara **melakukan kampanye/promosi dengan sistem pembayaran debit card dan credit card** seperti sistem pembayaran paling favorit di lokasi city tier 1 (lokasi dengan pelanggan terbanyak dan churn rate paling rendah).
- Sebaiknya lebih difokuskan untuk approach kepada pelanggan yang masih **berstatus lajang** karena merupakan **pelanggan terbanyak urutan ke-2** tetapi churn rate-nya paling tinggi. Salah satu caranya adalah dengan **menargetkan pelanggan yang masih muda karena pelanggan yang masih muda cenderung berstatus lajang**.
- Sebaiknya dilakukan **perbaikan terkait akses dan atau sistem web-aplikasi** sehingga dapat meningkatkan minat pelanggan yang selama ini melakukan akses platform e-commerce menggunakan PC/Computer yang memiliki churn rate tinggi.
- Sebaiknya mulai diadakan **kampanye/promosi terkait jenis barang konsumsi harian seperti groceries** karena churn rate-nya rendah tetapi distribusi pelanggannya masih sedikit. Apabila pelanggan yang berbelanja produk seperti groceries meningkat tentu akan meningkatkan revenue karena produk tersebut adalah produk yang akan rutin dibeli.
- Perlu dilakukan **perbaikan/perubahan terhadap sistem rating/feedback/review** yang sedang digunakan setelah itu di lakukan testing untuk setiap jenisnya/perubahannya dan dicari hasil sistem yang terbaik. Hal ini diperlukan agar layanan sistem rating dapat bekerja dengan optimal dan terhindar dari data anomali.
- Perlu dilakukan **penanganan terkait keluhan yang pernah disampaikan oleh pelanggan** karena pelanggan yang pernah memberikan keluhan lebih cenderung akan churn. Salah satu caranya adalah **melakukan kategorisasi pada setiap keluhan yang ada lalu dibuat skala prioritas terkait keluhan yang perlu ditangani**.
- Sebaiknya lebih difokuskan untuk approach kepada **pelanggan yang memiliki tenure rendah**. Salah satu caranya adalah memberikan penawaran/promosi terkait produk-produk populer seperti produk elektronik atau produk-produk dengan churn rate rendah seperti produk groceries.

**Berdasarkan Pemodelan yang sudah dilakukan, diberikan rekomendasi agar performa model dapat bekerja dengan lebih baik dan membantu perusahaan dalam mengatasi retensi pelanggan :**

1. Untuk kedepannya disarankan untuk mengembangkan model machine learning terkait segmentasi sehingga lebih memudahkan tim marketing dalam membuat program kampanye dan promosi.

2. Untuk efisien pemodelan ada baiknya menghapus fitur-fitur yang tidak terlalu berpengaruh terhadap model seperti fitur 'WarehouseToHome', 'Gender', 'HourSpendOnApp', 'OrderAmountHikeFromlastYear', 'CashbackAmount'

3. Untuk meningkatkan performa model, ada berbagai cara diantaranya adalah :
- Memperbanyak jumlah data pelanggan sehingga model lebih baik dalam membedakan pelanggan churn atau tidak,
- Menambah uji coba modelling seperti menggunakan metode resampling lainnya,
- Menghindari data redundan dan data kosong sehingga lebih mudah ketika proses data cleaning.

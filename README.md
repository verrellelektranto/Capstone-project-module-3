# Capstone-project-module-3
Analisis OCBC bank marketing campaign terhadap sales yang melakukan fraud apakah berdampak signifikan terhadap nasabah yang churn atau tidak.

### 1. CONTEXT
OCBC adalah sebuah bank singapore yang sudah berdiri lama sejak 4 April 1941 dengan nama NISP (Nederlandsch Indische Spaar En Deposito Bank). Pada tahun 2008 NISP resmi melakukan merger dengan OCBC singapore dengan berganti nama menjadi OCBC NISP Berbagai benefit dari program yang ditawarkan nasabah cukup variatif. Salah satunya adalah deposito, nasabah yang melakukan deposito melalui booth OCBC yang tersebar di berbagai mall akan mendapatkan benefit yang tidak didapatkan di cabang, yaitu gimmick koper, gopay, ransel dan berbagai gimmmick menarik lainnya.
#### Target :
- 0 : Mencari nasabah tidak churn (aktif)
- 1 : Mengidentifikasi nasabah churn (tidak aktif)


#### 2. PROBLEM STATEMENTS
Pada tahun 2023-2025 terindikasi bahwa terjadi fraud besar-besaran yang dilakukan secara sistematis oleh sales untuk achieve target bulanan. Dampaknya, OCBC rugi secara capital dan mendapati nasabah yang churn dikarenakan gimmick sudah diberikan tapi nasabah tidak menggunakan OCBC mobile. Alhasil, OCBC keluar uang berlebih untuk sales yang achieved dengan cara fraud dan rugi secara gimmick yang sudah diberikan nasabah churn. Bahkan ada yang mengimingi-imingi auto approve kartu kredit 90 degree north dengan catatan nasabah harus deposito dengan nominal minimal Rp. 50.000.000 tenor 3 bulan.

### 3. GOALS
Goals utama adalah untuk memprediksi nasabah yang churn dan tidak, sehingga OCBC BANK dapat menyiapkan strategi marketing campaign yang lebih efektif dan efisien. Tentu, salah duanya juga untuk mengidentifikasi faktor atau penyebab nasabah menjadi churn dengan program deposito OCBC.

### 4. ANALYTIC APPROACH
Kami melakukan pendekatan analysis data untuk menemukan pola pada nasabah yang churn dan tidak. Dengan pendekatan Classification Supervised Learning (logistic Regression) dapat membantu OCBC dalam memprediksi peluang atau probabilitas nasabah churn atau tidak, sehingga OCBC dapat menganalisa lebih lanjut terkait teknis strategi marketing campaign mendatang.

### 5. METRIC EVALUATION
Type 1 error : False Positive  
Konsekuensi: OCBC merugi secara capital untuk mengeluarkan insentif sales-sales yang achieved monthly dan reward trip beserta dana yang dikeluarkan untuk gimmick pada nasabah churn.

Type 2 error : False Negative  
Konsekuensi: Risiko kehilangan nasabah loyal meningkat.


### source :
#### - https://mediakonsumen.com/2025/02/21/surat-pembaca/janji-palsu-bonus-aktivasi-kartu-kredit-ocbc-90n
#### - https://mediakonsumen.com/2025/02/28/tanggapan/tanggapan-perihal-janji-palsu-bonus-aktivasi-kartu-kredit-ocbc-90n


### Attribute Information

| Attribute | Data Type, Length | Description |
| --- | --- | --- |
| age | Long (64-bit) | Umur nasabah (tahun). |
| job | Text | Jenis pekerjaan nasabah. |
| balance | Long (64-bit) | Saldo rata-rata tahunan pada rekening (mata uang lokal). |
| housing | Text | Kepemilikan kredit rumah (housing loan) (yes/no). |
| loan | Text | Kepemilikan kredit pribadi (personal loan) (yes/no). |
| contact | Text | Media kontak yang digunakan (cellular, telephone). |
| month | Text | Bulan kontak terakhir dalam kampanye (januari – december 2022)|
| campaign | Long (64-bit) | Jumlah kontak yang dilakukan selama kampanye saat ini. |
| pdays | Long (64-bit) | Jumlah hari sejak kontak terakhir pada kampanye sebelumnya (-1 = belum pernah dihubungi). |
| poutcome | Text | Hasil kampanye pemasaran sebelumnya (uccess, failure, unknown). |
| deposit | Text | Target: apakah nasabah berlangganan deposito berjangka (yes/no). |
| Sales Fraud | text | Apakah sales yang melakukan fraud berpengaruh pada churn atau tidaknya seorang nasabah? |


### SUMMARY
#### - Kita telah membuat fitur simulasi `sales_fraud` yang meningkatkan kemungkinan churn pada kondisi tertentu.
#### - EDA dan ablation menunjukkan bahwa kehadiran `sales_fraud` meningkatkan kemampuan model dalam memprediksi churn, 
####   sehingga dapat dikatakan churn terpengaruh oleh adanya fraud (sesuai skenario sales yang dilakukan secara sistematis).
#### - Model terbaik telah kami simpan dan dapat didemokan melalui UI sederhana dengan Gradio.

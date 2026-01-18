# Prediksi Indikasi Cedera Pada Atlet
## Latar belakang
Dalam ranah olahraga kompetitif, memahami faktor-faktor yang memengaruhi performa atlet sangatlah krusial untuk mengoptimalkan program latihan, meningkatkan strategi pemulihan, dan mengurangi risiko cedera. Seiring dengan meningkatnya ketersediaan data, ilmu keolahragaan telah berkembang dengan memanfaatkan analitik untuk mengevaluasi performa atlet secara holistik. Proyek ini berfokus pada analisis kumpulan data yang mencakup berbagai atribut atlet, termasuk karakteristik fisik, intensitas latihan, pola pemulihan, skor performa, serta indikator cedera. Dengan melakukan analisis menyeluruh terhadap faktor-faktor tersebut, kami bertujuan untuk memperoleh wawasan yang dapat ditindaklanjuti guna menyusun strategi latihan dan meningkatkan pencapaian atlet.
## Tujuan Analisis (Goals)
1. Evaluasi Performa: Untuk menilai hubungan antara intensitas latihan, jumlah jam latihan, dan hari pemulihan dengan skor performa serta kontribusi tim.
2. Visualisasi Data: Untuk membuat visualisasi yang secara efektif mengomunikasikan temuan dan tren, sehingga hasil analisis dapat dengan mudah dipahami oleh pelatih kepala, pelatih fisik (trainers), dan atlet.
3. Wawasan Demografis: Untuk menganalisis pengaruh faktor demografis, seperti usia dan jenis kelamin, terhadap performa dan risiko cedera.
4. Penilaian Risiko Cedera: Untuk menelaah faktor-faktor yang berkaitan dengan risiko ACL dan indikator cedera, guna memberikan wawasan bagi strategi pencegahan cedera.
5. Analisis Korelasi: Untuk mengeksplorasi korelasi antara berbagai metrik, yang memungkinkan pemahaman lebih mendalam mengenai dinamika yang memengaruhi performa atlet.
## Alur Kerja (Workflow)
### 1. Data Preprocessing
Dataset sudah cukup bersih sehingga tidak perlu mengatasi missing value serta outlier.
### 2. One-Hot Encoding
Dataset terdapat beberapa variabel kategorik, yaitu:
- Position: Terdiri dari Center, Forward, Guard
- Gender: Terdiri dari Female dan Male
### 3. Data Standardization
Teknik yang digunakan:
- StandardScaler: menyamakan rentang nilai pada semua fitur numerik ke dalam skala yang seragam, agar model tidak bias terhadap fitur yang memiliki angka satuan lebih besar.
### 4. Data Imbalance
Dataset menunjukkan adanya ketidakseimbangan kelas pada distribusi target (Injury Indicator). teknik yang digunakan:
- SMOTE (Synthetic Minority Over-sampling Technique): menangani ketidakseimbangan data (jumlah kasus "cedera" yang jauh lebih sedikit dibandingkan "tidak cedera").
### 4. Model Machine Learning
algoritma yang digunakan:
- Random Forest: menangani hubungan data yang kompleks dengan akurasi tinggi serta dapat mengidentifikasi faktor-faktor paling berpengaruh terhadap risiko cedera.
## Hasil dan Insight
### Fitur paling berpengaruh (Feature Importance)
Berdasarkan algoritma Random Forest, fitur-fitur yang cukup mempengaruhi indikasi cedera adalah:
1. ACL_Risk_Score: Indikator medis langsung mengenai kerentanan ligamen lutut yang memiliki korelasi paling kuat dan spesifik terhadap kejadian cedera fisik serius.
2. Load_Balance_Score: Ketidakseimbangan antara beban latihan dan kapasitas fisik tubuh merupakan penyebab utama overtraining, yang secara drastis meningkatkan potensi kerusakan jaringan.
3. Recovery_Days_Per_Week: Kurangnya waktu pemulihan mencegah regenerasi otot secara optimal, menyebabkan akumulasi kelelahan mikro yang berujung pada cedera.
4. Fatigue_Score: ingkat kelelahan yang tinggi menurunkan kontrol motorik dan konsentrasi atlet, sehingga meningkatkan risiko kesalahan gerak yang fatal.
5. Weight_kg:Massa tubuh yang lebih besar memberikan tekanan biomekanik tambahan pada sendi dan tumpuan kaki, terutama saat melakukan manuver berintensitas tinggi.
## Performa Model
Algoritma Random Forest mendapatkan Akurasi yang tinggi, mencapai 97,5%. model dievaluasi menggunakan Classification Report.


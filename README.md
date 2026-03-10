# Analisis Sentimen Ulasan ChatGPT di Play Store

## Gambaran Umum Proyek

Proyek ini bertujuan untuk menganalisis dan mengklasifikasikan ulasan pengguna ChatGPT dari Play Store ke dalam sentimen positif, negatif, dan netral. Analisis ini memanfaatkan teknik Pemrosesan Bahasa Alami (NLP) dan berbagai model pembelajaran mesin untuk mendapatkan wawasan tentang umpan balik pengguna. Hasil proyek ini dapat membantu meningkatkan kepuasan pelanggan dan memandu pengembangan produk berdasarkan sentimen pengguna yang sebenarnya.

## Pustaka yang Digunakan

- **Pandas**: Untuk manipulasi dan analisis data.

- **NumPy**: Untuk operasi numerik.

- **Seaborn dan Matplotlib**: Untuk visualisasi data.

- **Re**: Untuk ekspresi reguler dalam pemrosesan teks.

- **NLTK dan SpaCy**: Untuk pemrosesan teks dan tugas NLP.

- **WordCloud**: Untuk menghasilkan visualisasi word cloud.

- **PIL**: Untuk pemrosesan gambar.

- **Scikit-learn**: Untuk tugas pembelajaran mesin.

- **Imbalanced-learn**: Untuk menangani dataset yang tidak seimbang.

- **XGBoost**: Untuk penguatan gradien tingkat lanjut.

## Analisis Data Eksplorasi (EDA)

Dataset ulasan ChatGPT dimuat dan diperiksa untuk memahami strukturnya. EDA meliputi:

- **Distribusi Peringkat**: Memvisualisasikan distribusi peringkat untuk mengidentifikasi tren dan pola.

- **Analisis Nilai yang Hilang**: Mengidentifikasi dan menangani nilai yang hilang.

- **Analisis Teks Ulasan**: Menghasilkan awan kata untuk memvisualisasikan kata-kata yang paling umum dalam ulasan.

## Pra-pemrosesan Data

1. **Menggabungkan Kolom**: Menggabungkan stempel waktu ulasan dan teks ulasan ke dalam satu kolom untuk analisis komprehensif.

2. **Mengubah Menjadi Huruf Kecil**: Mengubah semua teks menjadi huruf kecil untuk menjaga keseragaman.

3. **Menghapus Tanda Baca dan Emoji**: Membersihkan data teks dengan menghapus karakter yang tidak perlu.

4. **Penghapusan Kata-Kata Penghenti**: Menghilangkan kata-kata umum yang tidak berkontribusi secara signifikan terhadap analisis sentimen.

5. **Lematisasi**: Mengurangi kata-kata ke bentuk dasarnya menggunakan SpaCy.

6. **Penghapusan Kata-Kata Spesifik**: Menghapus kata-kata spesifik untuk aplikasi (misalnya, 'chatgpt', 'aplikasi') untuk fokus pada kata-kata yang mengandung sentimen.

## Pemetaan Sentimen

Peringkat dipetakan ke sentimen:

- **Positif**: Peringkat > 3
- **Netral**: Peringkat = 3
- **Negatif**: Peringkat < 3

## Penanganan Data Tidak Seimbang

Dataset tidak seimbang, dengan proporsi ulasan positif yang lebih tinggi. Untuk mengatasi hal ini, Synthetic Minority Over-sampling Technique (SMOTE) digunakan untuk menyeimbangkan dataset dengan melakukan oversampling pada kelas minoritas.

## Ekstraksi Fitur

Fitur teks diekstraksi menggunakan:
- **Count Vectorizer**: Mengonversi teks menjadi model bag-of-words.

- **TF-IDF Vectorizer**: Mengonversi teks menjadi fitur term frequency-inverse document frequency (TF-IDF).

## Pelatihan dan Evaluasi Model

### Pembagian Data Pelatihan dan Pengujian

Data dibagi menjadi set pelatihan dan pengujian menggunakan pembagian 85-15 dengan stratifikasi untuk mempertahankan distribusi sentimen.

### Multinomial Naive Bayes

- **Pelatihan**: Model Multinomial Naive Bayes dilatih pada data yang telah diproses.

- **Evaluasi**: Kinerja model dievaluasi menggunakan metrik klasifikasi, mencapai akurasi yang wajar.

### Regresi Logistik

- **Pelatihan**: Model regresi logistik dilatih pada dataset yang seimbang.

- **Evaluasi**: Kinerja model dievaluasi, menunjukkan hasil yang kompetitif.

### XGBoost

- **Pelatihan**: Model XGBoost dilatih menggunakan API DMatrix untuk penanganan data yang efisien.

- **Evaluasi**: XGBoost mencapai akurasi tertinggi sebesar 92%, menunjukkan kinerja yang unggul dibandingkan model lain.

## Kesimpulan

Proyek ini berhasil mengklasifikasikan ulasan pengguna ChatGPT dari Play Store ke dalam sentimen positif, negatif, dan netral. XGBoost muncul sebagai model berkinerja terbaik dengan akurasi 92%. Analisis sentimen ini memberikan wawasan berharga bagi bisnis untuk memahami umpan balik pengguna, meningkatkan kepuasan pelanggan, dan membuat keputusan berbasis data untuk peningkatan produk.

Secara keseluruhan, model analisis sentimen yang dikembangkan menawarkan alat yang andal untuk menganalisis dan memahami sentimen pengguna dalam ulasan, membantu meningkatkan kualitas dan pengalaman pengguna ChatGPT.

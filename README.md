# Analisis Sentimen Ulasan Aplikasi Rosalia Indah - Pemrosesan Bahasa Alami

Nama: **Muhammad Rafi Widya Danendra**  
NRP: **5026221088**  
Tugas 1A - Pemrosesan Bahasa Alami

## 📋 Deskripsi Proyek

Proyek ini merupakan implementasi *pipeline* *Natural Language Processing* (NLP) untuk menganalisis sentimen dari ulasan pengguna aplikasi **Rosalia Indah** di Google Play Store. Proyek ini mencakup pengumpulan data, preprocessing untuk Bahasa Indonesia, analisis data eksploratif (EDA), *feature engineering* (BoW & TF-IDF), pelatihan dan evaluasi model *machine learning*, serta Part of Speech (POS).

## 🎯 Tujuan Proyek

- Mengimplementasikan *pipeline* NLP yang untuk data ulasan berbahasa Indonesia.
- Mengekstrak *insight* mengenai kekuatan dan kelemahan aplikasi berdasarkan opini pengguna.
- Menganalisis tren sentimen dari waktu ke waktu dan per versi aplikasi untuk mengidentifikasi dampak dari setiap pembaruan.
- Membangun dan membandingkan model klasifikasi sentimen untuk menemukan yang paling seimbang dan akurat.

## 🛠️ Teknologi yang Digunakan

- **Python 3.13.3**
- **Pandas & NumPy**: Manipulasi dan analisis data
- **Google Play Scraper**: Pengambilan data ulasan
- **Sastrawi**: Preprocessing teks Bahasa Indonesia (*stemming* & *stopwords*)
- **NLTK**: Tokenisasi
- **Scikit-learn**: *Feature engineering* (BoW, TF-IDF) dan pemodelan (*machine learning*)
- **Stanza**: POS Tagging untuk Bahasa Indonesia
- **Matplotlib & Seaborn**: Visualisasi data
- **WordCloud**: Visualisasi kata kunci
- **tqdm**: Progress bar

## 📚 Struktur Proyek

### Week 1: Latihan Tokenisasi Teks
Implementasi dan eksplorasi tokenisasi dasar menggunakan berbagai korpus Bahasa Indonesia.

File:

- `Tokenisasi Teks dengan Korpus Gutenberg.ipynb` - Notebook tokenisasi dengan Korpus Gutenberg
- `Tokenisasi Teks Indonesia dengan Korpus IndoNLU.ipynb` - Notebook tokenisasi dengan Korpus IndoNLU
- `tokens_sample_1.txt` - Hasil tokenisasi sample 1
- `tokens_sample_2.txt` - Hasil tokenisasi sample 2
- `tokens_sample_3.txt` - Hasil tokenisasi sample 3

---

### Week 2: Pengumpulan Data, Preprocessing, dan EDA Awal
Tahap ini dilakukan pengumpulan data mentah, pembersihan teks secara mendalam, dan analisis eksploratif untuk mendapatkan insight awal.

**File:**
- `1_Data_Scrapping.ipynb` - Script untuk mengambil data ulasan dari Google Play Store.
- `2_Preprocessing.ipynb` - Script untuk membersihkan teks, termasuk normalisasi slang dan penanganan negasi.
- `3_EDA.ipynb` - Analisis dan visualisasi data, termasuk tren per versi aplikasi dan analisis N-grams.
- `df_rosaliarev_raw.csv` - Data mentah hasil scraping.
- `df_rosaliarev_preprocessed.csv` - Data yang sudah bersih dan siap dianalisis.

**Output:**
- **df_rosaliarev_raw.csv**: Data mentah ulasan aplikasi Rosalia Indah.
- **df_rosaliarev_preprocessed.csv**: Data yang sudah melalui proses pembersihan teks tingkat lanjut.

---

### Week 3: Feature Engineering (Bag of Words)
Implementasi Bag of Words (BoW) untuk mengubah teks menjadi fitur numerik, termasuk frasa 2 kata (bigram) untuk menangkap konteks.

**File:**
- `4_BoW.ipynb` - Notebook untuk implementasi Bag of Words dengan N-grams.
- `bow_features_cleaned.csv` - Matriks fitur hasil BoW yang sudah bersih.

**Output:**
- **bow_features_cleaned.csv**: Matriks fitur BoW setelah dilakukan *rare words removal* dan penyertaan bigram.

---

### Week 4: Feature Engineering (TF-IDF) & Pemodelan
Implementasi TF-IDF dan pelatihan model *machine learning* untuk klasifikasi sentimen.

**File:**
- `5_TF-IDF.ipynb` - Notebook untuk implementasi TF-IDF.
- `6_Modeling_dan_Evaluasi.ipynb` - Script untuk melatih dan mengevaluasi model Naive Bayes dan Logistic Regression.
- `tfidf_features.csv` - Matriks fitur hasil TF-IDF.

**Output:**
- **tfidf_features.csv**: Matriks fitur TF-IDF yang siap digunakan untuk pemodelan.
- Laporan perbandingan performa model Naive Bayes dan Logistic Regression.

---

### Week 5: Analisis Linguistik Lanjutan (POS Tagging)
Analisis gramatikal mendalam menggunakan Part-of-Speech (POS) Tagging untuk mengekstrak kata kunci dan frasa deskriptif.

**File:**
- `7_POS_dan_Keyword_Extraction.ipynb` - Notebook implementasi POS Tagging dengan Stanza.

**Output:**
- Visualisasi distribusi kelas kata (Noun, Verb, Adjective).
- Daftar kata kunci dan frasa deskriptif (Sifat-Benda) yang paling umum dalam ulasan.

---

## 🚀 Cara Penggunaan

### Instalasi Dependencies
Disarankan untuk membuat *virtual environment* terlebih dahulu.
```bash
# Clone repository
git clone https://github.com/mrafiwd/pba-gasal-2025_5026221088.git
cd pba-gasal-2025_5026221088

# Install required packages
pip install pandas google-play-scraper sastrawi nltk scikit-learn stanza matplotlib seaborn wordcloud tqdm

# Download Stanza Indonesian model (hanya perlu sekali)
python -c "import stanza; stanza.download('id')"

# Download NLTK data (hanya perlu sekali)
python -c "import nltk; nltk.download('punkt')"
```

---

### Menjalankan Proyek Secara Berurutan
Jalankan file Jupyter Notebook secara berurutan sesuai dengan penamaannya (dari 1 hingga 7). Pastikan setiap notebook selesai dieksekusi sebelum melanjutkan, karena setiap tahap menghasilkan file .csv yang dibutuhkan oleh tahap selanjutnya.

- **Week 2**: Jalankan 1_Data_Scrapping.ipynb, lalu 2_Preprocessing.ipynb, dan 3_EDA.ipynb.

- **Week 3**: Jalankan 4_BoW.ipynb.

- **Week 4**: Jalankan 5_TF-IDF.ipynb, lalu 6_Modeling_dan_Evaluasi.ipynb.

- **Week 5**: Jalankan 7_POS_dan_Keyword_Extraction.ipynb.

---

## 📈 Hasil & Insights
Proyek ini menghasilkan berbagai insights tentang ulasan aplikasi Rosalia Indah:

- Distribusi Sentimen: Sebagian besar ulasan bersifat Positif, namun terdapat jumlah ulasan Negatif yang signifikan yang menyoroti area-area yang perlu perbaikan.

- Topik Negatif Utama: Keluhan pengguna sebagian besar berpusat pada masalah fungsionalitas aplikasi, seperti:

  - Kesulitan login dan daftar akun (frasa umum: "kode otp tidak", "tidak login").

  - Aplikasi yang sering error atau tidak bisa dibuka.

  - Masalah terkait pemesanan tiket dan kode OTP.

- Topik Positif Utama: Pengguna memberikan sentimen positif terutama karena aplikasi dianggap membantu, mudah digunakan, dan membuat perjalanan menjadi nyaman.

- Performa Model:

  - Naive Bayes menunjukkan akurasi yang lebih tinggi (~81%), namun gagal total dalam mengidentifikasi ulasan 'Netral'.

  - Logistic Regression menunjukkan akurasi total yang sedikit lebih rendah (~73%) tetapi merupakan model yang jauh lebih baik dan seimbang, karena berhasil mengidentifikasi ketiga kelas sentimen, termasuk kelas 'Netral' yang minoritas.

---

## Fitur-fitur Utama
### **Week 2: Data Pipeline**
✅ Scraping data otomatis dari Google Play Store.

✅ Preprocessing komprehensif untuk Bahasa Indonesia (termasuk normalisasi slang & penanganan negasi).

✅ EDA mendalam dengan analisis tren per versi aplikasi dan analisis N-grams.

### **Week 3 & 4: Feature Engineering & Modeling**
✅ Ekstraksi fitur dengan BoW dan TF-IDF yang menyertakan bigram.

✅ Rare Words Removal yang efisien menggunakan min_df.

✅ Perbandingan sistematis antara model Naive Bayes dan Logistic Regression.

✅ Penanganan imbalanced data menggunakan class_weight pada Logistic Regression.

### **Week 5: Analisis Lanjutan**
✅ Implementasi POS Tagging yang akurat untuk Bahasa Indonesia menggunakan Stanza.

✅ Ekstraksi wawasan kontekstual melalui analisis frasa Kata Sifat-Kata Benda.

---

## **Troubleshooting**
- **Masalah Stanza Model**: Pastikan Anda menjalankan stanza.download('id') dengan koneksi internet yang stabil.

- **File Tidak Ditemukan**: Pastikan Anda menjalankan notebook secara berurutan, karena file output dari satu tahap menjadi input untuk tahap berikutnya.

- **Memory Error**: Jika terjadi memory error saat memproses data, coba restart kernel notebook atau kurangi jumlah data yang diproses (terutama pada tahap POS Tagging).

---

## Struktur File
```
pba-gasal-2025_5026221088/
│
├── Week1/
│   ├── Tokenisasi Teks dengan Korpus Gutenberg.ipynb
│   ├── Tokenisasi Teks Indonesia dengan Korpus IndoNLU.ipynb
│   └── tokens_sample_1.txt
│   └── tokens_sample_2.txt
│   └── tokens_sample_3.txt
│
├── Week2/
│   ├── 1_Data_Scrapping.ipynb
│   ├── 2_Preprocessing.ipynb
│   ├── 3_EDA.ipynb
│   ├── df_rosaliarev_raw.csv
│   └── df_rosaliarev_preprocessed.csv
│
├── Week3/
│   ├── 4_BoW.ipynb
│   └── bow_features_cleaned.csv
│
├── Week4/
│   ├── 5_TF-IDF.ipynb
│   ├── 6_Modeling_dan_Evaluasi.ipynb
│   └── tfidf_features.csv
│
├── Week5/
│   └── 7_POS_dan_Keyword_Extraction.ipynb
│
└── README.md
```
